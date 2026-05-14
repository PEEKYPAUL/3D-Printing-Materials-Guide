# Conditional Homing & Conditional QGL

> Two small macros that every other macro in your config will thank you for. Instead of blindly re-homing or re-levelling at the start of every macro call, these check first — and only do the work if it's actually needed.

---

## The Problem

Without conditional homing, any macro that needs the printer to be homed has two bad options:

1. **Run G28 unconditionally** — adds 30–90 seconds to every macro call, even if you just homed five minutes ago
2. **Skip homing checks entirely** — which means if the printer somehow isn't homed, the macro moves to coordinates that make no sense and crashes

Conditional homing solves this cleanly. Call `_CG28` at the start of any macro instead of `G28` and it only homes when it needs to.

---

## _CG28 — Conditional Home

```ini
[gcode_macro _CG28]
description: Home only if not already homed
gcode:
    {% if "xyz" not in printer.toolhead.homed_axes %}
        G28
    {% endif %}
```

That's the whole thing. Klipper exposes `printer.toolhead.homed_axes` as a string containing whichever axes are currently homed. If all three are in there, skip. If not, home.

**Usage — replace `G28` with `_CG28` inside other macros:**

```gcode
; Instead of this:
G28

; Use this:
_CG28
```

> 💡 The underscore prefix (`_CG28`) is a Klipper convention for "internal" macros — they don't appear in the Mainsail / Fluidd macro buttons panel, which keeps your UI clean. Any macro starting with `_` is hidden from the dashboard by default.

---

## _CQGL — Conditional Quad Gantry Level

For Voron 2.4 and other printers with four independent Z motors that require `QUAD_GANTRY_LEVEL` before printing.

```ini
[gcode_macro _CQGL]
description: Run QGL only if not already levelled
gcode:
    {% if printer.quad_gantry_level.applied == False %}
        {% if "xyz" not in printer.toolhead.homed_axes %}
            G28
        {% endif %}
        QUAD_GANTRY_LEVEL
        G28 Z
    {% endif %}
```

This checks `printer.quad_gantry_level.applied` — a boolean that Klipper sets to `True` after a successful QGL. If levelling has already been done this session, the macro skips it entirely. If not, it homes first (if needed), levels, then re-homes Z — because QGL changes the Z position.

**For Trident (Z_TILT_ADJUST instead of QGL):**

```ini
[gcode_macro _CTILT]
description: Run Z tilt adjust only if not already done
gcode:
    {% if printer.z_tilt.applied == False %}
        {% if "xyz" not in printer.toolhead.homed_axes %}
            G28
        {% endif %}
        Z_TILT_ADJUST
        G28 Z
    {% endif %}
```

---

## Using Both in PRINT_START

The real power is combining them. A clean PRINT_START using conditional macros:

```gcode
[gcode_macro PRINT_START]
gcode:
    _CG28       ; home only if needed
    _CQGL       ; level only if needed
    BED_MESH_CALIBRATE
    ...
```

If you're running a second print back-to-back and the printer is already homed and levelled, both macros skip their work. The mesh still runs (it should, because the print area may differ), but you've already saved a minute or more of unnecessary motion.

---

*Back to [Macro Guides](../README.md#️-klipper-macros) | [README](../README.md)*
