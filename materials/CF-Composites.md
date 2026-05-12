# ⚫ Carbon Fibre & Composite Filaments

> **Difficulty:** ⭐⭐⭐ Advanced | **Category:** Composite | **Key Requirement:** Hardened nozzle

---

## Overview

Carbon fibre (CF) composite filaments combine a base polymer (PLA, PETG, Nylon, PEEK, etc.) with **chopped carbon fibre strands** — typically 10–20% by weight. The result is dramatically increased stiffness and improved surface finish, at the cost of reduced impact resistance and mandatory hardened nozzle use.

CF filaments don't make parts as strong as continuous carbon fibre composites — they improve **stiffness (Young's modulus)** significantly, but can be more brittle than the base material.

---

## Common CF Composite Families

| Base Material | Stiffness Gain | Heat Resistance | Difficulty | Notes |
|---|---|---|---|---|
| PLA-CF | High | Low (PLA base) | Easy | Great for display/rigid parts |
| PETG-CF | High | Moderate | Intermediate | Good all-rounder |
| ABS-CF | High | Moderate | Intermediate | Needs enclosure |
| PA-CF (Nylon-CF) | Very high | Good (~130°C) | Advanced | Best functional CF option |
| PC-CF | Very high | High (~140°C) | Advanced | High-temp engineering |
| PEEK-CF | Extreme | Very high (250°C+) | Expert | Aerospace-grade |

---

## Nozzle Requirements — Critical

> ⚠️ **NEVER print CF filaments with a standard brass nozzle.** CF is highly abrasive and will wear a brass nozzle to the point of under-extrusion within 200–500g of filament.

### Nozzle Options (Recommended to Less Recommended)
1. **Hardened steel** — good balance of durability and thermal conductivity. Best everyday choice.
2. **Tungsten carbide** — longest life, but expensive and can affect print quality.
3. **Ruby-tipped** — extremely durable tip, brass body retains conductivity. Premium option.
4. **Nickel-plated brass** — some wear resistance; a budget compromise.

### Nozzle Sizing
- CF filaments benefit from **0.4mm or larger** nozzles — fibres can partially block smaller orifices.
- **0.6mm is often the sweet spot** for CF: faster prints, better flow, fewer clog risks.
- Avoid 0.2–0.25mm nozzles with CF filament.

---

## Settings Reference

Settings vary by base material — use the base material guide as your starting point, then adjust:

| Parameter | Adjustment from Base |
|---|---|
| Nozzle Temp | +5–10°C (CF requires slightly more energy to flow) |
| Print Speed | -10–20% (CF is less forgiving) |
| Retraction | Reduce slightly (CF can be brittle mid-strand) |
| Cooling | Match base material |
| Flow Ratio | 1.02–1.05 | CF restricts flow slightly — start at 1.02 and increase if under-extruding |

---

## Tips & Tricks

### Surface Finish
- CF composites have a **distinctive matte, textured surface** that hides layer lines naturally.
- This makes them popular for **cosmetic parts** where a professional, technical look is desired.
- The surface is rough — not ideal for applications needing sliding fits.

### Structural Considerations
- CF composites are **stiffer but more brittle** than base polymers.
- Don't use them where impact resistance is the priority — use regular Nylon or PC instead.
- Excellent for **brackets, structural frames, stiff levers, jigs and fixtures**.
- **Orientation matters** — layer lines are still the weak axis. Design parts so loads are perpendicular to layer lines where possible.

### Moisture (CF-Nylon critical)
- CF-Nylon is just as hygroscopic as plain Nylon — **dry it equally aggressively**.
- CF-PLA and CF-PETG are less sensitive but still benefit from drying.

### Dust and Safety
- CF composite filaments generate **fine carbon dust** during printing. This is a respiratory irritant.
- Ensure your printer is **enclosed** and consider a HEPA filter on the exhaust.
- Don't sand CF parts without a dust mask — the particles are very fine.

---

## Continuous Carbon Fibre (Different Technology)

**Markforged** and similar systems print **continuous carbon fibre strands** embedded in a Nylon matrix — this is fundamentally different and produces parts approaching aluminium strength. This guide covers chopped-CF composites only.

---

## Popular CF Composite Products

| Product | Base | Notable Feature |
|---|---|---|
| Bambu PA12-CF | PA12 | Excellent for Bambu AMS |
| Polymaker PolyMide PA6-CF | PA6 | High stiffness, affordable |
| 3DXTech CarbonX PEEK-CF | PEEK | Aerospace-grade |
| Prusament PLA-CF | PLA | Easy-to-print, great finish |
| Fiberlogy PETG CF15 | PETG | Good value |

---

*← [Back to README](../README.md)*
