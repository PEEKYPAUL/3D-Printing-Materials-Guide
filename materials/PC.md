# PC - Polycarbonate

> **Difficulty:** Advanced | **Category:** High-Temp | **HDT:** ~130-140C | **Notable:** Optically clear, extremely tough

---

## Overview

Polycarbonate is one of the toughest thermoplastics available - it's used in bulletproof glass, safety helmets, and aerospace components. It prints at high temperatures, needs an enclosure, and absolutely requires an **all-metal hotend**. When printed correctly, it offers exceptional strength and heat resistance.

---

## Settings Reference

| Parameter | Range | Notes |
|---|---|---|
| Nozzle Temp | 260-310C | Pure PC: 290-310C; PC blends: 260-280C |
| Bed Temp | 110-120C | |
| Enclosure | **Required** | Chamber temp 50-60C ideal |
| All-Metal Hotend | **Required** | PTFE will off-gas and deform |
| Cooling | 0-20% | Very little cooling |
| Bed Surface | PEI or PC sheet | |
| Flow Ratio | 1.00 | Calibrate once filament is fully dry |

---

## Tips & Tricks

### Hardware Requirements
- **All-metal hotend** - mandatory. No PTFE above the heatbreak.
- High-temp bed: must reliably reach 115C+.
- Enclosed chamber. A **heated chamber** (50C+) dramatically reduces warping.
- **Hardened steel or ruby nozzle** recommended - PC is slightly abrasive.

### Moisture
- PC is hygroscopic. Dry at **80C for 6-8 hours**. Print from a dry box.

### Warping
- PC warps aggressively. Mitigations:
  - Maximum enclosure temperature
  - Large brim (15mm+)
  - Draft shield
  - Slow first layers
  - PC-specific adhesives (PC glue sticks, Magigoo PC)

### Blends vs Pure PC
- **PC/ABS blends** print at lower temps (~260-270C) and warp less - good starting point.
- **Pure PC** is harder to print but stronger and more heat-resistant.

### Applications
- High-temp functional parts
- Impact-resistant enclosures
- Electrical components needing UL-94 compliance (check brand)
- Optical clarity applications

---

## Common Problems

| Problem | Fix |
|---|---|
| Warping | Max enclosure temp, large brim, draft shield, PC adhesive |
| Layer delamination | Raise nozzle temp, reduce cooling, enclose |
| Poor bed adhesion | Use PC glue stick or Magigoo PC |
| Stringing | Tune retraction, ensure filament is dry |

---

## Recommended Brands
- **Polymaker PolyMax PC** - excellent printability, tough
- **Prusament PC Blend** - reliable, well-documented settings
- **Fiberlogy PC** - good quality
- **Bambu PC** - tuned for their system

---

*Back to [README](../README.md)*