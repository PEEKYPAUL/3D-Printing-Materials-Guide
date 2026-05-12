# 🟢 PLA — Polylactic Acid

> **Difficulty:** ⭐ Beginner | **Category:** Standard | **Biodegradable:** Yes (industrially)

---

## Overview

PLA is the most popular FDM filament and the best starting point for any printer. It's derived from renewable resources (corn starch, sugarcane) and prints reliably with minimal effort. It's not the strongest or most heat-resistant material, but for prototypes, display models, and low-stress parts it's hard to beat.

---

## Settings Reference

| Parameter | Typical Range | Notes |
|---|---|---|
| Nozzle Temp | 180–220°C | Start at 200°C; tune for brand |
| Bed Temp | 45–60°C | 0°C works on PEI/glass too |
| Print Speed | 40–80 mm/s | Can go faster with input shaping |
| Cooling Fan | 100% | High cooling = better bridges & overhangs |
| Retraction | 1–6 mm | Lower for direct drive, higher for Bowden |
| Layer Height | 0.1–0.3 mm | 0.2 mm is the sweet spot |
| Flow Ratio | 0.98 | Good starting point — tune per spool with flow calibration |

---

## Bed Surfaces

| Surface | Adhesion | Notes |
|---|---|---|
| PEI (textured) | ✅ Excellent | Best all-rounder — parts pop off when cool |
| PEI (smooth) | ✅ Excellent | Mirror finish on bottom layer |
| Glass (bare) | ✅ Good | Add glue stick if lifting |
| BuildTak | ✅ Good | Hard to remove sometimes |
| Blue tape | ⚠️ OK | Good for cold beds |

---

## Tips & Tricks

### Print Quality
- **Increase cooling** for better overhangs — PLA loves cold air. A part-cooling fan upgrade is one of the best mods for PLA quality.
- **Lower temp for less stringing** — drop 5°C at a time until you find the sweet spot.
- **Dry before printing** even for PLA — popping/crackling sounds and rough surfaces mean moisture. Dry at **45–50°C for 4–6 hours**.
- **Slow down for small details** — enable minimum layer time (e.g. 8–10 seconds) so each layer solidifies before the next.
- **Ironing** (top surface pass) gives a glass-smooth top layer — great for display models.

### Adhesion
- PEI is essentially perfect for PLA. If you're using a smooth PEI sheet, give it a **wipe with IPA** before every print.
- Struggling with lifting? Try **raising bed temp to 60°C** and adding a **brim** (5–8mm).
- **Don't use glue stick on PEI** for PLA — parts can be nearly impossible to remove.

### Post-Processing
- PLA sands easily with wet-and-dry paper — start at 200 grit, finish at 1000–2000.
- **Primer + spray paint** gives excellent results.
- **XTC-3D** or epoxy coatings create a smooth, glossy finish.
- PLA can be **acetone-smoothed slightly** but results are inconsistent — use ethyl acetate for better results.
- Avoid **high-temp environments**: PLA softens around 55–60°C. Don't leave prints in a car on a sunny day.

### Strength
- **Increase wall count** (3–4 perimeters) for functional parts over increasing infill.
- **0°/90° infill** (grid, gyroid) distributes load better than rectilinear for structural prints.
- Consider **PLA+** or **PLA-CF** variants for improved toughness and stiffness.

---

## Common Problems

| Problem | Likely Cause | Fix |
|---|---|---|
| Stringing | Temp too high, retraction too low | Lower temp 5°C, increase retraction |
| Warping/lifting | Bed too cold, draft | Raise bed temp, check for airflow drafts |
| Poor layer adhesion | Temp too low, speed too high | Raise nozzle temp 5°C, reduce speed |
| Clicking/grinding | Clog, too fast, too cold | Check for partial clog, reduce speed |
| Popping/bubbling | Wet filament | Dry at 45°C for 4–6 hrs |
| Elephant foot | First layer squished | Raise Z offset slightly |

---

## Variants

| Variant | Property Improvement | Trade-off |
|---|---|---|
| PLA+ | Toughness, less brittle | Slightly harder to tune |
| PLA-CF | Stiffness, surface finish | Abrasive — needs hardened nozzle |
| Silk PLA | Metallic sheen appearance | Weaker, stringier |
| High-Speed PLA | Prints at 100–300+ mm/s | Needs well-tuned fast printer |
| Matte PLA | Low-gloss, hides layer lines | Print slightly hotter |

---

## Recommended Brands

- **Bambu Lab PLA Basic/Matte** — consistent, reliable
- **Polymaker PolyLite / PolyMax PLA** — excellent quality
- **Prusament PLA** — high tolerance, great QC
- **Hatchbox PLA** — budget-friendly, widely available
- **eSUN PLA+** — great value for PLA+

---

*← [Back to README](../README.md)*
