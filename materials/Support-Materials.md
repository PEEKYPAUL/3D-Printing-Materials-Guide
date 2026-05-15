# Support Materials - PVA & HIPS

> **Difficulty:** Intermediate | **Category:** Support | **Use Case:** Dual-extrusion soluble supports

---

## Overview

Support materials are used alongside primary filaments in dual-extrusion printers to create supports that dissolve or separate cleanly, leaving no marks on the model. The two most common are **PVA** (water-soluble, pairs with PLA) and **HIPS** (limonene-soluble, pairs with ABS).

---

# PVA - Polyvinyl Alcohol

> Water-soluble | Pairs with: PLA | Difficulty: Intermediate

## Overview

PVA dissolves completely in water, making it ideal for complex overhangs and internal cavities that would be impossible to remove manually. It is extremely hygroscopic and must be kept rigorously dry.

## Settings Reference

| Parameter | Range | Notes |
|---|---|---|
| Nozzle Temp | 180–210°C | 190–200°C is the sweet spot |
| Bed Temp | 45–60°C | Match your PLA bed temp |
| Print Speed | 25-40 mm/s | Print slower than your primary material |
| Cooling | 50-100% | Good cooling improves bridging |
| Storage | Sealed + desiccant | Degrades within hours if exposed |
| Flow Ratio | 0.95 | PVA over-extrudes easily — keeps interfaces clean |

## Tips & Tricks

### Moisture - The #1 Issue with PVA
- PVA absorbs moisture faster than almost any other filament. Even a few hours of exposure causes problems.
- **Always store in a sealed airtight container with fresh desiccant.**
- Print directly from a dry box with active drying.
- Dry at **45–50°C for 6-8 hours** before use. Do not exceed 60°C or PVA degrades.
- Signs of wet PVA: bubbling, popping sounds, rough surface, failed bonding to primary material.

### Printing Tips
- Use a **purge tower** in your slicer to ensure clean transitions between PVA and PLA.
- Keep the PVA nozzle at temperature even when idle - but minimise idle time.
- **Interface layers only** mode (support interface = PVA, body = PLA) saves material and reduces print time.
- PVA bonds best to PLA. It will not bond well to PETG, ABS, or most other materials.

### Dissolving Supports
- Submerge in **warm water (25–35°C)** - do not use hot water, it can warp PLA.
- Agitation (ultrasonic cleaner or gentle swirling) speeds up dissolution significantly.
- Full dissolution takes 30 minutes to several hours depending on thickness.
- Rinse the model thoroughly after dissolving.

---

# HIPS - High Impact Polystyrene

> Dissolves in limonene | Pairs with: ABS | Difficulty: Intermediate

## Overview

HIPS is a support material that dissolves in d-limonene (a citrus-based solvent). It shares nearly identical print settings with ABS, making it the natural support partner for ABS printing. It can also be printed as a standalone structural material.

## Settings Reference

| Parameter | Range | Notes |
|---|---|---|
| Nozzle Temp | 230–250°C | Match to your ABS temp |
| Bed Temp | 100–110°C | Same as ABS |
| Cooling | 0-10% | Minimal, same as ABS |
| Enclosure | Required | Same warping tendencies as ABS |
| Flow Ratio | 1.00 | Standard starting point |
| Bed Surface | PEI or hairspray on glass | |

## Tips & Tricks

### Printing with ABS
- HIPS and ABS have near-identical thermal behaviour, which is why they pair so well.
- Use a **purge tower** to avoid colour contamination between materials.
- Both materials need an enclosure - the enclosure you already use for ABS works perfectly.

### Dissolving with Limonene
- Submerge the print in **d-limonene** - available from specialist suppliers or online.
- Dissolution takes **12-24 hours** at room temperature; agitation or mild heating (30°C) speeds it up.
- Rinse with isopropyl alcohol after dissolving, then water.
- Limonene is **flammable** - keep away from heat sources and store safely.
- Reuse limonene until it becomes saturated.

### HIPS as a Standalone Material
- HIPS is lightweight, easy to sand, and accepts paint well.
- Good for display models, cosplay props, and lightweight structural parts.
- Similar impact resistance to ABS but slightly more brittle.

---

## PVA vs HIPS: Quick Comparison

| Property | PVA | HIPS |
|---|---|---|
| Solvent | Water | D-limonene |
| Primary Partner | PLA | ABS |
| Hygroscopic | Extremely | Low |
| Dissolution Speed | Fast (30 min - 2 hr) | Slow (12-24 hr) |
| Solvent Safety | Safe | Flammable, odorous |
| Cost | Higher | Lower |

---

## Recommended Brands

**PVA:**
- **[Polymaker PolyDissolve S1](https://www.polymaker.com)** — PLA-compatible, top recommendation, dissolves cleanly
- **[eSUN PVA+](https://www.esun3d.com)** — good budget option, widely available
- **[FormFutura Helios Support](https://www.formfutura.com)** — mid-tier PVA, reliable dissolution

**HIPS:**
- **[eSUN HIPS](https://www.esun3d.com)** — widely available, good quality, great value
- **[Polymaker PolyLite HIPS](https://www.polymaker.com)** — consistent and reliable
- **[Fillamentum HIPS](https://fillamentum.com)** — premium European option, excellent surface finish

---

*Back to [README](../README.md)*