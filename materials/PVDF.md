# PVDF — Polyvinylidene Fluoride

> **Difficulty:** ⭐⭐⭐⭐ Expert | **Category:** High-Performance Fluoropolymer | **Chemical Resistant:** Yes

---

## Overview

PVDF is a semi-crystalline fluoropolymer that sits at the very high end of FDM materials. It offers outstanding chemical resistance to almost every aggressive substance — acids, bases, solvents, fuels, oils, and alcohols — combined with excellent UV stability, a V-0 flame rating, and a continuous use temperature of 130°C. It also resists nuclear radiation, making it genuinely unique among printable plastics.

It is not a beginner material. PVDF requires an all-metal hotend, a well-tuned printer, and careful first-layer dialling. When set up correctly it produces functional parts that can operate in environments that would destroy almost any other printed polymer.

> ⚠️ **PVDF is NOT the same as PTFE (Teflon).** PVDF is printable via FDM; PTFE is not. Both are fluoropolymers but they behave very differently.

---

## Settings Reference

| Parameter | Typical Range | Notes |
|---|---|---|
| Nozzle Temp | 245–265°C | Start at 250°C and tune — too hot causes burning and discolouration |
| Bed Temp | 90–110°C | 100°C is a good starting point |
| Print Speed | 20–40 mm/s | Print slowly — PVDF does not tolerate speed |
| Cooling Fan | Off or minimal | Too much cooling causes delamination and warping |
| Retraction | 1–3 mm | Keep low — PVDF is not prone to stringing |
| Layer Height | 0.1–0.25 mm | Thinner layers improve interlayer bonding |
| Flow Ratio | 1.0–1.05 | May need slight over-extrusion — tune with a flow test |
| Enclosure | Strongly recommended | Prevents warping; chamber temp 40–60°C ideal |

---

## Bed Surfaces

| Surface | Adhesion | Notes |
|---|---|---|
| PEI (textured) | ✅ Good | Works well at 100°C — parts release cleanly when cool |
| PEI (smooth) | ✅ Good | Clean with IPA before every print |
| Garolite (G10) | ✅ Excellent | Best adhesion for PVDF — used in professional settings |
| Glass + PVA glue | ⚠️ OK | Thin layer of glue stick or Magigoo can help |
| Bare glass | ❌ Poor | Usually not enough adhesion without adhesive |

> 💡 **Tip:** PVA glue stick or Magigoo HT on a glass or PEI surface significantly improves first layer adhesion and makes parts easier to remove.

---

## Hardware Requirements

| Requirement | Needed? | Notes |
|---|---|---|
| All-metal hotend | ✅ **Required** | PTFE-lined hotends must not be used above 240°C — PVDF prints at 245–265°C |
| Hardened steel nozzle | Recommended | PVDF is mildly abrasive and will wear a brass nozzle over time |
| Heated bed (110°C capable) | ✅ **Required** | Standard |
| Enclosure | Strongly recommended | Prevents warping, maintains ambient temp |
| Heated chamber | Not required | Though 40–60°C ambient helps significantly with adhesion |

---

## Material Properties

| Property | Value |
|---|---|
| Continuous Use Temp | 130°C |
| Flame Rating | UL 94 V-0 (self-extinguishing, low smoke) |
| UV Resistance | Excellent — stable molecular bonds resist UV degradation |
| Chemical Resistance | Outstanding — see table below |
| Moisture Absorption | Non-hygroscopic — **no drying required** |
| Abrasion Resistance | Excellent — comparable to Nylon and UHMW-PE |
| Radiation Resistance | Yes — resistant to nuclear radiation |
| Flexibility | Slight — more rigid than TPU but not brittle |

---

## Chemical Resistance

PVDF is resistant to a very wide range of aggressive substances:

| Chemical Group | Resistance |
|---|---|
| Acids (dilute & concentrated) | ✅ Excellent |
| Bases / Alkalis | ✅ Excellent |
| Solvents (ketones, esters, ethers) | ✅ Excellent |
| Alcohols | ✅ Excellent |
| Automotive fluids & fuels | ✅ Excellent |
| Oils & lubricants | ✅ Excellent |
| Chlorinated solvents | ⚠️ Check specific compound |
| Strong oxidising agents | ⚠️ Check specific compound |

> ⚠️ Always verify compatibility for your specific chemical environment before using in production parts. PVDF is not resistant to fuming sulphuric acid, amines, or certain polar aprotic solvents.

---

## Tips & Tricks

### Printing
- **Print slowly.** PVDF has a narrow processing window — rushing leads to delamination and warping.
- **An enclosure is essential for reliable results.** Even with PLA-level temperatures, open-air printing causes warping.
- **Do not use PTFE-lined hotends.** PVDF prints above 240°C — the maximum safe temperature for PTFE tubing.
- **Drying is not needed** — PVDF is non-hygroscopic, so it won't absorb moisture from the air.
- **First layer is critical** — take your time dialling in the Z offset and bed adhesion. A failed first layer is almost impossible to recover from with PVDF.
- **Avoid rapid cooling.** Don't open the enclosure immediately after printing — let parts cool slowly inside to reduce warping and residual stress.

### Adhesion
- Garolite (G10/FR4) sheet is the gold-standard bed surface for fluoropolymers.
- A thin layer of PVA glue stick on PEI is a cost-effective alternative.
- Add a **brim of 8–10mm** on all parts — PVDF wants to warp at corners.

### Post-Processing
- PVDF is chemically resistant — standard solvents and adhesives won't work.
- **Mechanical fastening** (screws, heat-set inserts) is the recommended joining method.
- Machining is possible — PVDF can be drilled, tapped, and milled cleanly.
- Surface finish is typically good out of the printer — sanding is possible but rarely needed.

---

## Common Problems

| Problem | Likely Cause | Fix |
|---|---|---|
| Warping / lifting | No enclosure, bed too cold | Add enclosure, raise bed to 100–110°C, use Garolite or glue |
| Delamination / layer separation | Cooling too aggressive, speed too high | Turn off or reduce part fan, slow down to 25 mm/s |
| Discolouration / burning | Nozzle too hot | Drop temp 5°C at a time |
| Poor bed adhesion | Wrong surface or cold bed | Switch to Garolite or add PVA glue, ensure bed is at temp |
| Stringing | Retraction too low | Increase retraction to 2–3 mm |
| Under-extrusion | Speed too high or temp too low | Slow down, raise temp 5°C |

---

## Applications

PVDF is chosen when no other printed material will survive the environment:

- **Chemical processing** — fluid handling components, valves, fittings, lab equipment
- **Aerospace & defence** — structural and fluid system parts requiring flame resistance
- **Automotive** — under-hood components exposed to oils, fuels, and high temperatures
- **Medical & laboratory** — chemically inert parts for sample handling
- **Outdoor & UV-exposed** — housings, clips, and fixtures that must survive years outdoors
- **Nuclear** — radiation-resistant components (unique among FDM materials)

---

## Variants & Suppliers

| Product | Supplier | Notes |
|---|---|---|
| [FluorX PVDF](https://www.3dxtech.com/products/fluorx-pvdf-1) | [3DXTech](https://www.3dxtech.com) | Leading PVDF filament — high quality, US-made, engineering-grade |

> PVDF filament is a speciality product with limited supplier options compared to commodity materials. 3DXTech is the most widely referenced source for printable PVDF.

---

*← [Back to README](../README.md)*
