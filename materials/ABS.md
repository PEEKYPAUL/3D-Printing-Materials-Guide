# 🟡 ABS — Acrylonitrile Butadiene Styrene

> **Difficulty:** ⭐⭐ Intermediate | **Category:** Engineering | **Heat Resistance:** ~100°C HDT

---

## Overview

ABS was the dominant FDM material before PLA took over, and for good reason — it's tough, impact resistant, machinable, and acetone-smoothable. Its main downsides are warping, fumes (ventilate!), and the need for an enclosure. It remains widely used in industry for functional parts.

---

## Settings Reference

| Parameter | Typical Range | Notes |
|---|---|---|
| Nozzle Temp | 230–250°C | 240°C is a common sweet spot |
| Bed Temp | 100–110°C | 105°C recommended |
| Print Speed | 40–60 mm/s | |
| Cooling Fan | 0–20% | **Minimal or zero** — prevents warping/cracking |
| Enclosure | **Required** | Open-frame printers will warp |
| Retraction | 4–7 mm (Bowden), 1–3 mm (direct) | |
| Flow Ratio | 1.00 | Good starting point; calibrate per brand |

---

## Bed Surfaces

| Surface | Notes |
|---|---|
| PEI (textured) | Excellent — releases when cool |
| ABS slurry | Classic method — ABS dissolved in acetone, brushed on glass |
| Garolite / G10 | Excellent adhesion for ABS |
| Hairspray on glass | Reliable budget method |

---

## Tips & Tricks

### Warping — The #1 ABS Challenge
- **Enclosure is mandatory** — even a cardboard box over the printer helps. A 45–50°C chamber temp is ideal.
- **No cooling fan** — ambient airflow causes thermal stress and layer separation.
- **Large brims** (10–15mm) help anchor the print.
- **ABS slurry** (dissolved ABS in acetone) on glass is the old-school reliable method.
- Print **slower for the first 5–10 layers**.
- **Draft shield** in slicer adds a sacrificial wall that stabilises temperature around the print.

### Fumes
- ABS releases **styrene** during printing — a known irritant and potential carcinogen.
- **Always ventilate** — print in a room with good airflow or use an enclosure with a HEPA + activated carbon filter.
- Consider ASA instead if fumes are a concern (similar properties, slightly less toxic fumes).

### Acetone Smoothing
ABS's killer feature — acetone vapour creates a glass-smooth surface:
1. Pour a small amount of acetone in a container with a metal platform above it.
2. Place the print on the platform, seal the container.
3. Leave for 5–20 minutes (check regularly).
4. Remove and let dry fully before handling.

> ⚠️ Acetone is highly flammable. Never heat it directly. Use outdoors or with excellent ventilation.

### Post-Processing
- Machines well — drill, tap, sand, and file like traditional plastics.
- Bonds with acetone — use it as a "glue" for ABS parts.
- Accepts paint well after light sanding and primer.

---

## Common Problems

| Problem | Fix |
|---|---|
| Warping/lifting | Enclose printer, raise bed temp, add brim, use ABS slurry |
| Layer separation/cracking | Reduce cooling, raise nozzle temp, enclose |
| Fumes | Improve ventilation / filter enclosure |
| Elephant foot | Lower bed temp slightly, adjust Z offset |
| Stringing | Tune retraction and temp |

---

## When to Use ABS
- Parts that need **acetone smoothing**
- Automotive / under-hood applications (moderate temps)
- Parts needing **post-machining**
- Where **ASA isn't available** but ABS is

---

---

# 🟠 ASA — Acrylonitrile Styrene Acrylate

> **Difficulty:** ⭐⭐ Intermediate | **Category:** Engineering | **UV Resistance:** Excellent

---

## Overview

ASA is essentially ABS's superior outdoor-rated cousin. It shares similar print requirements and properties but adds **excellent UV resistance** and slightly better weather resistance. If you're printing anything that will live outdoors — garden fixtures, automotive trim, outdoor enclosures — ASA is the go-to.

---

## Settings Reference

| Parameter | Typical Range | Notes |
|---|---|---|
| Nozzle Temp | 240–260°C | Start at 250°C |
| Bed Temp | 100–110°C | Same as ABS |
| Print Speed | 40–60 mm/s | |
| Cooling Fan | 0–15% | Keep minimal |
| Enclosure | **Required** | Same warping tendencies as ABS |

---

## Tips & Tricks

- Nearly all ABS tips apply to ASA — **same warping challenges, same enclosure requirements**.
- ASA is slightly **less acetone-smoothable** than ABS but still works.
- Often prints **slightly better** than ABS with fewer layer separation issues.
- **Fumes are less severe** than ABS but still ventilate properly.
- Some brands (e.g. Prusament ASA) are excellent quality with consistent results.

### Outdoor Use
- ASA will hold colour and structural integrity in **direct sunlight** for years where PLA/PETG degrade within months.
- Resistant to **rain, humidity, and temperature cycling**.
- Ideal for: garden stakes, outdoor camera mounts, letterbox parts, automotive exterior trim.

---

## ASA vs ABS: Quick Comparison

| Property | ABS | ASA |
|---|---|---|
| UV Resistance | Poor | **Excellent** |
| Acetone Smoothing | Excellent | Good |
| Printability | Slightly easier | Similar |
| Fumes | Worse | Slightly better |
| Cost | Cheaper | Slightly more |

---

## Recommended Brands

**ABS:**
- Prusament ABS
- Polymaker PolyLite ABS
- eSUN ABS+

**ASA:**
- Prusament ASA ← top recommendation
- Polymaker PolyLite ASA
- Fillamentum ASA

---

*← [Back to README](../README.md)*
