# PPS — Polyphenylene Sulfide

> **Difficulty:** ⭐⭐⭐⭐ Expert | **Category:** High-Temp Engineering | **HDT:** 100°C (unfilled) / 200–220°C (GF/CF filled) | **Notable:** Outstanding chemical resistance — one of the most chemically inert printable thermoplastics

---

## Overview

PPS (Polyphenylene Sulfide) is a high-performance semi-crystalline engineering thermoplastic known for its exceptional resistance to chemicals, solvents, and elevated temperatures. It sits between PC and PEI/Ultem in the engineering materials hierarchy — significantly more accessible than PEEK or PEKK, but still demanding hardware and careful process control.

PPS is used extensively in automotive underhood components, chemical processing equipment, electrical connectors, and filtration systems — anywhere a part must survive continuous heat, aggressive chemicals, or both. In FDM, it is available in three main grades:

| Grade | Filler | HDT | Stiffness | Notes |
|---|---|---|---|---|
| **PPS (unfilled)** | None | ~100°C | Moderate | Good baseline properties — chemical resistance is the headline |
| **PPS-GF (glass fibre)** | 30–40% GF | 200–220°C | High | Dramatically improved HDT — best for structural high-temp parts |
| **PPS-CF (carbon fibre)** | 20–30% CF | 200–220°C | Very High | Highest stiffness — lighter than GF variant — requires ruby nozzle |

> 💡 The unfilled grade is chemically resistant but has a modest HDT of around 100°C. If you need both chemical and thermal performance, PPS-GF or PPS-CF is the correct choice — they nearly double the heat deflection temperature.

---

## Settings Reference

| Parameter | PPS (Unfilled) | PPS-GF | PPS-CF |
|---|---|---|---|
| Nozzle Temp | 280–310°C | 300–330°C | 300–330°C |
| Bed Temp | 120–140°C | 130–150°C | 130–150°C |
| Chamber Temp | 80–100°C | 100–120°C | 100–120°C |
| Print Speed | 20–40 mm/s | 15–30 mm/s | 15–30 mm/s |
| Cooling | 0% | 0% | 0% |
| Flow Ratio | 1.00–1.05 | 1.00–1.05 | 1.00–1.05 |
| Nozzle | Hardened steel | Hardened steel or ruby | **Ruby required** |
| All-Metal Hotend | **Required** | **Required** | **Required** |

> ⚠️ Start at the lower end of the nozzle temperature range and increase in 5°C steps if you see poor layer adhesion or under-extrusion. Overshooting temperature on PPS can cause discolouration and material degradation.

---

## Hardware Requirements

| Requirement | PPS | PPS-GF | PPS-CF |
|---|---|---|---|
| All-metal hotend (300°C+ rated) | ✅ Required | ✅ Required | ✅ Required |
| Hardened steel nozzle | ✅ Required | ✅ Required | — |
| Ruby nozzle | Optional | Optional | ✅ Required |
| Heated bed (140–150°C capable) | ✅ Required | ✅ Required | ✅ Required |
| Actively heated enclosure | ✅ Required | ✅ Required | ✅ Required |
| High-temp bed surface | ✅ Required | ✅ Required | ✅ Required |

**Suitable printers:**
- **Intamsys Funmat HT / Pro** — purpose-built for engineering and high-temp filaments
- **AON3D AON-M2** — open-material high-temp platform
- **Apium P220** — industrial-grade high-temp FDM
- High-end custom Voron builds with actively heated chambers (120°C+)

> ⚠️ **PPS-CF is extremely abrasive.** A hardened steel nozzle will show measurable wear over a few hundred grams. A ruby-tipped nozzle is the correct choice for PPS-CF specifically.

---

## Bed Surfaces & Adhesion

PPS has low surface tack at room temperature but bonds aggressively when hot — do not try to remove parts from a hot bed.

| Surface | Adhesion | Notes |
|---|---|---|
| PEI-coated aluminium | ✅ Good | Works well with specialist adhesive |
| Garolite (G10) | ✅ Excellent | Industry standard for PPS — semi-permanent bond |
| Bare aluminium (lightly blasted) | ✅ Good | PPS builds its own release layer after a few prints |
| Kapton tape | ⚠️ OK | Rated for the temperature but adhesion is inconsistent |
| Glass | ❌ Poor | Not suitable |

**Adhesive:** A thin coat of **Vision Miner Nano Polymer Adhesive** works reliably with PPS on PEI and aluminium surfaces. Apply while the bed is warming (50–80°C) and let it flash off fully before printing.

**Garolite (G10/FR4):** Many PPS users prefer garolite sheet over PEI — PPS adheres to it directly without adhesive and releases cleanly once cool. A 1–2mm sheet cut to bed size is a cost-effective long-term solution.

---

## Material Properties

| Property | PPS (Unfilled) | PPS-GF | PPS-CF |
|---|---|---|---|
| Tensile Strength | ~80 MPa | ~140 MPa | ~160 MPa |
| Young's Modulus | ~3.5 GPa | ~9.0 GPa | ~12.0 GPa |
| Heat Deflection Temp | ~100°C | 200–220°C | 200–220°C |
| Chemical Resistance | Outstanding | Outstanding | Outstanding |
| Flame Rating | UL94 V-0 | UL94 V-0 | UL94 V-0 |
| UV Resistance | Good | Good | Good |
| Moisture Absorption | Very low (<0.01%) | Very low | Very low |
| Density | ~1.35 g/cm³ | ~1.6 g/cm³ | ~1.4 g/cm³ |

### Chemical Resistance Highlights

PPS resists virtually all common industrial chemicals below 200°C:

| Chemical Class | Resistance |
|---|---|
| Fuels and oils | ✅ Excellent |
| Acids (dilute and concentrated) | ✅ Excellent |
| Alkalis | ✅ Excellent |
| Organic solvents | ✅ Excellent |
| Chlorinated solvents | ✅ Excellent |
| Steam / hot water | ✅ Very Good |
| Strong oxidising acids (e.g. HNO₃ hot) | ⚠️ Limited |

> 💡 PPS chemical resistance is one of the reasons it is used in chemical processing and filtration — it handles environments that would destroy nylon, PC, and most other engineering thermoplastics.

---

## PPS vs Comparable Materials

| Property | PPS | PC | PEEK |
|---|---|---|---|
| Print temperature | 280–320°C | 260–310°C | 360–400°C |
| HDT (unfilled) | ~100°C | ~110–120°C | ~140°C |
| HDT (GF/CF filled) | 200–220°C | 130°C | 250°C+ |
| Chemical resistance | Outstanding | Moderate | Exceptional |
| Printability | Hard — needs chamber | Hard — needs enclosure | Very hard — needs 140°C chamber |
| Cost | £80–£150/kg (unfilled) | £30–£60/kg | £150–£200/kg |
| Flame rating | UL94 V-0 | HB–V-2 | UL94 V-0 |

---

## Filament Drying

PPS has very low moisture absorption, but it must still be dried before printing — absorbed moisture causes bubbling, stringing, and weak layer bonds.

| Drying Method | Temperature | Time |
|---|---|---|
| Convection oven | 120°C | 4–6 hours |
| Filament dryer (high-temp capable) | 120°C | 6–8 hours |
| Storage after drying | Airtight container with desiccant | Indefinitely |

> 💡 Because PPS absorbs moisture very slowly, it is less sensitive than nylon — but a high-temp drying cycle is still required before first use and after any extended open-air storage.

---

## Tips & Tricks

- **Pre-heat the chamber for 45–60 minutes** before printing — the build plate, frame, and part all need to be at temperature before the first layer goes down.
- **Zero part cooling** — even brief cooling fan use during the print can cause delamination between layers.
- **First layer is critical** — PPS first layers are unforgiving. Dial in your Z offset on a small test before committing to a full print.
- **Print slowly** — 20–40 mm/s for unfilled, 15–30 mm/s for GF and CF. PPS does not tolerate being rushed.
- **Dry before every print session** — even if the spool was recently dried, if it's been open to air for more than a day or two, re-dry it.
- **Use garolite for GF/CF grades** — the higher stiffness means more warp force at part edges. Garolite provides stronger grip than PEI with adhesive.
- **Ventilate your workspace** — PPS processing releases fumes. Ensure adequate extraction or filtration when printing in enclosed spaces.
- **Avoid abrupt temperature changes** — quenching a PPS part by removing it from a hot chamber too quickly can induce internal stress. Let it cool with the chamber door slightly open.

---

## Common Problems

| Problem | Likely Cause | Fix |
|---|---|---|
| Delamination / layer splitting | Chamber too cold or part cooling on | Raise chamber to 100°C+, disable fan completely |
| Warping / corner lifting | Bed too cold or poor adhesion | Raise bed to 130–140°C, switch to garolite or apply Vision Miner |
| Under-extrusion / poor flow | Temp too low, wet filament, or speed too high | Raise nozzle temp 5°C, re-dry at 120°C, reduce speed |
| Bubbling or popping during print | Wet filament | Dry at 120°C for 6 hours minimum |
| Poor first layer adhesion | Z offset, bed temp, or cold chamber | Re-dial Z, ensure chamber is fully pre-heated before starting |
| Nozzle wear (CF variant only) | Non-ruby nozzle being used | Switch to ruby-tipped nozzle |
| Discolouration or burning | Nozzle temp too high | Reduce temp by 5°C at a time |

---

## Applications

- **Automotive** — underhood fluid connectors, sensor housings, pump components
- **Chemical processing** — pump impellers, valve bodies, manifolds exposed to aggressive chemicals
- **Electrical / electronics** — connectors, relay housings, switch gear — inherently flame-retardant (UL94 V-0)
- **Filtration** — filter housings, membranes exposed to industrial solvents and acids
- **Aerospace** — brackets and ducting in environments combining heat and chemical exposure
- **Medical** — sterilisable housings and instrument components where chemical resistance is essential

---

## Recommended Brands

PPS filament is a specialist product — source from reputable engineering-grade suppliers.

- **[Luvocom 3F PPS (Lehvoss Group)](https://www.lehvoss.de)** — industrial-grade PPS and PPS-GF, excellent dimensional consistency, used in aerospace and automotive applications
- **[3DXTech PPS & PPS-CF](https://www.3dxtech.com)** — desktop-printer-compatible grades including CF-filled variants, widely available
- **[Treed Fillaments PPS](https://www.treedfillaments.com)** — European supplier, consistent quality, both unfilled and GF grades

---

*← [Back to README](../README.md)*
