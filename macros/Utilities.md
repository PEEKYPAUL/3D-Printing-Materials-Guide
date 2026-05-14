# Utility Macros

> A collection of smaller macros that don't fit a single category but earn their place in any Klipper config. OFF for clean shutdown, DUMP_VARIABLES for debugging, TEST_SPEED for finding your printer's limits, and LCD_RGB for display lighting.

---

## OFF — Shutdown Everything

One command to turn off all heaters, fans, and steppers. Useful at the end of a session or as a safety shortcut. The basic version covers everything most printers have — the commented lines are for optional extras like chamber fans or case lighting.

```ini
[gcode_macro OFF]
description: Turn off all heaters, fans, and steppers
gcode:
    TURN_OFF_HEATERS
    M107                            ; part cooling fan off
    M84                             ; steppers off

    # -- Optional extras — uncomment and adjust for your hardware --
    # SET_FAN_SPEED FAN=exhaust_fan SPEED=0
    # SET_FAN_SPEED FAN=bed_fans SPEED=0
    # SET_PIN PIN=case_light VALUE=0
```

> 💡 Because every printer's extras are different, treat `OFF` as a starting point rather than a copy-paste macro. Add or remove lines to match what your printer actually has.

---

## TEST_SPEED — Find Your Printer's Limits

Runs the toolhead through a series of movements at increasing speeds to find where the printer starts losing steps or skipping. Run this after tuning input shaping — then push the numbers up until you find the wall.

```ini
[gcode_macro TEST_SPEED]
description: Test max speed and acceleration. SPEED=mm/s ACCEL=mm/s² ITERATIONS=n BOUND=mm
gcode:
    {% set speed      = params.SPEED|default(printer.configfile.settings.printer.max_velocity)|int %}
    {% set iterations = params.ITERATIONS|default(5)|int %}
    {% set accel      = params.ACCEL|default(printer.configfile.settings.printer.max_accel)|int %}
    {% set bound      = params.BOUND|default(20)|int %}
    {% set max_x      = printer.toolhead.axis_maximum.x - bound %}
    {% set max_y      = printer.toolhead.axis_maximum.y - bound %}
    {% set min_x      = printer.toolhead.axis_minimum.x + bound %}
    {% set min_y      = printer.toolhead.axis_minimum.y + bound %}

    SAVE_GCODE_STATE NAME=TEST_SPEED
    G28
    SET_VELOCITY_LIMIT VELOCITY={speed} ACCEL={accel}
    G90

    {% for i in range(iterations) %}
        G0 X{min_x} Y{min_y} F{speed * 60}
        G0 X{max_x} Y{max_y} F{speed * 60}
        G0 X{min_x} Y{max_y} F{speed * 60}
        G0 X{max_x} Y{min_y} F{speed * 60}
        G0 X{min_x} Y{min_y} F{speed * 60}
        G0 X{min_x + (max_x - min_x) / 2} Y{min_y + (max_y - min_y) / 2} F{speed * 60}
    {% endfor %}

    SET_VELOCITY_LIMIT VELOCITY={printer.configfile.settings.printer.max_velocity} ACCEL={printer.configfile.settings.printer.max_accel}
    RESTORE_GCODE_STATE NAME=TEST_SPEED
```

**Parameters:**

| Parameter | Default | Description |
|---|---|---|
| `SPEED` | `max_velocity` from config | Speed to test in mm/s |
| `ACCEL` | `max_accel` from config | Acceleration to test in mm/s² |
| `ITERATIONS` | 5 | Number of full pattern runs |
| `BOUND` | 20 | Margin from axis limits in mm |

**Example usage:**
```gcode
TEST_SPEED SPEED=300 ACCEL=5000 ITERATIONS=5
TEST_SPEED SPEED=400 ACCEL=8000
```

After the run, check if the toolhead is still where it started. If it's shifted — the printer lost steps somewhere during the test. Drop the speed or accel back until it completes cleanly, then back off 10–15% from that number for your actual print settings.

---

## DUMP_VARIABLES — Debug Helper

Dumps every Klipper variable to the console. Invaluable when writing macros and you need to know exactly what a variable is called or what value it currently holds.

```ini
[gcode_macro DUMP_VARIABLES]
description: Dump all Klipper variables to console. Filter with NAME= or VALUE=
gcode:
    {% set filter_name  = params.NAME|default('')|string|lower %}
    {% set filter_value = params.VALUE|default('')|string|lower %}
    {% set show_cfg     = params.SHOW_CFG|default(0)|int %}

    {% set out = [] %}

    {% for key1 in printer %}
        {% for key2 in printer[key1] %}
            {% if (show_cfg or not (key1|lower == 'configfile' and key2|lower in ['config', 'settings']))
               and (filter_name in key1|lower or filter_name in key2|lower)
               and filter_value in printer[key1][key2]|string|lower %}
                {% set dummy = out.append("printer['%s'].%s = %s" % (key1, key2, printer[key1][key2])) %}
            {% endif %}
        {% else %}
            {% if filter_name in key1|lower and filter_value in printer[key1]|string|lower %}
                {% set dummy = out.append("printer['%s'] = %s" % (key1, printer[key1])) %}
            {% endif %}
        {% endfor %}
    {% endfor %}

    {action_respond_info(out|join("\n"))}
```

**Usage:**

| Command | Result |
|---|---|
| `DUMP_VARIABLES` | Dumps everything (excluding raw config) |
| `DUMP_VARIABLES NAME=stepper` | Only variables with "stepper" in the name |
| `DUMP_VARIABLES NAME=extruder` | Everything extruder-related |
| `DUMP_VARIABLES VALUE=true` | Variables whose current value contains "true" |
| `DUMP_VARIABLES SHOW_CFG=1` | Include the raw config sections too |

The output lands in the console log in Mainsail or Fluidd. Filter aggressively — unfiltered dumps are long.

---

## LCD_RGB — Display Colour Control

If your display supports RGB status lighting (like the MINI12864), this gives you a simple macro to set the colour by name rather than hunting for hex values mid-config.

```ini
[gcode_macro LCD_RGB]
description: Set LCD neopixel colour. Use RED= GREEN= BLUE= (0.0–1.0) or call with a preset
gcode:
    {% set r = params.RED|default(0)|float %}
    {% set g = params.GREEN|default(0)|float %}
    {% set b = params.BLUE|default(0)|float %}
    SET_LED LED=lcd RED={r} GREEN={g} BLUE={b} INDEX=1 TRANSMIT=0
    SET_LED LED=lcd RED={r} GREEN={g} BLUE={b} INDEX=2 TRANSMIT=0
    SET_LED LED=lcd RED={r} GREEN={g} BLUE={b} INDEX=3
```

**Quick colour reference:**

| Colour | Command |
|---|---|
| White | `LCD_RGB RED=1 GREEN=1 BLUE=1` |
| Red | `LCD_RGB RED=1` |
| Green | `LCD_RGB GREEN=1` |
| Blue | `LCD_RGB BLUE=1` |
| Orange | `LCD_RGB RED=1 GREEN=0.3` |
| Off | `LCD_RGB` |

You can call this from inside `PRINT_START` or `PRINT_END` to change the display colour by print phase — useful at a glance to know if the printer is heating, printing, or done without reading the screen.

---

*Back to [Macro Guides](../README.md#️-klipper-macros) | [README](../README.md)*
