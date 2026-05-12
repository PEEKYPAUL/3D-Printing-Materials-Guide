# 🔴 High-Performance & High-Temperature Materials

> These materials require significant printer capability upgrades. Read the [requirements table in README](../README.md) before purchasing filament.

---

# 🟤 Nylon (PA) — Polyamide

> **Difficulty:** ⭐⭐⭐ Advanced | **HDT:** ~120°C | **Notable:** Chemical resistant, tough, self-lubricating

---

## Overview

Nylon is one of the toughest FDM materials available — it's impact resistant, fatigue resistant, and self-lubricating (great for gears, bearings, hinges). The catch: it is **extremely hygroscopic** — it absorbs moisture from the air within hours, which causes catastrophic print failures.

Common variants: **PA6** (general), **PA12** (less moisture-sensitive), **PA6-CF/GF** (reinforced).

---

## Settings Reference

| Parameter | Range | Notes |
|---|---|---|
| Nozzle Temp | 240–270°C | PA6: 255–270°C; PA12: 240–260°C |
| Bed Temp | 70–85°C | Garolite/G10 preferred |
| Enclosure | Recommended | Reduces warping |
| Cooling | 20–40% | Some cooling helps bridging |
| Bed Surface | Garolite (G10) | Best adhesion by far |

---

## Tips & Tricks

### Moisture — Critical
- **Nylon must be bone dry.** Print directly from a **dryer box** — don't trust even "sealed" spools.
- Dry at **70–80°C for 8–12 hours** before printing.
- Wet nylon: foamy surface, bubbling, drastically reduced strength. Basically unusable.
- Use a **filament dryer with humidity display** — target below 15% RH in the box.

### Bed Adhesion
- **Garolite / G10 sheet** at 70–80°C is the gold standard for nylon adhesion.
- PEI with **PVA glue stick** works reasonably well.
- **Avoid glass** — nylon often won't stick or sticks permanently.

### Warping
- Enclose the printer.
- Use a brim (10+ mm).
- Slow down first layers significantly.

### Applications
- Functional gears, hinges, living hinges
- Wear-resistant parts
- Chemical-resistant enclosures
- Snap-fit mechanisms

---

## Common Problems

| Problem | Fix |
|---|---|
| Foamy/rough surface | **Dry the filament** — this is almost always moisture |
| Warping | Enclosure, garolite bed, brim |
| Poor bed adhesion | Switch to garolite, PVA glue, higher bed temp |
| Weak parts | Under-extruding or cold — raise temp, check flow |

---

## Recommended Brands
- **Taulman Bridge Nylon** — widely used, forgiving
- **Polymaker PolyMide PA12-CF** — excellent CF-reinforced option
- **Bambu PA12-CF** — optimised for their system, excellent results

---
---

# ⚫ PC — Polycarbonate

> **Difficulty:** ⭐⭐⭐ Advanced | **HDT:** ~130–140°C | **Notable:** Optically clear, extremely tough

---

## Overview

Polycarbonate is one of the toughest thermoplastics available — it's used in bulletproof glass, safety helmets, and aerospace components. It prints at high temperatures, needs an enclosure, and absolutely requires an **all-metal hotend**. When printed correctly, it offers exceptional strength and heat resistance.

---

## Settings Reference

| Parameter | Range | Notes |
|---|---|---|
| Nozzle Temp | 260–310°C | Pure PC: 290–310°C; PC blends: 260–280°C |
| Bed Temp | 110–120°C | |
| Enclosure | **Required** | Chamber temp 50–60°C ideal |
| All-Metal Hotend | **Required** | PTFE will off-gas and deform |
| Cooling | 0–20% | Very little cooling |
| Bed Surface | PEI or PC sheet | |

---

## Tips & Tricks

### Hardware Requirements
- **All-metal hotend** — mandatory. No PTFE above the heatbreak.
- High-temp bed: must reliably reach 115°C+.
- Enclosed chamber. A **heated chamber** (50°C+) dramatically reduces warping.
- **Hardened steel or ruby nozzle** recommended — PC is slightly abrasive.

### Moisture
- PC is hygroscopic. Dry at **80°C for 6–8 hours**. Print from a dry box.

### Warping
- PC warps aggressively. Mitigations:
  - Maximum enclosure temperature
  - Large brim (15mm+)
  - Draft shield
  - Slow first layers
  - PC-specific adhesives (PC glue sticks, Magigoo PC)

### Blends vs Pure PC
- **PC/ABS blends** print at lower temps (~260–270°C) and warp less — good starting point.
- **Pure PC** is harder to print but stronger and more heat-resistant.

### Applications
- High-temp functional parts
- Impact-resistant enclosures
- Electrical components needing UL-94 compliance (check brand)
- Optical clarity applications

---

## Recommended Brands
- **Polymaker PolyMax PC** — excellent printability, tough
- **Prusament PC Blend** — reliable, well-documented settings
- **Fiberlogy PC** — good quality
- **Bambu PC** — tuned for their system

---
---

# 🟣 PEI / Ultem — Polyetherimide

> **Difficulty:** ⭐⭐⭐⭐ Expert | **HDT:** 170–217°C | **Notable:** Aerospace-grade, inherently flame-retardant

---

## Overview

PEI (sold as Ultem by SABIC) is a high-performance engineering thermoplastic used in aerospace, medical, and automotive industries. It offers outstanding heat resistance, inherent flame retardancy (UL-94 V-0), chemical resistance, and excellent mechanical properties at elevated temperatures.

**This is a serious engineering material.** It requires a high-end printer with a heated chamber.

---

## Settings Reference

| Parameter | Range | Notes |
|---|---|---|
| Nozzle Temp | 340–380°C | Ultem 1010: 360–380°C; Ultem 9085: 340–360°C |
| Bed Temp | 145–160°C | |
| Chamber Temp | 120–160°C | **Actively heated chamber required** |
| All-Metal Hotend | **Required** | High-temp rated (Volcano, Revo High Flow, etc.) |
| Nozzle Material | Hardened steel / ruby | Standard brass won't survive long |
| Cooling | 0% | None |

---

## Tips & Tricks

### Printer Requirements
Only a handful of printers can print Ultem reliably:
- **Stratasys Fortus** (industrial FDM) — the reference platform
- **Apium P220** — dedicated PEI/PEEK printer
- **AON3D AON-M2** — open-material high-temp system
- High-end modified Voron builds with heated chamber
- Some Bambu X1 prints Ultem 9085 blends — check community results

### Critical Settings
- **Chamber heating is non-negotiable** — without it, delamination is certain.
- Bed surface: **PEI sheet on aluminium** or **PEEK-coated surfaces**. Some use polyimide (Kapton) tape.
- **Zero cooling fan** — even at layer bridges.
- Pre-heat chamber for **30+ minutes** before printing.

### Material Variants
| Variant | Notes |
|---|---|
| Ultem 1010 | Highest performance; food contact; highest temp req. |
| Ultem 9085 | Slightly easier to print; aerospace-qualified; FST rated |
| Ultem 1010-CF | Carbon-fibre reinforced — elite stiffness |

### Applications
- Aircraft interior components (FAR 25.853 compliant)
- Medical sterilisable parts (autoclave-safe)
- High-temperature electrical connectors
- Chemical processing equipment

---
---

# ⬛ PEEK — Polyether Ether Ketone

> **Difficulty:** ⭐⭐⭐⭐ Expert | **HDT:** 140°C (unfilled) / 315°C (filled) | **Notable:** The pinnacle of FDM materials

---

## Overview

PEEK is the king of FDM thermoplastics. It offers an extraordinary combination of mechanical strength, chemical resistance, biocompatibility, and temperature resistance. It's used in spinal implants, jet engine components, and semiconductor manufacturing.

It also costs £100–£200+/kg and requires a fully kitted-out high-temperature printer. But for applications where nothing else will do, PEEK delivers.

---

## Settings Reference

| Parameter | Range | Notes |
|---|---|---|
| Nozzle Temp | 360–400°C | 380°C typical for standard PEEK |
| Bed Temp | 120–160°C | |
| Chamber Temp | 120–140°C | Heated, active chamber |
| Print Speed | 15–30 mm/s | Slow and deliberate |
| Cooling | 0% | Absolutely none |
| Flow Ratio | 1.00 | Print slow at stock flow — adjust only after confirming dry filament and stable temps |
| Nozzle | Hardened steel / ruby | Brass will be destroyed |

---

## Tips & Tricks

### Hardware Requirements
PEEK demands the best:
- **All-metal hotend rated to 400°C+** — standard hotends are not suitable.
- **Actively heated and insulated enclosure** — chamber must maintain 120°C+.
- **High-temp bed** with appropriate surface (clean aluminium, PEI-coated).
- High-quality stepper drivers — long prints at elevated temps stress electronics.

Suitable printers:
- **Apium P220** (purpose-built for PEEK/PEI)
- **AON3D AON-M2**
- **Tractus3D T850P**
- **Raise3D Hyper Speed** (with high-temp upgrade)
- Custom industrial builds

### PEEK-Specific Tips
- **Pre-heat chamber for 45–60 minutes** before printing.
- Keep PEEK in a **sealed dry box** — moisture is devastating. Dry at **120–150°C for 6+ hours**.
- Print slow — there's no rushing PEEK. 20 mm/s is common.
- **First layer adhesion** on aluminium: lightly sandblasted or bead-blasted aluminium + thin PEEK film = excellent adhesion with clean release.
- **Annealing** after printing (in an oven at 200°C for 1–2 hours) significantly improves mechanical properties and reduces residual stress.

### PEEK Variants
| Variant | Notes |
|---|---|
| Standard PEEK | Baseline — excellent across the board |
| PEEK-CF | Carbon-fibre filled — higher stiffness, abrasive |
| PEEK-GF | Glass-fibre filled — balanced properties |
| PEEK-PTFE | Tribological grade — self-lubricating bearings |
| PEEK Unfilled | Best for biomedical/implant applications |

### Cost Justification
PEEK is expensive, but when you need:
- **Biocompatibility** (ISO 10993 compliant grades)
- **Radiation resistance** (nuclear/space)
- **Continuous service above 200°C**
- **Chemical resistance** to virtually all organic solvents
- **Strength approaching aluminium**

...no other FDM material comes close.

---

## PEEK vs PEI Quick Comparison

| Property | PEEK | PEI (Ultem) |
|---|---|---|
| Max Service Temp | 250°C | 170–217°C |
| Biocompatibility | Excellent (implant grade) | Good |
| Flame Retardancy | Self-extinguishing | **UL-94 V-0 inherent** |
| Chemical Resistance | Exceptional | Very good |
| Cost | £150–£200/kg | £100–£150/kg |
| Printability | Very hard | Hard |

---

## Recommended PEEK Brands
- **Victrex PEEK** — the original, industry standard
- **Solvay KetaSpire** — high-quality PEEK
- **Polymaker PolyMide PEEK-CF** — CF-reinforced, excellent
- **3DXTech PEEK** — widely available for desktop printers

---

*← [Back to README](../README.md)*
