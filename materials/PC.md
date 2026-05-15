# PC - Polycarbonate

> **Difficulty:** ⭐⭐⭐ Advanced | **Category:** High-Temp | **HDT:** ~130–140°C | **Notable:** Optically clear, extremely tough

---

## Overview

Polycarbonate is one of the toughest thermoplastics available - it's used in bulletproof glass, safety helmets, and aerospace components. It prints at high temperatures, needs an enclosure, and absolutely requires an **all-metal hotend**. When printed correctly, it offers exceptional strength and heat resistance.

---

## Settings Reference

| Parameter | Range | Notes |
|---|---|---|
| Nozzle Temp | 260–310°C | Pure PC: 290–310°C; PC blends: 260–280°C |
| Bed Temp | 110–120°C | |
| Enclosure | **Required** | Chamber temp 50–60°C ideal |
| All-Metal Hotend | **Required** | PTFE will off-gas and deform |
| Cooling | 0-20% | Very little cooling |
| Bed Surface | PEI or PC sheet | |
| Flow Ratio | 1.00 | Calibrate once filament is fully dry |

---

## Tips & Tricks

### Hardware Requirements
- **All-metal hotend** - mandatory. No PTFE above the heatbreak.
- High-temp bed: must reliably reach 115°C+.
- Enclosed chamber. A **heated chamber** (50°C+) dramatically reduces warping.
- **Hardened steel or ruby nozzle** recommended - PC is slightly abrasive.
- **Avoid Build-tak above 80°C** — PC's bed temp will cause parts to bond permanently to Build-tak, destroying both the part and the surface.

### First Layer & Temperature Strategy
- **Print the first layer 20–30°C hotter** than the rest of the print to maximise bed adhesion, then drop to your normal nozzle temp from layer 2.
- **First layer speed: 15–30% of normal** — very slow ensures proper bonding.
- **First layer width: 120–150%** — wider lines give more contact area with the bed.

### Cooling & Bridging
- **No fan for the first 4–5 layers** — then gradually increase to a maximum of 20% if needed for bridging. Never use high cooling with PC — delamination risk is severe.
- **Bridging fan: ~25%** — just enough to help bridges set without causing thermal stress.
- **Bridging extrusion multiplier: 120%** — PC needs slightly more material to bridge gaps cleanly.
- **Bridging speed: ~40% of normal** — slower bridging gives better results with PC.

### Infill & Structure
- Use a **minimum of 25% infill** to properly support top layers — PC's relatively high printing temp means thin top layers can sag without adequate support underneath.
- **4+ top layers** recommended for a solid, flat top surface.

### Moisture
- PC is hygroscopic. Dry at **80°C for 6-8 hours**. Print from a dry box.

### Warping
- PC warps aggressively. Mitigations:
  - Maximum enclosure temperature
  - Large brim (15mm+)
  - Draft shield
  - Slow first layers
  - PC-specific adhesives (PC glue sticks, Magigoo PC)

### Blends vs Pure PC
- **PC/ABS blends** print at lower temps (~260–270°C) and warp less - good starting point.
- **Pure PC** is harder to print but stronger and more heat-resistant.

### Applications
- High-temp functional parts
- Impact-resistant enclosures
- Electrical components needing UL-94 compliance (check brand)
- Optical clarity applications

---

## 📊 Strength Statistics

Approximate mechanical properties for printed parts — values vary by brand and print settings. Use as a guide for material selection, not engineering calculations.

| Property | Standard PC | PC-CF | PC-GF |
|---|---|---|---|
| Tensile Strength | 65 MPa | 78 MPa (+20%) | 72 MPa (+11%) |
| Young's Modulus (Stiffness) | 2.3 GPa | 6.0 GPa (+161%) | 5.0 GPa (+117%) |
| Heat Deflection Temp | 130°C | 145°C | 140°C |

> 📖 See the full [CF & GF Composites Guide](CF-Composites.md) for a cross-material strength comparison and details on printing fibre-reinforced variants.

---

## Common Problems

| Problem | Fix |
|---|---|
| Warping | Max enclosure temp, large brim, draft shield, PC adhesive |
| Layer delamination | Raise nozzle temp, reduce cooling, enclose |
| Poor bed adhesion | Use PC glue stick or Magigoo PC |
| Stringing | Tune retraction, ensure filament is dry |

---

## Recommended Brands
- **[Polymaker PolyMax PC](https://www.polymaker.com)** — excellent printability, tough, widely available
- **[Prusament PC Blend](https://www.prusament.com)** — reliable, well-documented settings
- **[3DXTech PC](https://www.3dxtech.com)** — engineering-grade, high performance
- **[Fiberlogy PC](https://fiberlogy.com)** — solid mid-tier, good print quality

---

*Back to [README](../README.md)*