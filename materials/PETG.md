# PETG — Polyethylene Terephthalate Glycol

> **Difficulty:** ⭐⭐ Intermediate | **Category:** Standard/Engineering | **Chemical Resistance:** Good

---

## Overview

PETG bridges the gap between easy-to-print PLA and demanding engineering materials. It offers excellent layer adhesion, good chemical resistance, slight flexibility (impact resistant), and a higher heat deflection temperature (~80°C) than PLA. It's one of the best all-round materials for functional parts.

The "G" (glycol-modified) makes it less brittle and clearer than standard PET. It's the material used for most plastic bottles.

---

## Settings Reference

| Parameter | Typical Range | Notes |
|---|---|---|
| Nozzle Temp | 230–250°C | Start at 240°C |
| Bed Temp | 70–85°C | 80°C is a reliable starting point |
| Print Speed | 30–60 mm/s | Slower than PLA — don't rush it |
| Cooling Fan | 20–50% | Too much cooling = delamination |
| Retraction | 1–5 mm | Tricky — PETG is stringy |
| Layer Height | 0.15–0.3 mm | 0.2 mm works well |
| Flow Ratio | 0.95 | PETG over-extrudes easily — start here and tune up if needed |

---

## Bed Surfaces

| Surface | Adhesion | Notes |
|---|---|---|
| PEI (textured) | ✅ Excellent | **Clean with IPA only** — PETG bonds aggressively |
| PEI (smooth) | ⚠️ Too good | Risk of sheet damage — use release agent |
| Glass + glue stick | ✅ Good | Easy release when cool |
| BuildTak | ⚠️ Aggressive | Can pull up the surface |

> ⚠️ **Warning:** PETG can bond *permanently* to smooth PEI and some build surfaces. Always use a **thin layer of glue stick or hairspray as a release agent** on smooth surfaces.

---

## Tips & Tricks

### Print Quality
- **Reduce cooling fan** significantly compared to PLA — PETG needs warmer air to bond layers properly. Too much cooling causes delamination.
- **Slow down** — PETG is prone to stringing and blobs at speed. 40–50 mm/s is a sweet spot.
- **Tune retraction carefully** — PETG strings easily but too much retraction causes grinding and clogs. Start low and increase gradually.
- **First layer slightly higher** than PLA — PETG should be "kissed" onto the bed, not squished. Excessive squish causes the notorious "PETG stuck to bed" problem.
- Print in an **enclosure or draught-free area** for consistent results.

### Adhesion
- PETG adheres *extremely* well — the challenge is usually **getting prints off** rather than keeping them on.
- **Glue stick on PEI** = easy release while still adhesion. This is the recommended approach for smooth PEI.
- Wait for the bed to **cool to room temperature** before removing — PETG releases cleanly when cold.
- If stuck: **gentle flex** of flexible plates, or place in a freezer for 10 minutes.

### Stringing
PETG is notoriously stringy. Attack it from multiple angles:
1. **Raise temp slightly** (counterintuitive but helps with flow consistency)
2. **Increase travel speed**
3. **Enable "avoid crossing perimeters"** in slicer — keeps travel moves inside the model so strings are hidden
4. **Reduce fan** (cool air makes strings set mid-air)
5. **Tune pressure advance** precisely
6. **Enable Coasting** in your slicer — cuts extrusion slightly before the end of each move to reduce nozzle pressure and prevent ooze
7. **Enable "Extra Restart Distance"** — compensates for pressure drop at the start of a move, reducing blobs at segment start points

### Moisture
- PETG is moderately hygroscopic. Dry at **65–70°C for 4–6 hours**.
- Signs of wet PETG: excessive stringing, bubbling, rough surface texture, reduced strength.

---

## Common Problems

| Problem | Likely Cause | Fix |
|---|---|---|
| Excessive stringing | Temp too high, retraction off | Tune retraction, check travel speed |
| Delamination | Too much cooling | Reduce fan to 30–40% |
| Stuck to bed | First layer too squished, surface type | Raise Z offset, use glue stick |
| Blobs/zits | Pressure/retraction | Tune pressure advance |
| Wet filament | Moisture | Dry at 65–70°C |
| Poor bed adhesion | Bed too cold, contaminated | Clean with IPA, raise bed temp |

---

## 📊 Strength Statistics

Approximate mechanical properties for printed parts — values vary by brand and print settings. Use as a guide for material selection, not engineering calculations.

| Property | Standard PETG | PETG-CF | PETG-GF |
|---|---|---|---|
| Tensile Strength | 50 MPa | 60 MPa (+20%) | 62 MPa (+24%) |
| Young's Modulus (Stiffness) | 2.1 GPa | 5.5 GPa (+162%) | 3.5 GPa (+67%) |
| Heat Deflection Temp | 72°C | 82°C | 79°C |

> 📖 See the full [CF & GF Composites Guide](CF-Composites.md) for a cross-material strength comparison and details on printing fibre-reinforced variants.

---

## Variants

| Variant | Notes |
|---|---|
| PETG-CF | Carbon fibre reinforced — stiffer, matte, abrasive |
| PETG-GF | Glass fibre — good strength/temp resistance |
| PETG Clear | High clarity — great for light guides, containers |

---

## When to Choose PETG Over PLA

- Parts exposed to **moisture or outdoors** (PETG won't degrade like PLA)
- Functional parts needing **slight flex and impact resistance**
- Parts near **mild heat** (e.g. inside a PC case, outdoor summer)
- **Food-contact** parts (check brand certification — not all PETG is food-safe)
- **Chemical resistance** required (mild acids, some solvents)

---

## Recommended Brands

- **Polymaker PolyLite PETG** — excellent consistency, great all-rounder
- **Prusament PETG** — tight tolerances, great quality
- **Formatura PETG** — reliable mid-tier, good layer adhesion
- **Sunlu PETG** — solid budget option, wide colour range
- **eSUN PETG** — widely available, consistent quality

---

## Applications

| Use Case | Why PETG Works |
|---|---|
| Waterproof containers & planters | Water and chemical resistant, no degradation |
| Snap-fit parts | Good flex and impact resistance without breaking |
| Outdoor parts | More UV and moisture resistant than PLA |
| Water bottles & food containers | Check brand for food-safe certification |
| PC cases & electronics enclosures | Good temp resistance, slightly flexible |
| Mechanical parts needing fatigue resistance | Handles repeated flex without cracking |

---

*← [Back to README](../README.md)*
