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
| Flow Ratio | 0.98 | TPU varies widely by brand and hardness — calibrate per spool |

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

### Preventing Tangles & Feed Issues
- TPU spools can tangle and kink. Feed filament **straight and supported** to the extruder.
- Don't let the spool unwind loosely — it tangles on itself.
- **Mount the spool directly above the extruder** so filament feeds straight down under gravity — this reduces the resistance the extruder has to fight and significantly improves reliability.
- Add a **bearing to the spool hub** so it spins freely with minimal drag. Resistance on the spool is one of the leading causes of under-extrusion with flex filaments.

### Slicer Tips
- **Enable "Avoid crossing perimeters"** for all travel moves — this keeps strings inside the model where they're invisible, dramatically reducing the need for retraction.
- **Enable Coasting** to reduce nozzle pressure before travel moves — helps prevent blobs at travel start/end points.
- **Avoid rafts** — the higher extrusion rate used in raft base layers can cause blobs and adhesion problems when transitioning to the actual part. Use a brim instead if you need extra adhesion.
- Layer height **0.1–0.2mm** gives the best interlayer bonding and surface finish for flex materials.

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

- **[Polymaker PolyFlex TPU95](https://www.polymaker.com)** — reliable, widely available, great all-rounder
- **[FormFutura TPU](https://www.formfutura.com)** — solid mid-tier, consistent diameter
- **[Sunlu TPU](https://www.sunlu.com)** — budget-friendly, good colour range
- **[eSUN TPU 95A](https://www.esun3d.com)** — consistent quality, widely available
- **[NinjaTek Cheetah 95A](https://ninjatek.com)** — premium, excellent performance, very consistent
- **[NinjaTek NinjaFlex 85A](https://ninjatek.com)** — very soft, challenging to print, best-in-class flexibility
- **[Recreus FilaFlex](https://recreus.com)** — Spanish brand, excellent range from 60A to 96A

---

*← [Back to README](../README.md)*
