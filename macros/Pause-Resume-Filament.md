# Pause, Resume & Filament Handling

> A proper pause macro saves the toolhead position, lifts off the print, parks safely, turns off the hotend, and waits — indefinitely if needed. Resume puts everything back exactly where it left off. Getting this right means filament changes mid-print are reliable rather than a gamble.

---

## The Problem With Default Pause

Klipper's built-in `PAUSE` command stops the print but doesn't do much else — the hotend stays at temperature cooking the filament, the nozzle hovers over the print, and there's no timeout. Leave it long enough and you'll come back to a clogged nozzle resting on a melted hole in your part.

The macros below fix all of that.

---

## PAUSE

```ini
[gcode_macro PAUSE]
rename_existing: BASE_PAUSE
gcode:
    {% set z_hop = params.Z|default(10)|int %}
    {% set x_park = printer.toolhead.axis_maximum.x / 2 %}
    {% set y_park = printer.toolhead.axis_minimum.y + 5 %}

    SAVE_GCODE_STATE NAME=PAUSE_STATE

    BASE_PAUSE

    {% if printer.extruder.can_extrude|lower == 'true' %}
        G91
        G1 E-1.5 F2100          ; small retract to prevent ooze
        G90
    {% endif %}

    {% if printer.toolhead.homed_axes == 'xyz' %}
        G91
        {% if (printer.toolhead.position.z + z_hop) <= printer.toolhead.axis_maximum.z %}
            G1 Z{z_hop} F900    ; hop up
        {% else %}
            G1 Z{printer.toolhead.axis_maximum.z - printer.toolhead.position.z} F900
        {% endif %}
        G90
        G1 X{x_park} Y{y_park} F6000   ; park at front centre
    {% else %}
        {action_respond_info("Printer not homed — skipping park")}
    {% endif %}

    SET_IDLE_TIMEOUT TIMEOUT=43200      ; 12 hour idle timeout during pause
    TURN_OFF_HEATERS                    ; hotend off — saves the filament, saves the nozzle
```

---

## RESUME

```ini
[gcode_macro RESUME]
rename_existing: BASE_RESUME
gcode:
    {% set e_prime = params.E|default(2.5)|float %}

    SET_IDLE_TIMEOUT TIMEOUT={printer.configfile.settings.idle_timeout.timeout}

    {% if printer.extruder.can_extrude|lower == 'true' %}
        G91
        G1 E{e_prime} F2100     ; prime nozzle before returning to print
        G90
    {% endif %}

    RESTORE_GCODE_STATE NAME=PAUSE_STATE MOVE=1 MOVE_SPEED=100
    BASE_RESUME
```

> 💡 **The idle timeout is reset on resume.** During a pause it's stretched to 12 hours so the printer doesn't auto-shutdown mid-swap. On resume it goes back to whatever your normal `[idle_timeout]` is set to.

---

## CANCEL_PRINT

```ini
[gcode_macro CANCEL_PRINT]
rename_existing: BASE_CANCEL_PRINT
gcode:
    SET_IDLE_TIMEOUT TIMEOUT={printer.configfile.settings.idle_timeout.timeout}
    CLEAR_PAUSE
    SDCARD_RESET_FILE
    PRINT_END
    BASE_CANCEL_PRINT
```

Calling `PRINT_END` here means your cancel sequence follows the same cleanup path as a normal finish — heaters off, fan off, park, mesh clear.

---

## M600 — Filament Change Compatibility

Slicers that insert colour change commands use M600. Without this alias, those commands do nothing in Klipper:

```ini
[gcode_macro M600]
gcode:
    {% set x_park = printer.toolhead.axis_maximum.x / 2 %}
    {% set y_park = printer.toolhead.axis_minimum.y + 5 %}
    {% set z_hop = [printer.toolhead.position.z + 10, printer.toolhead.axis_maximum.z]|min %}

    SAVE_GCODE_STATE NAME=M600_STATE
    PAUSE
    G1 X{x_park} Y{y_park} Z{z_hop} F6000
```

Now when a slicer colour change fires mid-print, it drops into your `PAUSE` macro automatically.

---

## Filament Sensors

### Basic Switch Sensor

Detects presence or absence of filament. Simple and reliable for runout detection.

```ini
[filament_switch_sensor filament_sensor]
switch_pin: ^PB6       ; ^ prefix enables internal pull-up — required to prevent false triggers
pause_on_runout: True
runout_gcode:
    PAUSE
insert_gcode:
    M117 Filament inserted
```

### Smart Motion Sensor (BTT Smart Filament Sensor)

Detects actual filament movement rather than just presence. Catches jams and tangles that a switch sensor would miss — the filament is still there but has stopped moving.

```ini
[filament_motion_sensor filament_sensor]
switch_pin: ^PB6
detection_length: 10   ; 10mm recommended — any shorter and Bowden flex causes false positives
extruder: extruder
pause_on_runout: True
runout_gcode:
    PAUSE
```

> ⚠️ **Keep the `^` pull-up prefix on the pin** regardless of sensor type. Without it the pin floats and you'll get random false trigger pauses mid-print.

> 💡 **Smart sensors need 10mm detection length.** The filament in a Bowden setup rocks back and forth slightly during retraction and pressure advance — too short a window and the sensor interprets normal movement as a jam.

---

## Disabling the Sensor During Pauses

If your filament sensor is running while you load new filament during a swap, it will immediately re-trigger and pause again. Disable it in PAUSE and re-enable in RESUME:

In your `PAUSE` macro, add:
```gcode
SET_FILAMENT_SENSOR SENSOR=filament_sensor ENABLE=0
```

In your `RESUME` macro, add:
```gcode
SET_FILAMENT_SENSOR SENSOR=filament_sensor ENABLE=1
```

---

*Back to [Macro Guides](../README.md#️-klipper-macros) | [README](../README.md)*
