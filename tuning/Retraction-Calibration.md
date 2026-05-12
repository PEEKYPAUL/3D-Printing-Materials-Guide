# Retraction Calibration

> Dial in retraction distance and speed to eliminate stringing between features.

---

## Overview

Retraction pulls filament back into the nozzle during travel moves to prevent ooze from dragging strings across the print. Too little retraction = stringing. Too much = grinding, clogs, or gaps. The goal is the minimum retraction that eliminates strings.

---

## What You Need

- Orca Slicer (built-in retraction calibration)
- A well-tuned temperature (calibrate that first — a temperature that is too high will string regardless of retraction)

---

## Step 1 — Verify Temperature First

Stringing is often caused by printing too hot, not by incorrect retraction. Before tuning retraction, confirm your nozzle temperature is correct using the [Temperature Tower](Temperature-Tower.md) guide.

---

## Step 2 — Open the Calibration Tool

In Orca Slicer go to **Calibration > Retraction**.

![Orca Slicer calibration menu showing Retraction option](../images/retraction-01-menu.jpg)
*Calibration > Retraction in Orca Slicer.*

---

## Step 3 — Set Your Range

Use these starting ranges by extruder type and material:

| Setup | Distance Range | Speed |
|---|---|---|
| Direct drive — PLA/PETG | 0.5–2.0 mm | 25–45 mm/s |
| Direct drive — ABS/ASA | 0.5–2.0 mm | 25–45 mm/s |
| Direct drive — TPU | 0–0.5 mm | 20–25 mm/s |
| Bowden — PLA/PETG | 3.0–7.0 mm | 40–60 mm/s |
| Bowden — ABS/ASA | 3.0–7.0 mm | 40–60 mm/s |

Set step to 0.1 mm (direct drive) or 0.5 mm (Bowden).

![Retraction calibration settings in Orca Slicer](../images/retraction-02-settings.jpg)
*Set start, end, and step values appropriate for your extruder type.*

---

## Step 4 — Print and Read the Tower

The test prints a series of towers with travel moves between them. Each tower section uses a different retraction distance.

Look for:**The lowest distance value where strings disappear completely.**

| What You See | Meaning |
|---|---|
| Thick strings between towers | Retraction too low or temp too high |
| Fine hairs between towers | Slightly low — increase slightly |
| Clean gaps, no strings | Correct retraction |
| Gaps or holes in walls | Retraction too high — causing gaps |
| Grinding or clicking sounds | Way too high — reduce immediately |

![Printed retraction tower showing different string levels per zone](../images/retraction-03-printed.jpg)
*The retraction tower — zones with no stringing indicate the correct range.*

![Close-up comparing heavy stringing vs clean travel](../images/retraction-04-detail.jpg)
*Left: insufficient retraction. Right: correct retraction — clean travel gaps.*

---

## Step 5 — Apply Your Value

In Orca Slicer, go to **Filament Settings > Filament** and update:
- **Retraction length**
- **Retraction speed**

Save to your filament profile.

---

## Tips

- **Always tune temperature before retraction** — the correct temp reduces stringing more than retraction alone.
- **TPU and flexible materials**: use minimal or zero retraction — flexibles don't retract cleanly and clog easily.
- **PETG**: use lower retraction than PLA — PETG is stringy but overly aggressive retraction causes blobs.
- **Bowden setups**: high retraction distances are normal due to the gap between extruder and nozzle.
- Enable **Avoid crossing perimeters** in Orca Slicer to reduce travel moves across open air — this eliminates stringing opportunities entirely.

---

*Back to [Tuning Guides](../README.md#tuning-guides) | [README](../README.md)*