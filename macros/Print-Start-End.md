# PRINT_START & PRINT_END

> The two most important macros in your Klipper config. Every slicer calls these at the start and end of every print. Getting them right means your printer homes, heats, meshes, and purges cleanly before the first layer — and parks and cools down properly at the end.

---

## Why Bother?

Out of the box, slicers send raw G-code for start and end sequences — fixed temperature commands, no conditional logic, no mesh loading, no adaptive features. PRINT_START gives you full control: you decide the order, you control what runs and when, and you can pass variables from the slicer like bed and nozzle temperatures so the macro handles everything.

---

## Slicer Setup

Before the macro does anything useful, you need to tell your slicer to hand off to it. Replace your slicer's start G-code with this (Orca Slicer / PrusaSlicer / SuperSlicer):

```gcode
PRINT_START EXTRUDER={first_layer_temperature[initial_extruder]} BED={first_layer_bed_temperature} CHAMBER={chamber_temperature}
```

And your end G-code:

```gcode
PRINT_END
```

That's it on the slicer side. Everything else lives in your `printer.cfg` or a macro include file.

---

## PRINT_START

A solid general-purpose starting macro. Adjust the park position, purge line, and any printer-specific sections for your setup.

```ini
[gcode_macro PRINT_START]
gcode:
    {% set target_extruder = params.EXTRUDER|int %}
    {% set target_bed = params.BED|int %}
    {% set target_chamber = params.CHAMBER|default(0)|int %}

    # -- Heat bed first, hotend to safe no-ooze temp while waiting --
    M140 S{target_bed}                         ; start bed heating (no wait)
    M109 S150                                  ; heat hotend to safe temp — stops ooze while bed heats

    # -- Home --
    G28                                        ; home all axes

    # -- Wait for bed to reach target --
    M190 S{target_bed}                         ; wait for bed temp

    # -- Bed mesh --
    BED_MESH_CALIBRATE                         ; run adaptive mesh (remove if not using a probe)

    # -- Heat hotend to print temp --
    M109 S{target_extruder}                    ; heat to final print temp and wait

    # -- Prime nozzle --
    G92 E0                                     ; reset extruder
    G1 X5 Y5 F3000                             ; move to purge start position
    G1 Z0.3 F600                               ; drop to purge height
    G1 X100 E15 F1500                          ; purge line
    G92 E0                                     ; reset extruder again

    # -- Ready --
    G90                                        ; absolute positioning
    G92 E0
```

> 💡 **Pre-heating the hotend to 150°C** while the bed soaks up to temperature stops ooze dripping onto the build plate during homing and levelling — but it keeps the nozzle below the temp where serious material degradation begins for most filaments.

> 💡 **If you use Klippain Shake&Tune or have a skew profile**, load them here — after the mesh and before the final heat. Example:
> ```gcode
> SKEW_PROFILE LOAD=califlower
> ```

---

## PRINT_END

```ini
[gcode_macro PRINT_END]
gcode:
    # -- Secure the final position --
    M400                                       ; wait for moves to finish
    G92 E0                                     ; reset extruder

    # -- Retract slightly to break the melt zone --
    G1 E-2 F3600

    # -- Move toolhead to safe park position --
    {% set x_safe = printer.toolhead.position.x + 20 %}
    {% set y_safe = printer.toolhead.position.y + 20 %}
    {% set z_safe = [printer.toolhead.position.z + 10, printer.toolhead.axis_maximum.z]|min %}

    G0 X{x_safe} Y{y_safe} Z{z_safe} F20000   ; move away from print
    G0 X{printer.toolhead.axis_maximum.x / 2} Y{printer.toolhead.axis_maximum.y - 10} F3600 ; park rear

    # -- Shutdown --
    TURN_OFF_HEATERS
    M107                                       ; turn off part cooling fan
    M84                                        ; disable steppers
    BED_MESH_CLEAR                             ; clear the mesh
    SET_SKEW CLEAR=1                           ; clear skew profile if loaded
```

> ⚠️ The safe Z calculation — `[current_z + 10, max_z]|min` — clamps the hop so you never try to move higher than the printer's Z limit. Worth keeping even if you don't think you'll ever print that high.

---

## Adapting For Your Printer

| Feature | How to adapt |
|---|---|
| No bed probe | Remove `BED_MESH_CALIBRATE` and replace with `G28 Z` |
| Enclosed printer with chamber sensor | Add `TEMPERATURE_WAIT SENSOR="temperature_sensor chamber" MINIMUM={target_chamber}` after the bed wait |
| Klicky / TAP / Beacon probe | Your probe macro replaces or wraps `BED_MESH_CALIBRATE` — check your probe's documentation |
| Nozzle scrubber | Call your scrub macro after final hotend heat and before the purge line |
| Multi-colour / ERCF | Your MMU macro set will override PRINT_START entirely — follow that system's setup guide |

---

*Back to [Macro Guides](../README.md#️-klipper-macros) | [README](../README.md)*
