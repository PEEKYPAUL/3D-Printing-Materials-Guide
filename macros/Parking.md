# Parking Macros

> Five macros that move the toolhead to useful named positions. All of them home first if needed, save state before moving, and restore it after. Drop them into your config and call them from the console, a button in Mainsail/Fluidd, or from inside other macros.

---

## Why Parking Macros?

Manually jogging the toolhead to get it out of the way, clear for a nozzle swap, or positioned for inspection is tedious and inconsistent. These macros give you one-command shortcuts to the positions you actually use — and because they use the printer's configured axis limits, they scale automatically to any bed size without needing to change values.

---

## The Macros

All five use `_CG28` (conditional homing — see [Conditional Homing](Conditional-Homing.md)) to home only if not already homed, and use `SAVE_GCODE_STATE` / `RESTORE_GCODE_STATE` to leave positioning mode as they found it.

```ini
[gcode_macro PARKFRONT]
description: Park toolhead at front centre, mid height
gcode:
    _CG28
    SAVE_GCODE_STATE NAME=PARKFRONT
    G90
    G0 X{printer.toolhead.axis_maximum.x / 2} Y{printer.toolhead.axis_minimum.y + 5} Z{printer.toolhead.axis_maximum.z / 2} F6000
    RESTORE_GCODE_STATE NAME=PARKFRONT
```

```ini
[gcode_macro PARKFRONTLOW]
description: Park toolhead at front centre, low — good for nozzle access
gcode:
    _CG28
    SAVE_GCODE_STATE NAME=PARKFRONTLOW
    G90
    G0 X{printer.toolhead.axis_maximum.x / 2} Y{printer.toolhead.axis_minimum.y + 5} Z20 F6000
    RESTORE_GCODE_STATE NAME=PARKFRONTLOW
```

```ini
[gcode_macro PARKREAR]
description: Park toolhead at rear, near top — clears the bed completely
gcode:
    _CG28
    SAVE_GCODE_STATE NAME=PARKREAR
    G90
    G0 X{printer.toolhead.axis_minimum.x + 10} Y{printer.toolhead.axis_maximum.y - 10} Z{printer.toolhead.axis_maximum.z - 50} F6000
    RESTORE_GCODE_STATE NAME=PARKREAR
```

```ini
[gcode_macro PARKCENTER]
description: Park toolhead at centre of build volume
gcode:
    _CG28
    SAVE_GCODE_STATE NAME=PARKCENTER
    G90
    G0 X{printer.toolhead.axis_maximum.x / 2} Y{printer.toolhead.axis_maximum.y / 2} Z{printer.toolhead.axis_maximum.z / 2} F6000
    RESTORE_GCODE_STATE NAME=PARKCENTER
```

```ini
[gcode_macro PARKBED]
description: Park toolhead above bed centre — useful for first layer inspection
gcode:
    _CG28
    SAVE_GCODE_STATE NAME=PARKBED
    G90
    G0 X{printer.toolhead.axis_maximum.x / 2} Y{printer.toolhead.axis_maximum.y / 2} Z15 F6000
    RESTORE_GCODE_STATE NAME=PARKBED
```

---

## Which One to Use When

| Macro | Best Used For |
|---|---|
| `PARKFRONT` | General access — tool changes, visual inspection mid-print |
| `PARKFRONTLOW` | Nozzle swaps, cold pulls, cleaning the nozzle tip |
| `PARKREAR` | Removing a finished print, accessing the bed fully |
| `PARKCENTER` | Mid-print checks, photography |
| `PARKBED` | Z offset checks, first layer inspection |

---

## Adding to Mainsail / Fluidd

In Mainsail or Fluidd you can add these as macro buttons that appear in the dashboard. In Mainsail, go to **Interface Settings → Macros** and they will appear automatically once defined. In Fluidd they show up in the Macros panel. No additional configuration needed — Klipper exposes all `[gcode_macro]` definitions to the UI automatically.

---

*Back to [Macro Guides](../README.md#️-klipper-macros) | [README](../README.md)*
