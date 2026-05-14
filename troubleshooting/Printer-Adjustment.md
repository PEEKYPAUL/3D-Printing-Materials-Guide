# Printer Adjustment — Skew & Scale Calibration

> Even a well-built printer can have subtle inaccuracies baked in — axes that aren't perfectly square, or parts that print slightly too large or too small. This guide covers how to identify and correct both problems using the **Califlower Calibration Tool**.

---

## What Problems Does This Fix?

### Skew (XY Plane Misalignment)

Skew occurs when your X and Y axes are not perfectly perpendicular to each other. Even a small misalignment — invisible to the naked eye on the frame — causes printed parts to be subtly parallelogram-shaped rather than truly square. It shows up as:

- Rectangles that are not quite right-angles when measured diagonally
- Circles that print as ellipses
- Parts that don't mate cleanly with each other even if dimensions seem correct
- Press-fit joints that are tight on one side and loose on the other

Skew can come from a slightly off-square frame, uneven belt tension, or imperfect XY joint alignment. It cannot be fixed by adjusting hardware alone in most cases — it must be corrected in firmware or slicer.

### Size / Scale Error (XY Dimensional Accuracy)

Scale error means the printer is consistently printing slightly too large or too small in X and/or Y. This is caused by incorrect `rotation_distance` values in Klipper (or e-steps in Marlin), belt stretch, or pulley diameter tolerances. It shows up as:

- Holes that are always slightly too tight or too loose
- Parts that are consistently a fraction of a mm off in one axis
- Assemblies that never quite fit even after accounting for tolerances

---

## The Tool — Califlower Calibration Tool Mk2

**[→ Buy from Vector 3D — £8.00](https://vector3d.shop/products/califlower-calibration-tool-mk2)**

The Califlower is an STL file paired with a web-based calculator. You print the included model, take a series of measurements, enter them into the calculator, and receive ready-to-paste correction values for your firmware or slicer. No manual maths required.

**What you get:**
- The Califlower STL — a precisely designed calibration print
- Access to the web calculator at [vector3d.co.uk](https://vector3d.co.uk)
- Step-by-step guided workflow with 3D visualisation
- Copy-paste correction commands for your firmware
- Skew correction **and** size correction in one workflow

**Firmware compatibility:**

| Firmware | Skew Correction | Size Correction |
|---|---|---|
| Klipper | ✅ `[skew_correction]` section | ✅ `rotation_distance` adjustment |
| Marlin | ✅ `M852` command | ✅ `M92` e-steps adjustment |
| RepRap Firmware | ✅ Supported | ✅ Supported |
| Bambu | ✅ Supported | ✅ Supported |
| Prusa firmware | ❌ No skew correction | ✅ Size only |

**Slicer compatibility for size correction:**

| Slicer | Size Correction Method |
|---|---|
| Orca Slicer | ✅ XY size compensation — easy |
| PrusaSlicer / SuperSlicer | ✅ XY size compensation |
| Bambu Studio | ⚠️ Limited |
| Cura | ⚠️ Limited |

---

## How to Use It

### Step 1 — Print the Califlower Model

- Print the Califlower STL at your **normal print settings** — do not change anything
- Use PLA or PETG for best dimensional stability
- Let the print cool fully before measuring — warm plastic is still slightly expanded

> ⚠️ Print with the settings you actually use day-to-day. The point is to measure your printer's real-world output, not an idealised condition.

### Step 2 — Measure

Use a **digital calliper** for all measurements — do not use a ruler. The Califlower is designed with specific measurement points. Enter each measurement into the web calculator at **[vector3d.co.uk](https://vector3d.co.uk)**.

The calculator takes you through the measurements step by step and validates each entry before moving on.

### Step 3 — Apply Corrections

The calculator outputs ready-to-use correction values. How you apply them depends on your firmware:

---

#### Klipper — Skew Correction

Add the `[skew_correction]` section to your `printer.cfg`:

```ini
[skew_correction]
```

Then from the Mainsail or Fluidd console, apply the values provided by the Califlower calculator:

```gcode
SET_SKEW XY=140.4,140.2,99.8   ; replace with your Califlower output values
SKEW_PROFILE SAVE=califlower
SAVE_CONFIG
```

To load the skew profile automatically on every print, add this to your `PRINT_START` macro:

```gcode
SKEW_PROFILE LOAD=califlower
```

And clear it at the end of the print in your `PRINT_END` macro:

```gcode
SET_SKEW CLEAR=1
```

> 💡 Always load the skew profile in `PRINT_START` and clear it in `PRINT_END`. Leaving skew active outside of prints can cause homing and mesh probing issues.

---

#### Klipper — Size / Scale Correction

If the Califlower identifies a consistent size error in X or Y, you can correct it by adjusting the `rotation_distance` in your stepper config. The calculator gives you a correction percentage — apply it like this:

```ini
# Example: if X is printing 0.5% too large, multiply current rotation_distance by 1.005
[stepper_x]
rotation_distance: 40.2   ; was 40.0 — adjusted by Califlower calculator output
```

Alternatively, apply size correction in **Orca Slicer** under:
**Printer Settings > Machine > XY Size Compensation**

This keeps the firmware clean and applies the correction per-slicer rather than globally.

---

#### Marlin — Skew Correction

Add to your start G-code or configuration:

```gcode
M852 I0.00128   ; replace with your Califlower output value
```

Save permanently with `M500`.

---

## How Often Should You Re-Run This?

| Event | Re-Calibrate? |
|---|---|
| Initial printer build or rebuild | ✅ Yes — always do this on a new build |
| After replacing belts | ✅ Yes |
| After frame disassembly or moving the printer | ✅ Yes |
| After changing XY joints or carriages | ✅ Yes |
| Routine maintenance (nozzle swap, bed surface etc.) | ❌ Not needed |
| Parts drifting out of tolerance over time | ✅ Yes — re-run annually or when you notice fit issues |

---

## Tips

- **Use a good calliper** — a cheap £5 calliper will give inaccurate results and defeat the purpose. A decent digital calliper (Mitutoyo or similar) is worth the investment.
- **Measure at room temperature** — let the print cool completely before measuring.
- **Don't over-correct** — if your skew result is very small (< 0.1°), the error may be within normal acceptable tolerance. Apply the correction anyway — it costs nothing and improves accuracy.
- **Print a verification model after correcting** — a 100mm XY square is a good quick check. Both diagonals should measure the same.
- **Skew fix before input shaping** — mechanical accuracy should be sorted before resonance calibration. Get the geometry right first.

---

*Back to [Troubleshooting Guides](../README.md#️-troubleshooting-guides) | [README](../README.md)*
