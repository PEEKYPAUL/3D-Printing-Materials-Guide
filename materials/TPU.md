# 🟢 TPU / Flexible Filaments

> **Difficulty:** ⭐⭐ Intermediate | **Category:** Flexible | **Shore Hardness:** 75A–98A

---

## Overview

TPU (Thermoplastic Polyurethane) is the most common flexible filament. It's rubber-like, abrasion resistant, and great for phone cases, gaskets, wheels, and wearable parts. The softer the filament (lower Shore A rating), the harder it is to print — particularly on Bowden setups.

Other flexibles include **TPE** (softer, harder to print), **TPC** (higher temp resistance), and **Shore 95A TPU** which behaves almost like a rigid material.

---

## Settings Reference

| Parameter | Typical Range | Notes |
|---|---|---|
| Nozzle Temp | 220–240°C | Start at 230°C |
| Bed Temp | 30–60°C | PEI at 40–50°C works great |
| Print Speed | **15–30 mm/s** | **Slow is essential** |
| Cooling Fan | 50–100% | Good cooling helps |
| Retraction | **Minimal or off** | Flexibles clog easily with retraction |
| Direct Drive | **Strongly recommended** | Bowden requires careful setup |

---

## Shore Hardness Guide

| Shore Rating | Feel | Printability |
|---|---|---|
| 75A | Very soft, gel-like | ⭐ Very hard |
| 85A | Soft rubber | ⭐⭐ Hard |
| 95A | Firm rubber | ⭐⭐⭐ Moderate |
| 98A | Almost rigid | ⭐⭐⭐⭐ Easy |

---

## Tips & Tricks

### The Golden Rule: Slow Down
- TPU buckles, coils, and clogs if pushed too fast. **20 mm/s** is a safe starting point.
- Even with a direct drive, don't exceed 40 mm/s until you've confirmed reliability.
- **Disable or minimise retraction** — flexibles don't retract cleanly; they stretch and can cause under-extrusion.

### Bowden Printers
- Soft TPU (below 90A) on a Bowden setup is extremely challenging.
- Gaps in the PTFE path allow the filament to buckle and loop.
- If you must use Bowden: print very slowly (15 mm/s), reduce retraction to 0–1 mm, and keep the tube gap-free.
- A **direct drive conversion** is strongly recommended if you print flex regularly.

### Slicer Settings
- **Infill pattern:** Gyroid, honeycomb, or concentric — these compress and stretch naturally.
- **Wall count:** 3–4 walls for durability, fewer for extra flexibility.
- **Infill %:** Lower infill = more flex. 10–20% for very flexible, 50–80% for firmer.
- **No ironing** — the extra nozzle pass can create blobs on flex.

### Preventing Tangles
- TPU spools can tangle and kink. Feed filament **straight and supported** to the extruder.
- Don't let the spool unwind loosely — it tangles on itself.

### Moisture
- TPU absorbs moisture. Dry at **50–60°C for 4–6 hours**. Signs: stringing, bubbly surface.

---

## Applications
- Phone and tablet cases
- Gaskets and seals
- RC tyres and wheels
- Cable strain reliefs
- Anti-vibration feet/mounts
- Wearable bands (watch straps, braces)
- Rollers and conveyor wheels

---

## Common Problems

| Problem | Fix |
|---|---|
| Filament coiling in extruder | Reduce speed, disable retraction, check PTFE gaps |
| Stringing | Disable retraction, increase travel speed, dry filament |
| Under-extrusion | Too fast — slow down |
| Bubbling/hissing | Wet filament — dry it |
| Part too stiff | Reduce infill, reduce wall count |
| Part too soft/floppy | Increase infill, increase walls |

---

## Recommended Brands

- **Polymaker PolyFlex TPU95** — reliable, widely available
- **Bambu TPU 95A** — excellent for Bambu systems
- **Sainsmart TPU** — budget-friendly, good quality
- **NinjaTek Cheetah (95A)** — premium, excellent performance
- **NinjaTek NinjaFlex (85A)** — very soft, challenging to print
- **Recreus FilaFlex** — Spanish brand, excellent soft options

---

*← [Back to README](../README.md)*
