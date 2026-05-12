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
3. **Enable "avoid crossing perimeters"** in slicer
4. **Reduce fan** (cool air makes strings set mid-air)
5. **Tune pressure advance** precisely

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

- **Polymaker PolyLite PETG** — excellent consistency
- **Prusament PETG** — tight tolerances, great quality
- **Bambu Lab PETG HF** — optimised for high-speed printing
- **Hatchbox PETG** — reliable budget option
- **eSUN PETG** — widely available, solid quality

---

*← [Back to README](../README.md)*
