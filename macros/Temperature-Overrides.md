# Temperature Overrides — Replacing M109 & M190

> M109 and M190 are legacy Marlin commands for "heat and wait." Klipper supports them for compatibility, but they have a frustrating quirk: they block the command queue entirely while waiting. Swapping them out for Klipper-native `TEMPERATURE_WAIT` gives you smarter, non-blocking temperature management.

---

## The Problem With M109 / M190

When Klipper processes `M109` or `M190`, it holds the entire G-code queue until the target temperature is reached. Nothing else can run — no fans, no status updates, nothing. More importantly, it only triggers at the **exact** target temperature. If your hotend is at 199.8°C and the target is 200°C, it waits. If it overshoots to 201°C and cools back down, it triggers immediately on the way up, potentially before the temperature has actually stabilised.

`TEMPERATURE_WAIT` lets you set a minimum and maximum range, so the printer moves on once the temperature is stable within a window — not just the moment a single reading crosses a threshold.

---

## The Replacement Macros

These redefine M109 and M190 so anything in your config or slicer that uses those commands transparently gets the better behaviour instead. No need to change your slicer start G-code.

```ini
[gcode_macro M109]
rename_existing: M109.1
description: Override M109 — wait for hotend temp using TEMPERATURE_WAIT
gcode:
    {% set s = params.S|float %}
    M104 S{s}                                ; start heating (non-blocking)
    {% if s > 0 %}
        TEMPERATURE_WAIT SENSOR=extruder MINIMUM={s - 2} MAXIMUM={s + 5}
    {% endif %}
```

```ini
[gcode_macro M190]
rename_existing: M190.1
description: Override M190 — wait for bed temp using TEMPERATURE_WAIT
gcode:
    {% set s = params.S|float %}
    M140 S{s}                                ; start bed heating (non-blocking)
    {% if s > 0 %}
        TEMPERATURE_WAIT SENSOR=heater_bed MINIMUM={s - 2} MAXIMUM={s + 5}
    {% endif %}
```

---

## What the Ranges Mean

| Parameter | Value | Meaning |
|---|---|---|
| `MINIMUM={s - 2}` | Target minus 2°C | Triggers once temp is within 2°C below target |
| `MAXIMUM={s + 5}` | Target plus 5°C | Allows up to 5°C overshoot before waiting |

So if you set `M109 S200`, the printer waits until the hotend is between 198°C and 205°C. This catches real-world PID overshoot on the way up without waiting for a perfect reading that may never come on a bouncy temperature curve.

Adjust the window to suit your printer. A well-tuned PID needs a tighter window (`±1`). A noisy or poorly-tuned system may need more headroom.

> 💡 The `rename_existing` directive is what makes this safe. It renames the original command to `M109.1` and `M190.1` before defining the new macro — so if you ever need the original behaviour for any reason, it's still available. Without this, redefining M109 would cause infinite recursion.

---

## When You Don't Need This

If you've already replaced M109 and M190 calls in your PRINT_START with direct `TEMPERATURE_WAIT` calls — which is the cleanest approach — you may not need these overrides. They're most useful when:

- Your slicer is inserting M109/M190 calls you can't easily edit out
- You're using pre-built macro sets that use these commands internally
- You want a drop-in improvement with no config changes elsewhere

---

*Back to [Macro Guides](../README.md#️-klipper-macros) | [README](../README.md)*
