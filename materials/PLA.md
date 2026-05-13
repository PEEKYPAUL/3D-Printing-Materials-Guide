# PLA — Polylactic Acid

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

## 📸 Common PLA Fails — Visual Examples

*Recognising what a failed print looks like helps you diagnose and fix problems faster.*

---

### 🌊 Warping / Bed Adhesion Failure

![3DBenchy detached from buildplate shortly after first layer](https://live.staticflickr.com/568/21731294668_4a4549a987.jpg)

*The print detached from the buildplate shortly after the first layer — a classic warping failure. Usually caused by a bed that's too cold, a dirty surface, or air drafts hitting the print. Fix: clean the bed with IPA, raise bed temp to 60°C, add a brim.*
*Photo: [#3DBenchy](https://www.flickr.com/photos/3dbenchy/21731294668) — CC BY 2.0*

---

### 🍝 Spaghetti / Catastrophic Print Detachment

![Catastrophic spaghetti print failure](https://upload.wikimedia.org/wikipedia/commons/4/48/Filament_fail_face.jpg)

*The print detached mid-print and the nozzle kept extruding into thin air, creating a chaotic mess of plastic — commonly called "spaghetti". Often caused by poor bed adhesion on the first layer, or the print being knocked off by the nozzle.*
*Photo: [Quinn Daedal](https://commons.wikimedia.org/wiki/File:Filament_fail_face.jpg) — CC BY-SA 4.0*

---

### ↔️ Layer Shifting

![Layer shifting caused by input shaping / belt issue](https://upload.wikimedia.org/wikipedia/commons/d/d2/Stampa_3d_scostamento_strati.jpg)

*Layers shifting horizontally mid-print. The upper layers are offset from the lower ones. Caused by loose belts, a stepper motor skipping steps, or incorrect input shaping settings in Klipper. Fix: check belt tension, reduce acceleration, re-run input shaper calibration.*
*Photo: [A7N8X](https://commons.wikimedia.org/wiki/File:Stampa_3d_scostamento_strati.jpg) — CC BY-SA 4.0*

---

### 📏 Poor Layer Quality / Layers Too Thick

![3DBenchy printed with excessively thick layers](https://live.staticflickr.com/390/20146074666_90fd41d274_n.jpg)

*Excessively thick layers result in very visible layer lines, rough surface finish, and a loss of fine detail. Keep layer height between 25–75% of your nozzle diameter — 0.2 mm on a 0.4 mm nozzle is the standard sweet spot.*
*Photo: [#3DBenchy](https://www.flickr.com/photos/3dbenchy/20146074666) — CC BY 2.0*

---

### 🫧 Infill Bleed-Through / Surface Artefacts

![Infill artefacts pushing through the outer shell](https://upload.wikimedia.org/wikipedia/commons/5/56/-3DBenchy_Cura_Infill_Artefacts_%2818857670356%29.jpg)

*The internal infill structure pushes through the outer perimeter walls, creating visible bumps and surface artefacts. Fix: reduce infill percentage, increase wall count (3–4 perimeters), or switch to a less aggressive infill pattern.*
*Photo: [#3DBenchy](https://commons.wikimedia.org/wiki/File:-3DBenchy_Cura_Infill_Artefacts_(18857670356).jpg) — CC BY 2.0*

---

### 🐘 Elephant Foot

*📷 Community photo wanted — drop yours in `images/pla-fails/` and open a PR!*

The first layer spreads out wider than the rest of the print, creating a flared "foot" at the base. Caused by the Z offset being too low (nozzle too close to the bed) or bed temperature being too high. Fix: raise your Z offset slightly and reduce bed temp by 5°C.

---

### 🕸️ Stringing

*📷 Community photo wanted — drop yours in `images/pla-fails/` and open a PR!*

Fine wispy threads of plastic left between parts of the print during travel moves. Caused by filament oozing out of the nozzle when it shouldn't be. Fix: lower nozzle temp by 5°C, increase retraction distance, and raise travel speed. See the [Stringing Guide](../troubleshooting/Stringing.md) for a full walkthrough.

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
