# Extruder Calibration

> **Difficulty:** ⭐⭐ Beginner | **Firmware:** Klipper · Marlin · RepRapFirmware | **Do this before:** Flow rate, pressure advance, or any extrusion-based tuning

---

## What This Actually Does

Extruder calibration makes sure that when Klipper asks for 100mm of filament, the extruder actually delivers 100mm. It sounds basic — but if this is off, every other tuning step built on top of it (flow rate, pressure advance, volumetric limits) is working with a skewed baseline.

This is separate from flow ratio / extrusion multiplier. Extruder calibration is a mechanical correction — it accounts for your motor's actual step count, gear ratio, and drive gear diameter. Flow ratio is a print-time fine-tune on top of that. Get extruder calibration right first.

---

## Hot or Cold Testing?

| Setup | Method | Why |
|---|---|---|
| Direct drive | **Hot** — print temp | Avoids disassembly. The small amount of ooze during testing is acceptable |
| Bowden | **Cold** — disconnect tube | Far easier to measure free filament without fighting the tube |

---

## Step 1 — Prep Your Config

### Klipper

In `printer.cfg`, temporarily allow long cold extrudes and raise the extrude distance limit:

```ini
[extruder]
max_extrude_only_distance: 101   ; raise from default 50mm
```

For cold testing only, also add:
```ini
min_extrude_temp: 0
```

Then `RESTART`.

### Marlin
Cold extrusion is enabled with:
```gcode
M302 P1
```

---

## Step 2 — Mark Your Filament

![Marking filament at 120mm for extruder calibration](../images/extruder-cal-01-marking.jpg)

1. Heat the hotend to print temperature (or enable cold extrude as above)
2. Extrude a small amount to make sure the motor is energised:
   ```gcode
   M83          ; relative extrusion
   G1 E5 F60   ; extrude 5mm slowly
   ```
3. Hold a ruler against the filament going into the extruder
4. Make a clear mark on the filament at exactly **120mm** from the extruder entrance

---

## Step 3 — Extrude 100mm

Run this exactly — **1mm/s is important**. Faster speeds introduce motor slip and momentum errors that make the measurement unreliable:

```gcode
M83
G1 E100 F60   ; extrude 100mm at 1mm/s (60mm/min)
```

Watch the filament during the test. On a direct drive hot test, watch for any skipping or irregular movement — that indicates a different problem (clog, tension issue) and the measurement won't be meaningful until fixed.

---

## Step 4 — Measure What Was Actually Extruded

![Measuring remaining filament distance after extrusion](../images/extruder-cal-02-measuring.jpg)

After the extrude command finishes:

1. Measure the distance from your original 120mm mark to the extruder entrance
2. Subtract that from 120mm — the result is how much filament was actually moved

**Example:**
- Mark was at 120mm
- After extrusion, mark is now 22mm from the extruder
- Actual extrusion = 120 − 22 = **98mm**

---

## Step 5 — Calculate the Correction

### Klipper — rotation_distance

```
new_rotation_distance = old_rotation_distance × (actual / 100)
```

**Example:** old value is 22.6, actual extrusion was 98mm:
```
new_rotation_distance = 22.6 × (98 / 100) = 22.148
```

Apply temporarily to test before saving:
```gcode
SET_EXTRUDER_ROTATION_DISTANCE EXTRUDER=extruder DISTANCE=22.148
```

Once confirmed, update `printer.cfg` and `RESTART`.

### Marlin / RepRapFirmware — E-steps

```
new_e_steps = current_e_steps × (100 / actual)
```

**Example:** current is 415 steps/mm, actual was 98mm:
```
new_e_steps = 415 × (100 / 98) = 423.5
```

Apply and test:
```gcode
M92 E423.5
```

Save permanently:
```gcode
M500   ; Marlin — saves to EEPROM
```
For RepRapFirmware, edit the `M92` line in `config.g` and reboot.

---

## Step 6 — Verify

Repeat the full measurement with your new values. You're aiming for the mark to end up at exactly 20mm from the extruder entrance (120 − 100 = 20mm remaining).

If two back-to-back tests give different results — inconsistent extrusion is the problem, not the calibration value. Check for:

- Partial clog or heat creep
- Loose extruder drive gear grub screw
- Filament grinding against the housing
- Bowden coupler slipping

Fix the mechanical issue first, then re-calibrate.

---

## After Calibrating

- Restore `min_extrude_temp` to its original value if you changed it
- Remove the `max_extrude_only_distance: 101` line (or restore the original value)
- `RESTART` Klipper to apply

Now move on to [Flow Rate Calibration](Flow-Rate-Calibration.md) — that's the fine-tune on top of this mechanical correction.

---

## Common Problems

| Problem | Likely Cause |
|---|---|
| Measured value jumps between tests | Extruder skipping, grinding, or partial clog |
| Value needs correcting by more than 5% | Something mechanical is wrong — check gear ratio, grub screws, and drive gear diameter |
| Filament slips during cold test | Cold extrusion too stiff — either test hot or reduce your grip/tension if using a BMG-style extruder |
| Klipper won't extrude cold | `min_extrude_temp` not set to 0, or `RESTART` not run after change |

---

*Back to [Tuning Guides](../README.md#-tuning-guides) | [README](../README.md)*
