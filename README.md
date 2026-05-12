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
| [ASA](materials/ASA.md) | Engineering | ⭐⭐ Intermediate | 240–260°C |
| [TPU / Flexibles](materials/TPU.md) | Flexible | ⭐⭐ Intermediate | 220–240°C |
| [Nylon (PA)](materials/Nylon.md) | Engineering | ⭐⭐⭐ Advanced | 240–270°C |
| [PC (Polycarbonate)](materials/PC.md) | High-Temp | ⭐⭐⭐ Advanced | 260–310°C |
| [PEI / Ultem](materials/PEI.md) | High-Temp | ⭐⭐⭐⭐ Expert | 340–380°C |
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

### Silicone Socks for Low-Temp Materials
A silicone sock is a small sleeve that wraps around your hotend's heater block. For low-temperature materials like PLA, PETG, and TPU they are one of the most overlooked quality-of-life upgrades you can make.

![Silicone sock fitted on a hotend heater block](images/silicone-sock-fitted.jpg)
*A silicone sock fitted on a standard E3D V6 heater block.*

**Benefits:**
- **Temperature stability** - insulates the heater block from the part cooling fan, preventing the fan from fighting your PID and causing temperature swings that show up as surface banding.
- **Prevents filament sticking to the block** - PLA and PETG that ooze onto a bare aluminium block burn, carbonise, and are a pain to clean. A sock keeps the block clean.
- **Reduces heat creep risk** - the sock retains heat more efficiently so your heater doesn't cycle as hard, reducing thermal stress at the heatbreak.
- **Lower power draw** - insulated blocks reach and hold temperature with less energy.
- **Cleaner purges** - ooze drips cleanly off silicone rather than baking onto the block.

![Comparison of heater block with and without silicone sock](images/silicone-sock-comparison.jpg)
*Left: bare heater block after several PLA prints. Right: block protected by a silicone sock - still clean.*

> **Tip:** Silicone socks are shape-specific (E3D V6, Volcano, Dragon, Revo, etc.) - make sure you buy the correct one for your hotend. They cost £1-3 and are one of the best-value upgrades for any printer running PLA or PETG.

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
├── images/
│   └── (drop your images here)
└── CONTRIBUTING.md
```

---

## 🤝 Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) — community tips, corrections, and new material profiles are welcome!

---

*Last updated: 2026 | Licensed under CC BY-SA 4.0*
