# 🖨️ 3D Printing — Ultimate Guide

> The all-in-one reference for FDM/FFF 3D printing. Covering everything from printer tuning and troubleshooting to post-processing, Klipper software & plugins, hardware upgrades, and filament materials — whether you're a beginner dialling in your first PLA print or running exotic high-temperature engineering filaments.

---

## 🎯 Tuning Guides

| Guide | What It Covers |
|---|---|
| [First Layer Calibration](tuning/First-Layer-Calibration.md) | Open Orca Slicer, print an 80×80mm square, dial in Z offset and flow ratio |
| [Temperature Tower](tuning/Temperature-Tower.md) | Find the optimal nozzle temperature for any filament using Orca Slicer's built-in calibration |
| [Pressure Advance](tuning/Pressure-Advance.md) | Eliminate corner bulging and improve sharp detail with PA/LA calibration |
| [Retraction Calibration](tuning/Retraction-Calibration.md) | Reduce stringing and oozing by dialling in retraction distance and speed |
| [Flow Rate Calibration](tuning/Flow-Rate-Calibration.md) | Measure actual extrusion width and correct your flow ratio with a single-wall cube |
| [Input Shaping](tuning/Input-Shaping.md) | Reduce ringing and ghosting artefacts — ADXL345 setup, resonance testing, belt comparison, and applying results to printer.cfg |
| [PID Tuning](tuning/PID-Tuning.md) | Stabilise hotend and bed temperatures — tune under real print conditions for accurate results |

---

## 🛠️ Troubleshooting Guides

| Guide | What It Covers |
|---|---|
| [Stringing & Oozing](troubleshooting/Stringing.md) | Root causes in fix order — retraction, temperature, travel speed, material-specific tips |
| [Warping & Adhesion Failure](troubleshooting/Warping.md) | Bed temps, brim sizing, enclosures, adhesive table, draft shields |
| [Poor Layer Adhesion](troubleshooting/Layer-Adhesion.md) | Temperature, speed, cooling, flow rate — with a strength test method |
| [Clogged Nozzle](troubleshooting/Clogged-Nozzle.md) | Symptom table, cold pull step-by-step, needle method, when to replace |
| [Moisture-Damaged Filament](troubleshooting/Moisture-Damage.md) | Symptoms, sensitivity by material, drying guide with temps and durations, storage tips |
| [Raspberry Pi Wi-Fi Disconnecting](troubleshooting/WiFi-Disconnecting.md) | Fix random Wi-Fi dropouts on your Pi — disable power saving mode via PuTTY and a udev rule |
| [General Tips](troubleshooting/General-Tips.md) | Printer preparation, silicone socks, slicer philosophy, and filament storage — applies to all materials |
| [Printer Adjustment — Skew & Scale](troubleshooting/Printer-Adjustment.md) | Fix XY skew and dimensional scale errors using the Califlower calibration tool — covers Klipper, Marlin, and slicer correction |

---

## ✨ Post-Processing Guides

| Guide | What It Covers |
|---|---|
| [Sanding & Finishing](post-processing/Sanding-Finishing.md) | Grit progression, filler primer guide coat, wet sanding, final finish options |
| [Acetone Smoothing](post-processing/Acetone-Smoothing.md) | ABS/ASA cold vapour and direct wipe methods, safety, timing guide |
| [Painting Prints](post-processing/Painting.md) | Surface prep, primer types, base coat technique, hobby acrylics, clear coat |
| [Heat-Set Inserts](post-processing/Heat-Set-Inserts.md) | Hole sizing table (M2–M5), iron temps by material, installation process, common mistakes |

---

## 💻 Klipper Software Guides & Recommendations

Essential tools and plugins to get the most out of your Klipper setup.

| Tool | Description |
|---|---|
| [KIAUH](https://github.com/dw-0/kiauh) | **Klipper Installation And Update Helper** — the go-to script for installing, updating, and managing Klipper, Moonraker, Mainsail, Fluidd, and related components. Start here if setting up Klipper from scratch. |
| [KAMP – Klipper Adaptive Meshing & Purging](https://github.com/kyleisah/Klipper-Adaptive-Meshing-Purging) | Intelligently limits your bed mesh and purge line to only the area your print occupies — speeds up start sequences and improves first-layer reliability on large beds. |
| [klipper_tmc_autotune](https://github.com/andrewmcgr/klipper_tmc_autotune) | Automatically calculates and applies optimal TMC stepper driver settings based on your motor specs — quieter operation, better torque, and reduced heat with minimal manual tuning. |
| [Klipper Estimator Plugin](https://github.com/Annex-Engineering/klipper_estimator) | A highly accurate print time estimator for Klipper — accounts for firmware limits and gives far more realistic time predictions than standard slicer previews. |
| [Klippain Shake&Tune](https://github.com/Frix-x/klippain-shaketune) | Streamlines the input shaper and resonance calibration workflow with automated measurement, graph generation, and analysis — takes the guesswork out of vibration tuning. |
| [Klicky Probe](https://github.com/jlas1/Klicky-Probe) | A popular magnetic microswitch probe system aimed at CoreXY printers — highly repeatable Z-probing with a robust magnetic dock-and-detach mechanism. |
| [Voron User Mods](https://github.com/VoronDesign/VoronUsers) | The official Voron community mods repo — user-contributed macros, Klipper configs, hardware mods, and slicer profiles for Voron and compatible machines. |
| [Kalico](https://github.com/KalicoCrew/kalico) | A feature-rich fork of Klipper with additional capabilities and experimental features baked in — ideal if you want bleeding-edge functionality without waiting for upstream Klipper merges. |
| [Beacon Klipper Module](https://github.com/beacon3d/beacon_klipper) | Official Klipper module for the Beacon eddy-current probe — enables ultra-fast, high-accuracy non-contact bed scanning and Z-offset calibration. |
| [Cartographer](https://github.com/cartographer-project/cartographer) | Real-time SLAM-based mapping technology that underpins the Cartographer probe — a high-speed eddy-current bed scanner similar to Beacon, offering rapid full-bed mesh generation with excellent repeatability. |
| [Updating Klipper and Mcu's](https://github.com/fbeauKmi/update_klipper_and_mcus) | A single bash script that updates Klipper and flashes all connected MCUs in one step — removes the hassle of manually reflashing each board after a Klipper update. |

---

## 🔧 Toolheads

Community-designed toolheads for Voron, CoreXY, and micro-format Klipper printers. All are open-source and Klipper-native.

| Toolhead | Compatible Printers | Highlights |
|---|---|---|
| [Voron Stealthburner](hardware/Toolheads.md#voron-stealthburner) | Voron 2.4, Trident, Switchwire | The official Voron toolhead — dual 5015 fans, CW2 extruder, Neopixels, TAP/Beacon support |
| [Xol Toolhead](hardware/Toolheads.md#xol-toolhead--armchair-heavy-industries) | Voron 2.4, Trident | Modular hotend & extruder system — swap hardware without full disassembly |
| [A4T](hardware/Toolheads.md#a4t--another-4010-toolhead) | Voron front-rail printers | Dual 4010 fans with CFD-optimised ducts — excellent part cooling, Neopixel LEDs |
| [AntHead](hardware/Toolheads.md#anthead--printersforants) | Micron, Stealth Forge, Pandora, Voron V0 | Purpose-built for micro-format printers — compact, light, configurable |
| [Reaper](hardware/Toolheads.md#reaper--apd-machine) | Voron front-rail printers | Widest hotend and extruder compatibility — dual 5015 fans, TAP/Beacon/Klicky |
| [K3 Mods](hardware/Toolheads.md#k3-mods--annex-k3-community-collection) | Annex Engineering K3 | Curated community upgrades — hotend swaps, Beacon probe, K3rabiner board configs |

→ **[Full Toolheads Guide with images and specs](hardware/Toolheads.md)**

---

## ⚙️ Hardware Guides

| Guide | What It Covers |
|---|---|
| [Nozzle Guide](hardware/Nozzle-Guide.md) | Brass vs hardened steel vs ruby vs tungsten, size guide, when to replace, hot swap procedure |
| [All-Metal Hotend Upgrade](hardware/All-Metal-Hotend.md) | PTFE-lined vs all-metal comparison, when you need the upgrade, popular options, heat creep management |
| [Enclosure Guide](hardware/Enclosure-Guide.md) | Requirement table by material with chamber temps, passive/active options, ventilation and filtration |

---

## 📚 Materials Table of Contents

| Material | Category | Difficulty | Temp Range | Enclosure | Chamber Temp |
|---|---|---|---|---|---|
| [PLA](materials/PLA.md) | Standard | ⭐ Beginner | 180–220°C | Not needed | — |
| [PETG](materials/PETG.md) | Standard | ⭐⭐ Intermediate | 230–250°C | Not needed | — |
| [ABS](materials/ABS.md) | Engineering | ⭐⭐ Intermediate | 230–250°C | **Required** | 45–50°C |
| [ASA](materials/ASA.md) | Engineering | ⭐⭐ Intermediate | 240–260°C | **Required** | 45–50°C |
| [TPU / Flexibles](materials/TPU.md) | Flexible | ⭐⭐ Intermediate | 220–240°C | Not needed | — |
| [Support Materials (PVA, HIPS)](materials/Support-Materials.md) | Support | ⭐⭐ Intermediate | Varies | HIPS: Required | — |
| [Nylon (PA)](materials/Nylon.md) | Engineering | ⭐⭐⭐ Advanced | 240–270°C | Recommended | — |
| [PC (Polycarbonate)](materials/PC.md) | High-Temp | ⭐⭐⭐ Advanced | 260–310°C | **Required** | 50–60°C |
| [Carbon Fibre & Glass Fibre Composites](materials/CF-Composites.md) | Composite | ⭐⭐⭐ Advanced | Varies | Base material dependent | Varies |
| [PVDF](materials/PVDF.md) | High-Performance Fluoropolymer | ⭐⭐⭐⭐ Expert | 245–265°C | Strongly recommended | — |
| [PEI / Ultem](materials/PEI.md) | High-Temp | ⭐⭐⭐⭐ Expert | 340–380°C | **Required** | 120–160°C |
| [PEKK](materials/PEKK.md) | High-Temp PAEK | ⭐⭐⭐⭐ Expert | 340–370°C | **Required** | 120–140°C |
| [PEEK](materials/PEEK.md) | High-Temp | ⭐⭐⭐⭐ Expert | 360–400°C | **Required** | 120–140°C |

---

## 🌡️ Temperature Quick Reference

```
PLA      ████░░░░░░░░░░░  180–220°C nozzle | 45–60°C bed
PETG     ██████░░░░░░░░░  230–250°C nozzle | 70–85°C bed  
ABS      ██████░░░░░░░░░  230–250°C nozzle | 100–110°C bed
ASA      ███████░░░░░░░░  240–260°C nozzle | 100–110°C bed
Nylon    ████████░░░░░░░  240–270°C nozzle | 70–85°C bed
PVDF     ████████░░░░░░░  245–265°C nozzle | 90–110°C bed
PC       █████████░░░░░░  260–310°C nozzle | 110–120°C bed
PEI      ████████████░░░  340–380°C nozzle | 120–160°C bed
PEEK     █████████████░░  360–400°C nozzle | 120–160°C bed
```

> ⚠️ High-temp materials (PC, PEI, PEEK, PVDF) require an **all-metal hotend**, high-temp bed surface, and ideally an **enclosed, actively heated chamber**.

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

## 🖥️ Slicer Options & Recommendations

Choosing the right slicer makes a big difference, especially with Klipper. The table below covers the most popular options, what firmware they support, and where to get them.

> ⭐ **Recommended: Orca Slicer** — the best all-round choice for Klipper users. It has native support for pressure advance, input shaping, adaptive bed meshing, and a huge library of community printer and filament profiles. Free and open source.

| Slicer | Klipper | Marlin | RepRapFirmware | Bambu | Best For | Download |
|---|---|---|---|---|---|---|
| [Orca Slicer](https://github.com/SoftFever/OrcaSlicer) ⭐ | ✅ Native | ✅ | ✅ | ✅ | Klipper & Bambu users — best-in-class calibration tools and profile library | [Download](https://github.com/SoftFever/OrcaSlicer/releases) |
| [PrusaSlicer](https://github.com/prusa3d/PrusaSlicer) | ✅ | ✅ | ✅ | ❌ | Prusa owners and a solid general-purpose slicer with great support | [Download](https://github.com/prusa3d/PrusaSlicer/releases) |
| [SuperSlicer](https://github.com/supermerill/SuperSlicer) | ✅ | ✅ | ✅ | ❌ | PrusaSlicer power users — adds extra tuning options including pressure advance and better Klipper integration | [Download](https://github.com/supermerill/SuperSlicer/releases) |
| [Bambu Studio](https://bambulab.com/en/download/studio) | ⚠️ Limited | ❌ | ❌ | ✅ | Bambu printer owners primarily — third-party Klipper support is basic | [Download](https://bambulab.com/en/download/studio) |
| [Cura](https://ultimaker.com/software/ultimaker-cura) | ⚠️ Via plugin | ✅ | ⚠️ | ❌ | Beginners and a wide range of FDM printers — large plugin ecosystem | [Download](https://ultimaker.com/software/ultimaker-cura) |
| [ideaMaker](https://www.raise3d.com/ideamaker) | ❌ | ✅ | ❌ | ❌ | Raise3D printer users | [Download](https://www.raise3d.com/ideamaker) |
| [Simplify3D](https://www.simplify3d.com) | ⚠️ Manual | ✅ | ✅ | ❌ | Users who want fine-grained control — paid software, no longer actively developed | [Download](https://www.simplify3d.com) |

> ⚠️ = Supported but requires manual configuration or plugins. ✅ = Native support out of the box.

## 💬 Community Chat & Support

Get connected with the people building, tuning, and pushing 3D printers further. These Discord communities are where real-world help happens — whether you're troubleshooting a failed print at midnight, looking for feedback on a mod, or just want to see what other people are building.

> 🔗 Click any server name to join. Most servers have dedicated help channels, showcase channels, and pinned resources from experienced community members.

### Printer Communities

| Community | Discord | About |
|---|---|---|
| **Voron Design** | [Join](https://discord.com/invite/voron) | The official home of the Voron project — 2.4, Trident, V0, Switchwire and more. One of the largest and most active 3D printing communities. Excellent help channels and a massive pool of experienced builders. |
| **Rat Rig** | [Join](https://discord.com/invite/ratrig) | Community server for Rat Rig V-Core and other Rat Rig printer owners. Help, mods, and build logs for this popular open-source CoreXY platform. |
| **VzBoT** | [Join](https://discord.com/invite/vzbot-829828765512106054) | Official community for the VzBot — a high-speed CoreXY printer designed to push print speeds to their limits. Active development and tuning discussion. |
| **ANNEX Engineering** | [Join](https://discord.com/invite/MzTR3zE) | Official server for Annex Engineering printer designs including the K3, K2, and other community machines. Direct access to the design team and community. |
| **DOOMCUBE** | [Join](https://discord.com/invite/doomcube) | Community for the Doomcube — a fully enclosed CoreXY printer designed for high-temp materials and serious engineering prints. |
| **Monolith** | [Join](https://discord.com/invite/monolith3d) | Home of the Monolith 3D printer community. Design discussion, build support, and mod sharing. |
| **Hyperdrive Design** | [Join](https://discord.com/invite/2e3dPyAdX) | Community for Hyperdrive Design printer builds and mods. |

### Toolhead & Hardware Communities

| Community | Discord | About |
|---|---|---|
| **Armchair Heavy Industries** | [Join](https://discord.com/invite/armchairengineeringsux) | The team behind the Xol Toolhead and A4T. Best place for support, development updates, and mod discussion for both toolheads. |

### Software & Firmware Communities

| Community | Discord | About |
|---|---|---|
| **Kalico** | [Join](https://discord.com/invite/6CK8AqK6tN) | Community for Kalico — the feature-rich Klipper fork with bleeding-edge capabilities. Support, feature requests, and development chat. |
| **Cartographer 3D** | [Join](https://discord.com/invite/EFSwpureHz) | Official support server for the Cartographer eddy-current probe. Setup help, firmware updates, and troubleshooting. |

### Content & General

| Community | Discord | About |
|---|---|---|
| **Luke's Laboratory** | [Join](https://discord.com/invite/9KjzuWHdFW) | Community around Luke's Lab — popular 3D printing content creator focused on Voron builds, Klipper tuning, and performance mods. Great place for general advice and discussion. |

---

## 🤝 Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) — community tips, corrections, and new material profiles are welcome!

---

## 📂 Repository Structure

```
3d-printing-ultimate-guide/
├── README.md                          <- You are here
├── materials/
│   ├── PLA.md
│   ├── PETG.md
│   ├── ABS.md
│   ├── ASA.md
│   ├── TPU.md
│   ├── Nylon.md
│   ├── PC.md
│   ├── PEI.md
│   ├── PEKK.md
│   ├── PEEK.md
│   ├── PVDF.md
│   ├── CF-Composites.md
│   └── Support-Materials.md
├── tuning/
│   ├── First-Layer-Calibration.md
│   ├── Temperature-Tower.md
│   ├── Pressure-Advance.md
│   ├── Retraction-Calibration.md
│   ├── Flow-Rate-Calibration.md
│   ├── Input-Shaping.md
│   └── PID-Tuning.md
├── troubleshooting/
│   ├── Stringing.md
│   ├── Warping.md
│   ├── Layer-Adhesion.md
│   ├── Clogged-Nozzle.md
│   ├── Moisture-Damage.md
│   ├── WiFi-Disconnecting.md
│   ├── General-Tips.md
│   └── Printer-Adjustment.md
├── post-processing/
│   ├── Sanding-Finishing.md
│   ├── Acetone-Smoothing.md
│   ├── Painting.md
│   └── Heat-Set-Inserts.md
├── hardware/
│   ├── Nozzle-Guide.md
│   ├── All-Metal-Hotend.md
│   ├── Enclosure-Guide.md
│   └── Toolheads.md
├── images/
│   └── (drop your images here)
└── CONTRIBUTING.md
```

---

*Last updated: 2026 | Licensed under CC BY-SA 4.0*
