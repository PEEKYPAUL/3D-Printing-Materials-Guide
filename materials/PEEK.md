
# PEEK — Polyether Ether Ketone

> **Difficulty:** ⭐⭐⭐⭐ Expert | **HDT:** 140–250°C (amorphous to semi-crystalline) / 270–280°C (CF/GF filled) | **Notable:** The pinnacle of FDM materials

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
- Custom industrial builds

### PEEK-Specific Tips

### Bed Adhesives for PEEK
PEEK requires adhesives rated for extreme bed and chamber temperatures. Standard adhesives fail completely.

**Vision Miner Nano Polymer Adhesive** (the industry standard for PEEK)
- Widely regarded as the best adhesive for PEEK printing.
- Rated to **160C bed temperature** — handles PEEK's demanding bed requirements.
- Apply a **very thin coat** to the clean bed surface as it warms (50-80C), then allow the solvent to fully flash off before printing.
- Delivers strong first-layer grip even under the elevated chamber temps PEEK demands.
- **Releases cleanly** once the bed cools — parts peel away without damage.
- Reapply every 2-4 prints or when you notice a drop in first-layer grip.
- Works on aluminium, PEI-coated aluminium, and high-temp build surfaces.

**Bare Aluminium (No Adhesive)**
For some PEEK grades (especially filled variants):
- Lightly sandblasted or bead-blasted aluminium at 120-160C provides mechanical adhesion.
- Apply a very thin PEEK film to the bare aluminium in the first few layers — it fuses and acts as its own adhesive base for subsequent prints.
- Some users prefer this approach for the cleanest part release.

> **Avoid:** Glue sticks, hairspray, and PVA — these all burn off well below PEEK's bed temperature and will leave a carbonised mess on your bed surface.


- **Pre-heat chamber for 45–60 minutes** before printing.
- Keep PEEK in a **sealed dry box** — moisture is devastating. Dry at **120–150°C for 6+ hours**.
- Print slow — there's no rushing PEEK. 20 mm/s is common.
- **First layer adhesion** on aluminium: lightly sandblasted or bead-blasted aluminium + thin PEEK film = excellent adhesion with clean release.
- **Annealing** after printing significantly improves mechanical properties — see the [PEEK Annealing guide](../post-processing/PEEK-Annealing.md) for the full two-stage cycle (100°C/3h → 200°C/5h with a 24h cool-down).

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

## 📊 Strength Statistics

Approximate mechanical properties for printed parts — values vary by brand and print settings. Use as a guide for material selection, not engineering calculations.

| Property | Standard PEEK | PEEK-CF | PEEK-GF |
|---|---|---|---|
| Tensile Strength | 100 MPa | 160 MPa (+60%) | 140 MPa (+40%) |
| Young's Modulus (Stiffness) | 4.5 GPa | 15.0 GPa (+233%) | 10.0 GPa (+122%) |
| Heat Deflection Temp | 250°C | 280°C+ | 270°C+ |

> 📖 See the full [CF & GF Composites Guide](CF-Composites.md) for a cross-material strength comparison and details on printing fibre-reinforced variants.

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
- **[Victrex PEEK](https://www.victrex.com)** — the original, industry-standard PEEK resin made into filament
- **[Solvay KetaSpire PEEK](https://www.solvay.com)** — high-purity, aerospace and medical grade
- **[Polymaker PolyMide PEEK-CF](https://www.polymaker.com)** — CF-reinforced, excellent stiffness
- **[3DXTech PEEK](https://www.3dxtech.com)** — widely available, engineering-grade, desktop-printer compatible

---

*← [Back to README](../README.md)*
