# Maximum Volumetric Flow Rate

> **Difficulty:** ⭐⭐⭐ Intermediate | **Firmware:** Klipper · Marlin · RepRapFirmware | **Do this after:** Extruder calibration and flow rate calibration

---

## What Is Volumetric Flow Rate?

Volumetric flow rate is how much plastic your hotend can melt and push through the nozzle per second, measured in **mm³/s**. It is the real limit on how fast you can print — not the motion speed of your axes, but the rate at which your hotend can keep up with that speed.

Push past your hotend's limit and you get under-extrusion, weak layer bonding, and inconsistent walls — even if the toolhead is moving at the speed you set.

Understanding and setting your volumetric limit in the slicer means you can freely change layer heights, nozzle sizes, line widths, and speeds without manually recalculating whether your hotend can keep up. The slicer handles it automatically.

---

## The Formula

```
Volumetric flow (mm³/s) = speed (mm/s) × layer height (mm) × line width (mm)
```

Rearranged to find max print speed from a known flow limit:

```
Max speed = volumetric flow ÷ layer height ÷ line width
```

**Example:** Hotend limit is 18 mm³/s, printing at 0.2mm layer height and 0.45mm line width:
```
Max speed = 18 ÷ 0.2 ÷ 0.45 = 200 mm/s
```

For 1.75mm filament, a useful shorthand: `mm³/s ≈ mm/s of filament × 2.4`

---

## Reference Flow Rates by Hotend

These are approximate values for a **0.4mm brass nozzle** at typical print temperatures. Hardened steel nozzles reduce flow by ~10–15% due to lower thermal conductivity. Larger nozzles increase flow significantly.

| Hotend | Approximate Max Flow |
|---|---|
| E3D V6 | ~11 mm³/s |
| Dragon SF | ~15 mm³/s |
| Dragon HF | ~22–24 mm³/s |
| Rapido HF | ~24 mm³/s |
| Rapido UHF | ~30 mm³/s |
| Mosquito Magnum | ~28–30 mm³/s |
| Bambu hotend | ~28–32 mm³/s |

> ⚠️ These numbers vary significantly with temperature, filament type, and nozzle condition. Always test your specific setup — don't rely solely on published figures.

---

## How to Find Your Limit

### Step 1 — Prepare

In `printer.cfg`:
```ini
[extruder]
max_extrude_only_distance: 200
```
Restart Klipper. Heat the hotend to your normal print temperature for the filament you're testing.

Extrude a small amount to prime the nozzle:
```gcode
M83
G1 E5 F60
```

---

### Step 2 — Mark 100mm of Filament

Mark the filament 100mm above the extruder entrance — the same technique as [Extruder Calibration](Extruder-Calibration.md).

---

### Step 3 — Test at Increasing Speeds

Extrude 100mm at progressively faster speeds. Each test uses the filament speed in mm/s — multiply by 60 for the F value (mm/min):

```gcode
M83
G1 E100 F300    ; 5 mm/s filament speed
```

| Target (mm/s) | F value | mm³/s (approx, 1.75mm) |
|---|---|---|
| 3 | F180 | ~7 |
| 5 | F300 | ~12 |
| 7 | F420 | ~17 |
| 9 | F540 | ~22 |
| 11 | F660 | ~26 |
| 13 | F780 | ~31 |

After each extrude, measure how much filament was actually consumed. When the measured amount starts dropping noticeably below 100mm — that's your hotend running out of melt capacity.

![Graph showing volumetric flow dropoff as speed increases past hotend limit](../images/max-flow-01-dropoff-graph.jpg)

*Flow drops progressively as you approach the hotend's limit. The point where measured extrusion starts falling below 100mm marks the edge of your reliable operating range.*

---

### Step 4 — Find the Drop-Off Point

The pattern you're looking for:

```
 5 mm/s → 99.8mm extruded  ✅ fine
 7 mm/s → 99.2mm extruded  ✅ fine
 9 mm/s → 97.1mm extruded  ⚠️ dropping
11 mm/s → 91.4mm extruded  ❌ significant under-extrusion
```

Your reliable limit sits just below where the drop-off starts — in this example, around 8 mm/s filament speed, or roughly 19 mm³/s.

> 💡 **Test at sustained length too.** Short 100mm tests can flatter a hotend that can't hold that rate continuously. Run a 300mm extrude at your target speed to confirm it can sustain the flow without degrading.

---

### Step 5 — Convert to mm³/s

```
volumetric flow = filament speed (mm/s) × 2.4   (for 1.75mm filament)
```

**Example:** limit found at 8 mm/s filament speed:
```
8 × 2.4 = 19.2 mm³/s
```

Take 10–15% off this as a practical working limit — real prints have pressure changes, direction changes, and cooling variations that the bench test doesn't replicate:
```
19.2 × 0.87 = ~16.7 mm³/s working limit
```

---

## Setting the Limit in Your Slicer

### Orca Slicer
**Printer Settings → Machine → Max volumetric speed** — set per printer profile.
You can also override per filament in **Filament Settings → Max volumetric speed** to set lower limits for high-resistance materials.

### PrusaSlicer / SuperSlicer
Set in **Filament Settings → Advanced → Max volumetric speed**.

> ⚠️ In PrusaSlicer, the setting in the Print profile's Auto Speed section only applies in specific circumstances. Set it in Filament Settings to make it apply universally.

### Cura
Cura doesn't have a native volumetric speed limit. Calculate your max speed manually for each layer height and line width combination:
```
max_speed = volumetric_limit ÷ layer_height ÷ line_width
```

---

## Temperature Matters

Higher temperatures increase flow capacity — sometimes significantly. If you're tuning for speed, test at your actual print temperature, not a conservative one. For high-speed functional prints where appearance is secondary, running 10–20°C hotter than normal can meaningfully raise your volumetric ceiling.

The flip side: running hotter increases ooze, stringing, and the chance of material degradation on extended prints. Find the balance for your use case.

---

## Common Problems

| Problem | Likely Cause | Fix |
|---|---|---|
| Extrusion drops immediately at any speed increase | Partial clog, or extruder not fully calibrated | Fix clog, re-run extruder calibration first |
| Wildly inconsistent measurements | Temperature fluctuating, wet filament | Check PID tune, dry filament thoroughly |
| Measured limit much lower than hotend spec | Hardened steel nozzle, or nozzle needs replacing | Expected — hardened steel reduces flow ~15% vs brass |
| Under-extrusion only on perimeters, not infill | Pressure advance needs tuning, not a flow limit issue | See Pressure Advance guide |

---

*Back to [Tuning Guides](../README.md#-tuning-guides) | [README](../README.md)*
