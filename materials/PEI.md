# PEI / Ultem - Polyetherimide

> **Difficulty:** ⭐⭐⭐⭐ Expert | **Category:** High-Temp | **HDT:** 170-217C | **Notable:** Aerospace-grade, inherently flame-retardant

---

## Overview

PEI (sold as Ultem by SABIC) is a high-performance engineering thermoplastic used in aerospace, medical, and automotive industries. It offers outstanding heat resistance, inherent flame retardancy (UL-94 V-0), chemical resistance, and excellent mechanical properties at elevated temperatures.

**This is a serious engineering material.** It requires a high-end printer with a heated chamber.

---

## Settings Reference

| Parameter | Range | Notes |
|---|---|---|
| Nozzle Temp | 340-380C | Ultem 1010: 360-380C; Ultem 9085: 340-360C |
| Bed Temp | 145-160C | |
| Chamber Temp | 120-160C | **Actively heated chamber required** |
| All-Metal Hotend | **Required** | High-temp rated |
| Nozzle Material | Hardened steel / ruby | Standard brass won't survive |
| Cooling | 0% | None |
| Flow Ratio | 1.00 | High-temp materials run at stock flow — verify with a test print |

---

## Tips & Tricks

### Printer Requirements

Only a handful of printers can print Ultem reliably:
- **Stratasys Fortus** (industrial FDM) - the reference platform
- **Apium P220** - dedicated PEI/PEEK printer
- **AON3D AON-M2** - open-material high-temp system
- High-end modified Voron builds with heated chamber

### Bed Adhesives
Standard adhesives (glue sticks, hairspray, PVA) **burn off at PEI/Ultem bed temperatures (145-160C)** and should not be used. You need high-temperature rated adhesives.

**Vision Miner Nano Polymer Adhesive** (strongly recommended)
This is the go-to adhesive for printing PEI/Ultem and other high-temp materials:
- Rated for use at **bed temperatures up to 160C** — covers the full Ultem bed temp range.
- Apply a **very thin, even coat** to the clean bed surface while the bed is warming (40-60C).
- Allow the solvent to **fully flash off** (30-60 seconds) before printing — a wet coat will cause adhesion problems.
- Provides extremely strong first-layer grip during the print.
- **Releases cleanly** when the bed cools below 60C — parts lift off with minimal force.
- One bottle lasts a long time when applied correctly (thin coats only).
- Works on aluminium beds, PEI-coated surfaces, and Kapton tape.

> **Tip:** If parts are hard to remove after cooling, wait longer — Ultem and Vision Miner release best at room temperature. Never force a part off a hot bed.

### Critical Settings
- **Chamber heating is non-negotiable** - without it, delamination is certain.
- Bed surface: **PEI sheet on aluminium** or PEEK-coated surfaces. Some use Kapton tape.
- **Zero cooling fan** - even at layer bridges.
- Pre-heat chamber for **30+ minutes** before printing.

### Material Variants

| Variant | Notes |
|---|---|
| Ultem 1010 | Highest performance; food contact; highest temp req. |
| Ultem 9085 | Slightly easier to print; aerospace-qualified; FST rated |
| Ultem 1010-CF | Carbon-fibre reinforced - elite stiffness |

### Applications
- Aircraft interior components (FAR 25.853 compliant)
- Medical sterilisable parts (autoclave-safe)
- High-temperature electrical connectors
- Chemical processing equipment

---

## Common Problems

| Problem | Fix |
|---|---|
| Delamination | Chamber temp too low - must actively heat to 120C+ |
| Warping | Increase chamber temp, extend pre-heat time, add brim |
| Poor adhesion | Ensure bed is clean, use Kapton or PEI-coated surface |
| Nozzle clog | Nozzle too cold or filament not dry - raise temp, re-dry |

---

## PEI vs PEEK Quick Comparison

| Property | PEEK | PEI (Ultem) |
|---|---|---|
| Max Service Temp | 250C | 170-217C |
| Biocompatibility | Excellent (implant grade) | Good |
| Flame Retardancy | Self-extinguishing | **UL-94 V-0 inherent** |
| Chemical Resistance | Exceptional | Very good |
| Cost | £150-200/kg | £100-150/kg |
| Printability | Very hard | Hard |

---

*Back to [README](../README.md)*