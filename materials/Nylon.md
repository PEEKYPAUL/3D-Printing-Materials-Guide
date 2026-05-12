# Nylon (PA) - Polyamide

> **Difficulty:** Advanced | **Category:** Engineering | **HDT:** ~120C | **Notable:** Chemical resistant, tough, self-lubricating

---

## Overview

Nylon is one of the toughest FDM materials available - it's impact resistant, fatigue resistant, and self-lubricating (great for gears, bearings, hinges). The catch: it is **extremely hygroscopic** - it absorbs moisture from the air within hours, which causes catastrophic print failures.

Common variants: **PA6** (general), **PA12** (less moisture-sensitive), **PA6-CF/GF** (reinforced).

---

## Settings Reference

| Parameter | Range | Notes |
|---|---|---|
| Nozzle Temp | 240-270C | PA6: 255-270C; PA12: 240-260C |
| Bed Temp | 70-85C | Garolite/G10 preferred |
| Enclosure | Recommended | Reduces warping |
| Cooling | 20-40% | Some cooling helps bridging |
| Bed Surface | Garolite (G10) | Best adhesion by far |
| Flow Ratio | 1.00 | Nylon can vary — dry thoroughly before calibrating |

---

## Tips & Tricks

### Moisture - Critical
- **Nylon must be bone dry.** Print directly from a **dryer box** - don't trust even sealed spools.
- Dry at **70-80C for 8-12 hours** before printing.
- Wet nylon symptoms: foamy surface, bubbling, drastically reduced strength.
- Use a **filament dryer with humidity display** - target below 15% RH in the box.

### Bed Adhesives
Choosing the right adhesive makes the difference between nylon sticking reliably and prints popping off mid-print or fusing permanently to the bed.

**PA Glue (Polyamide-Specific Glue)**
Dedicated PA glues (such as Polymaker PA Glue and Bambu Liquid Glue for PA) are purpose-formulated for Nylon and are one of the best options when printing on PEI:
- Apply a **thin, even coat** to the warm bed (50-60C) and allow the solvent to fully flash off before printing.
- Gives a strong grip during the print with a **clean release when the bed cools** — no tearing or stuck prints.
- Works on smooth PEI, textured PEI, and glass surfaces.
- Reapply every 2-3 prints or when adhesion starts dropping.

**Vision Miner Nano Polymer Adhesive**
For higher-temp Nylon variants (PA6-CF, PA6-GF) printing above 260C or where PA glue isn't giving consistent results:
- Apply a **very thin coat** to the heated bed, let the solvent fully evaporate before the print starts.
- Rated for bed temps up to 160C — handles the full range of Nylon bed temperatures.
- Provides excellent adhesion with a clean peel release once cooled.
- One bottle goes a long way — a little applied thinly is more effective than a thick layer.

**PVA Glue Stick**
The simplest option — a standard Pritt stick or equivalent on a PEI bed:
- Reliable for plain PA6/PA12 at standard temps.
- Breaks down at higher temps (above ~100C bed) so not suitable for high-temp Nylon variants.
- Easy to apply and wash off with water.

**Garolite / G10 Sheet (No Adhesive Needed)**
The gold standard for Nylon — no adhesive required, mechanical adhesion to the surface texture:
- Best all-round option if you print Nylon regularly.
- Parts release cleanly when the bed cools.

### Bed Adhesion
- **Garolite / G10 sheet** at 70-80C is the gold standard for nylon adhesion.
- PEI with **PVA glue stick** works reasonably well.
- **Avoid glass** - nylon often won't stick or sticks permanently.

### Warping
- Enclose the printer.
- Use a brim (10+ mm).
- Slow down first layers significantly.

### Applications
- Functional gears, hinges, living hinges
- Wear-resistant parts
- Chemical-resistant enclosures
- Snap-fit mechanisms

---

## Common Problems

| Problem | Fix |
|---|---|
| Foamy/rough surface | **Dry the filament** - this is almost always moisture |
| Warping | Enclosure, garolite bed, brim |
| Poor bed adhesion | Switch to garolite, PVA glue, higher bed temp |
| Weak parts | Under-extruding or cold - raise temp, check flow |

---

## Recommended Brands
- **Taulman Bridge Nylon** - widely used, forgiving
- **Polymaker PolyMide PA12-CF** - excellent CF-reinforced option
- **Bambu PA12-CF** - optimised for their system, excellent results

---

*Back to [README](../README.md)*