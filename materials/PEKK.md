# PEKK — Polyetherketoneketone

> **Difficulty:** ⭐⭐⭐⭐ Expert | **Category:** High-Temp PAEK | **HDT:** 160°C (amorphous) / 250°C+ (semi-crystalline) | **Notable:** Slightly more printable than PEEK with comparable performance

---

## Overview

PEKK (Polyetherketoneketone) is a high-performance engineering thermoplastic from the PAEK family — the same family as PEEK. It offers an exceptional combination of mechanical strength, chemical resistance, temperature resistance, and biocompatibility, and is widely used in aerospace, medical, and industrial applications.

The key difference from PEEK is PEKK's **lower and more controllable crystallisation rate**. PEEK crystallises rapidly during cooling, which demands precise chamber temperature control to prevent warping and delamination. PEKK crystallises more slowly, giving you two distinct ways to process it:

| Grade | Crystallinity | HDT | Printability | Best For |
|---|---|---|---|---|
| **PEKK-A (Amorphous)** | Low | ~160°C | Easier — prints more like a tough PC | General engineering parts, complex geometries |
| **PEKK-SC (Semi-Crystalline)** | High (via annealing) | 250°C+ | Harder — requires post-print annealing | High-temp structural, chemical resistance |

> 💡 Most desktop PEKK filaments target the amorphous processing route — you get a strong, chemically resistant part at a lower processing difficulty than PEEK. Semi-crystalline performance requires a controlled annealing cycle after printing.

---

## Settings Reference

| Parameter | Range | Notes |
|---|---|---|
| Nozzle Temp | 340–370°C | Lower than PEEK — start at 350°C and tune |
| Bed Temp | 120–160°C | 140°C is a good starting point |
| Chamber Temp | 120–140°C | Actively heated — mandatory |
| Print Speed | 15–25 mm/s | Print slowly for best interlayer bonding |
| Cooling | 0% | Absolutely no part cooling |
| Flow Ratio | 1.00 | Calibrate after temps are stable |
| Nozzle | Hardened steel / ruby | Brass will not survive |
| All-Metal Hotend | **Required** | High-temp rated to 400°C+ |

---

## Hardware Requirements

| Requirement | Needed? | Notes |
|---|---|---|
| All-metal hotend (400°C rated) | ✅ **Required** | Standard hotends are not suitable |
| Hardened steel or ruby nozzle | ✅ **Required** | Brass will be destroyed |
| Heated bed (160°C capable) | ✅ **Required** | |
| Actively heated enclosure | ✅ **Required** | 120°C+ chamber — no passive enclosures |
| High-temp bed surface | ✅ **Required** | See bed surfaces below |

Suitable printers:
- **Apium P220** — purpose-built for PAEK materials
- **AON3D AON-M2** — open-material high-temp system
- **Intamsys Funmat HT / Pro** — designed for PEEK/PEKK
- High-end custom industrial builds

---

## Bed Surfaces & Adhesion

PEKK requires adhesives rated for extreme temperatures — standard glue sticks and hairspray burn off well below PEKK's bed temperature.

| Surface | Adhesion | Notes |
|---|---|---|
| PEI-coated aluminium | ✅ Good | With Vision Miner Nano Polymer Adhesive |
| Bare aluminium (lightly blasted) | ✅ Good | A thin PEKK film builds up and acts as its own base |
| Kapton tape | ⚠️ OK | Can work at lower bed temps — monitor carefully |
| Glass | ❌ Poor | Not suitable without a specialist adhesive |

**Vision Miner Nano Polymer Adhesive** is the industry standard for PEKK and PEEK:
- Rated to **160°C bed temperature** — covers the full PEKK range
- Apply a very thin, even coat as the bed warms (50–80°C) and allow to fully flash off before printing
- Releases cleanly once the bed cools — do not force parts off a hot bed
- Works on PEI-coated aluminium and bare aluminium

---

## Material Properties

| Property | Amorphous PEKK | Semi-Crystalline PEKK |
|---|---|---|
| Tensile Strength | ~100 MPa | ~130 MPa |
| Young's Modulus | ~4.0 GPa | ~5.0 GPa |
| Heat Deflection Temp | ~160°C | 250°C+ (after annealing) |
| Chemical Resistance | Excellent | Outstanding |
| Biocompatibility | Yes (select grades) | Yes (select grades) |
| Flame Rating | Self-extinguishing | Self-extinguishing |
| UV Resistance | Good | Good |
| Moisture Absorption | Very low | Very low |

---

## PEKK vs PEEK — Key Differences

| Property | PEKK | PEEK |
|---|---|---|
| Print temperature | 340–370°C | 360–400°C |
| Crystallisation rate | Slow — more controllable | Fast — demands precise chamber control |
| Printability | Slightly easier | Harder |
| HDT (amorphous) | ~160°C | ~140°C |
| HDT (semi-crystalline) | 250°C+ (anneal required) | 250°C+ |
| Biocompatibility | Yes (select grades) | Yes (select grades) |
| Chemical resistance | Excellent | Exceptional |
| Cost | £150–£250/kg | £150–£200/kg |
| Availability | Limited | Limited |

---

## Annealing for Semi-Crystalline Performance

Printing PEKK in the amorphous state gives a strong, well-bonded part. To unlock full semi-crystalline performance (HDT 250°C+, higher stiffness and chemical resistance), the part must be annealed after printing:

1. Place the printed part in an oven or controlled furnace
2. Ramp temperature slowly to **200°C** at ~2°C/min to avoid thermal shock
3. Hold at 200°C for **1–2 hours**
4. Cool slowly back to room temperature — do not quench
5. Expect minor dimensional changes (~0.1–0.3%) — account for this in design if tolerances are tight

> ⚠️ Design parts for post-annealing if semi-crystalline properties are needed. Support structures, thin walls, and overhangs may be affected by the dimensional shift during annealing.

---

## Tips & Tricks

- **Pre-heat chamber for 45–60 minutes** before printing — do not rush this step.
- **Dry PEKK thoroughly** before printing — 120–150°C for 6+ hours in a convection oven. Moisture causes bubbling, poor layer bonding, and voids.
- **Print slow** — 15–25 mm/s is typical. PEKK does not respond well to speed.
- **Zero cooling fan** at all times — even a small amount of part cooling causes delamination.
- **First layer is critical** — a failed first layer on PEKK is very difficult to recover from. Take time to dial in your Z offset and bed adhesion on a small test before committing to a long print.
- **Avoid sharp internal corners** — stress concentrations in PEKK can cause cracking under load. Use fillets of at least 0.5–1 mm in structural parts.

---

## Common Problems

| Problem | Likely Cause | Fix |
|---|---|---|
| Delamination / layer cracking | Chamber too cold or part cooling on | Raise chamber to 120°C+, disable fan completely |
| Warping / lifting | Bed too cold or poor adhesion | Raise bed to 140–160°C, apply Vision Miner adhesive |
| Under-extrusion / poor flow | Temp too low or filament not dry | Raise nozzle temp 5°C, re-dry at 130°C for 6h |
| Bubbling / popping during print | Wet filament | Dry at 120–150°C for 6+ hours before printing |
| Poor first layer | Z offset or bed adhesion | Re-dial Z, ensure Vision Miner adhesive is applied correctly |
| Discolouration / burning | Nozzle too hot | Drop 5°C at a time |

---

## Applications

- **Aerospace** — structural brackets, ducting, cable management in high-temp environments
- **Medical** — implant-adjacent devices, sterilisable surgical tools, chemically inert labware
- **Oil & gas** — downhole components, valves, seals exposed to aggressive chemicals
- **Automotive** — under-hood structural parts, fluid system components
- **Industrial** — semiconductor manufacturing equipment, high-temp fixtures and jigs

---

## Recommended Brands

PEKK filament is a specialist product with very limited supplier options. Source from reputable engineering-grade suppliers only.

- **[Kimya PEKK-A](https://www.kimya.fr)** — amorphous grade, specifically formulated for FDM, from Arkema resin — one of the most accessible PEKK filaments for high-temp desktop printers
- **[Solvay KetaSpire PEKK](https://www.solvay.com)** — aerospace and medical grade resin made into filament; premium performance
- **[3DXTech PEKK](https://www.3dxtech.com)** — engineering-grade, desktop-printer compatible, consistently dimensioned

---

*← [Back to README](../README.md)*
