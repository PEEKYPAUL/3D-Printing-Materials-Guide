[README.md](https://github.com/user-attachments/files/27641746/README.md)
# 🧵 3D Printing Materials Guide

> A comprehensive reference for FDM/FFF filament materials — tricks, tips, and troubleshooting for every plastic from beginner-friendly PLA to exotic high-temperature engineering filaments.

---

## 📚 Table of Contents

| Material | Category | Difficulty | Temp Range |
|---|---|---|---|
| [PLA](materials/PLA.md) | Standard | ⭐ Beginner | 180–220°C |
| [PETG](materials/PETG.md) | Standard | ⭐⭐ Intermediate | 230–250°C |
| [ABS](materials/ABS.md) | Engineering | ⭐⭐ Intermediate | 230–250°C |
| [ASA](materials/ABS.md) | Engineering | ⭐⭐ Intermediate | 240–260°C |
| [TPU / Flexibles](materials/TPU.md) | Flexible | ⭐⭐ Intermediate | 220–240°C |
| [Nylon (PA)](materials/PEEK.md) | Engineering | ⭐⭐⭐ Advanced | 240–270°C |
| [PC (Polycarbonate)](materials/PEEK.md) | High-Temp | ⭐⭐⭐ Advanced | 260–310°C |
| [PEI / Ultem](materials/PEEK.md) | High-Temp | ⭐⭐⭐⭐ Expert | 340–380°C |
| [PEEK](materials/PEEK.md) | High-Temp | ⭐⭐⭐⭐ Expert | 360–400°C |
| [Carbon Fibre Composites](materials/CF-Composites.md) | Composite | ⭐⭐⭐ Advanced | Varies |
| [Support Materials (PVA, HIPS)](materials/Support-Materials.md) | Support | ⭐⭐ Intermediate | Varies |

---

## 🔧 General Tips (Apply to All Materials)

### Printer Preparation
- **Dry your filament** before every print — moisture ruins almost every material. Even "dry" filament absorbs humidity within hours in humid climates.
- **Calibrate your e-steps** and flow rate per spool, not just per material type.
- **First-layer calibration** is non-negotiable. A bad first layer causes 90% of failed prints.
- **PID-tune your hotend and bed** when switching material families.

### Slicer Settings Philosophy
- Start with a **known-good community profile** then dial in from there — don't start from scratch.
- Change **one variable at a time** when troubleshooting.
- **Pressure advance / linear advance** makes a huge difference for quality — tune it per filament.
- **Print slower** when in doubt. Speed is the enemy of quality for difficult materials.

### Storage
- Store all filament in **airtight containers with desiccant** (silica gel or colour-indicating varieties).
- **Vacuum seal bags** are excellent for long-term storage.
- A **filament dryer** (e.g. Sunlu S2, PrintDry) is one of the best investments you can make.
- Track **date opened** on each spool.

---

## 🌡️ Temperature Quick Reference

```
PLA      ████░░░░░░░░░░░  180–220°C nozzle | 45–60°C bed
PETG     ██████░░░░░░░░░  230–250°C nozzle | 70–85°C bed  
ABS      ██████░░░░░░░░░  230–250°C nozzle | 100–110°C bed
ASA      ███████░░░░░░░░  240–260°C nozzle | 100–110°C bed
Nylon    ████████░░░░░░░  240–270°C nozzle | 70–85°C bed
PC       █████████░░░░░░  260–310°C nozzle | 110–120°C bed
PEI      ████████████░░░  340–380°C nozzle | 120–160°C bed
PEEK     █████████████░░  360–400°C nozzle | 120–160°C bed
```

> ⚠️ High-temp materials (PC, PEI, PEEK) require an **all-metal hotend**, high-temp bed surface, and ideally an **enclosed, actively heated chamber**.

---

## 🔬 Printer Requirements by Category

| Requirement | Standard (PLA/PETG) | Engineering (ABS/Nylon) | High-Temp (PC/PEEK) |
|---|---|---|---|
| Hotend | PTFE-lined OK | All-metal preferred | **All-metal required** |
| Max Nozzle Temp | 250°C | 280°C | **400°C+** |
| Heated Bed | 60°C | 110°C | **120°C+** |
| Enclosure | Not needed | Strongly recommended | **Required** |
| Chamber Heating | No | Optional | **Required for PEEK** |
| Hardened Nozzle | Optional | Recommended for CF | **Required for CF** |

---

## 📂 Repository Structure

```
3d-printing-materials-guide/
├── README.md                    ← You are here
├── materials/
│   ├── PLA.md
│   ├── PETG.md
│   ├── ABS.md
│   ├── ASA.md
│   ├── TPU.md
│   ├── Nylon.md
│   ├── PC.md
│   ├── PEI.md
│   ├── PEEK.md
│   ├── CF-Composites.md
│   └── Support-Materials.md
├── troubleshooting/
│   ├── Warping.md
│   ├── Stringing.md
│   ├── Layer-Adhesion.md
│   └── Moisture-Damage.md
└── CONTRIBUTING.md
```

---

## 🤝 Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) — community tips, corrections, and new material profiles are welcome!

---

*Last updated: 2026 | Licensed under CC BY-SA 4.0*
