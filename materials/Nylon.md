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