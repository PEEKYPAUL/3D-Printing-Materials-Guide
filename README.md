# 🖨️ 3D Printing — Ultimate Guide

> The all-in-one reference for FDM/FFF 3D printing. Covering everything from printer tuning and troubleshooting to post-processing, Klipper software & plugins, hardware upgrades, and filament materials — whether you're a beginner dialling in your first PLA print or running exotic high-temperature engineering filaments.

---

## 🎯 Tuning Guides

| Guide | What It Covers |
|---|---|
| [Build Surface Prep](tuning/Build-Surface-Prep.md) | Washing, handling, scuffing PEI, IPA maintenance, adhesion aids — start here before any first-layer tuning |
| [First Layer Calibration](tuning/First-Layer-Calibration.md) | Open Orca Slicer, print an 80×80mm square, dial in Z offset and flow ratio |
| [Extruder Calibration](tuning/Extruder-Calibration.md) | Verify 100mm requested = 100mm delivered — rotation_distance for Klipper, e-steps for Marlin |
| [Temperature Tower](tuning/Temperature-Tower.md) | Find the optimal nozzle temperature for any filament using Orca Slicer's built-in calibration |
| [Pressure Advance](tuning/Pressure-Advance.md) | Eliminate corner bulging and improve sharp detail with PA/LA calibration |
| [Retraction Calibration](tuning/Retraction-Calibration.md) | Reduce stringing and oozing by dialling in retraction distance and speed |
| [Flow Rate Calibration](tuning/Flow-Rate-Calibration.md) | Measure actual extrusion width and correct your flow ratio with a single-wall cube |
| [Cooling & Layer Times](tuning/Cooling-Layer-Times.md) | Fan speed by material, minimum layer time, chamber temperature scaling, overhang-specific cooling |
| [Input Shaping](tuning/Input-Shaping.md) | Reduce ringing and ghosting artefacts — ADXL345 setup, resonance testing, belt comparison, and applying results to printer.cfg |
| [PID Tuning](tuning/PID-Tuning.md) | Stabilise hotend and bed temperatures — tune under real print conditions for accurate results |
| [Max Volumetric Flow Rate](tuning/Max-Volumetric-Flow.md) | Find your hotend's real melt capacity in mm³/s — the formula, test method, and how to set limits in your slicer |
| [Max Speed & Acceleration](tuning/Max-Speed-Acceleration.md) | Find your printer's motion limits safely using TEST_SPEED — acceleration first, then speed, with position verification |
| [Infill / Perimeter Overlap](tuning/Infill-Perimeter-Overlap.md) | Close pinholes at infill-perimeter junctions — disconnected top infill and overlap value adjustment |

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
| [Voron V2 Gantry Squaring](troubleshooting/Voron-Gantry-Squaring.md) | Square the gantry mechanically before relying on QGL — Z joint alignment, de-racking, belt tension, heat soak, and final hot tightening |
| [Belt Tension — XY & Z](troubleshooting/Belt-Tension.md) | Target frequencies and forces for AB and Z belts, phone app and Diyshift tension meter measurement methods, symptoms table, and when to re-check |
| [Printer Adjustment — Skew & Scale](troubleshooting/Printer-Adjustment.md) | Fix XY skew and dimensional scale errors using the Califlower calibration tool — covers Klipper, Marlin, and slicer correction |

---

## ✨ Post-Processing Guides

| Guide | What It Covers |
|---|---|
| [Sanding & Finishing](post-processing/Sanding-Finishing.md) | Grit progression, filler primer guide coat, wet sanding, final finish options |
| [Acetone Smoothing](post-processing/Acetone-Smoothing.md) | ABS/ASA cold vapour and direct wipe methods, safety, timing guide |
| [Painting Prints](post-processing/Painting.md) | Surface prep, primer types, base coat technique, hobby acrylics, clear coat |
| [Heat-Set Inserts](post-processing/Heat-Set-Inserts.md) | Hole sizing table (M2–M5), iron temps by material, installation process, common mistakes |
| [PEEK Annealing](post-processing/PEEK-Annealing.md) | Sand burial method, oven ramp rates, hold times, cooling process — unlock full semi-crystalline PEEK performance |

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
| [Automatic Config Backup](klipper/Automatic-Backup.md) | Step-by-step guide to automatically backing up your Klipper config to a private GitHub repository — file-change detection, scheduled backups, and restore instructions. |

---

## ⚙️ Klipper Macros

Ready-to-use macros covering the essentials — from a solid PRINT_START to parking, filament handling, speed testing, and debug tools. All Klipper only.

| Guide | What It Covers |
|---|---|
| [PRINT_START & PRINT_END](macros/Print-Start-End.md) | A proper start/end macro setup — slicer passthrough, pre-heat logic, mesh, purge line, and safe park on finish |
| [Pause, Resume & Filament Handling](macros/Pause-Resume-Filament.md) | Z-hop pause, toolhead park, hotend shutdown, filament swap, resume with prime — plus switch and smart motion sensor setup |
| [Parking Macros](macros/Parking.md) | Five named park positions — front, front-low, rear, centre, bed — all auto-scaled to your printer's axis limits |
| [Conditional Homing & QGL](macros/Conditional-Homing.md) | `_CG28` and `_CQGL` — home and level only when needed, not every time a macro runs |
| [Temperature Overrides](macros/Temperature-Overrides.md) | Replace M109/M190 with `TEMPERATURE_WAIT` — smarter heating with range-based triggers instead of exact-value blocking |
| [Beeper](macros/Beeper.md) | PWM and non-PWM beeper control — variable pitch, duration, and repeat count for audio feedback from any macro |
| [Utility Macros](macros/Utilities.md) | `OFF` for clean shutdown, `TEST_SPEED` for finding your speed limits, `DUMP_VARIABLES` for debugging, `LCD_RGB` for display colour |

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
| [PPS / PPS-GF / PPS-CF](materials/PPS.md) | High-Temp Engineering | ⭐⭐⭐⭐ Expert | 280–330°C | **Required** | 80–120°C |
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
TPU      █████░░░░░░░░░░  220–240°C nozzle | 30–60°C bed
Nylon    ████████░░░░░░░  240–270°C nozzle | 70–85°C bed
PVDF     ████████░░░░░░░  245–265°C nozzle | 90–110°C bed
PC       █████████░░░░░░  260–310°C nozzle | 110–120°C bed
PPS      ██████████░░░░░  280–310°C nozzle | 120–140°C bed
PEI      ████████████░░░  340–380°C nozzle | 120–160°C bed
PEKK     ███████████░░░░  340–370°C nozzle | 120–160°C bed
PEEK     █████████████░░  360–400°C nozzle | 120–160°C bed
```

> ⚠️ High-temp materials (PC, PPS, PEI, PEKK, PEEK, PVDF) require an **all-metal hotend**, high-temp bed surface, and ideally an **enclosed, actively heated chamber**.

---

## 🔬 Printer Requirements by Category

Use this table as a guide when choosing hardware or checking whether your printer can handle a material. Each column represents a tier of material difficulty.

| Requirement | Standard (PLA / PETG) | Engineering (ABS / ASA / Nylon) | High-Temp (PC / PPS / PEI / PEKK / PEEK) |
|---|---|---|---|
| **Hotend** | PTFE-lined OK | All-metal preferred | **All-metal required** |
| **Max Nozzle Temp** | 250°C | 280°C | **400°C+** |
| **Heated Bed** | 45–85°C | 100–115°C | **120–160°C** |
| **Enclosure** | Not needed | Strongly recommended | **Required** |
| **Chamber Temp** | Ambient | 40–50°C (passive OK) | **120–140°C (active heating required)** |
| **Hardened Nozzle** | Optional | Recommended for CF/GF blends | **Required for CF / abrasive fills** |
| **Nozzle Diameter** | 0.4 mm standard | 0.4–0.6 mm | 0.4–0.6 mm (larger = better flow) |
| **Part Cooling Fan** | High — 50–100% | Low — 0–30% (ABS/ASA 0%) | None — **0% always** |
| **Max Volumetric Flow** | 10–20 mm³/s (standard hotend) | 8–15 mm³/s | 3–8 mm³/s (print slowly) |
| **Typical Print Speed** | 50–200 mm/s | 30–80 mm/s | **15–30 mm/s** |
| **Filament Drying** | PLA optional — PETG recommended | **Required** — 70–80°C, 4–6 h | **Required** — 100–150°C, 6–12 h |
| **Bed Surface** | PEI, textured PEI, glass | PEI (smooth), Garolite (Nylon) | PEI + specialist adhesive (Vision Miner) |
| **Min Layer Height** | 0.1 mm | 0.15 mm | 0.15–0.2 mm |
| **Typical Wall Count** | 2–4 | 3–5 | 4–6 |
| **Typical Infill** | 15–40% | 25–50% | 40–80% |

> ⚠️ **High-temp materials (PC, PPS, PEI, PEKK, PEEK)** demand a fully enclosed, actively heated chamber. Attempting these on a stock printer without enclosure and chamber heating will result in warping, delamination, and failed prints.

### Flow Rate & Fan Speed — Quick Reference

Flow ratio is the multiplier applied to your extruder's output — 1.00 is the baseline. Most materials print well between 0.95 and 1.05. Tuning flow ratio compensates for filament diameter variation, hotend behaviour, and material viscosity differences. Always calibrate flow ratio per filament after dialling in temperature.

| Material | Part Cooling Fan | Flow Ratio | Notes |
|---|---|---|---|
| PLA | 80–100% | 0.95–1.00 | Needs cooling — high fan is fine |
| PETG | 20–50% | 0.95–1.00 | Too much fan causes layer adhesion issues |
| ABS | 0–10% | 0.98–1.02 | No fan — delamination risk |
| ASA | 0–10% | 0.98–1.02 | No fan — same risk as ABS |
| TPU | 30–80% | 1.00–1.05 | Soft grades (75A–85A) need more cooling; harder grades (95A+) need less |
| Nylon | 0–20% | 0.98–1.02 | Minimal fan; higher for PA12 than PA6 |
| PC | 0–20% | 1.00–1.05 | 0% for pure PC; up to 20% for PC blends — no more |
| PPS | 0% | 1.00–1.05 | Chemical-resistant — no fan, actively heated chamber required |
| PPS-GF | 0% | 1.00–1.05 | Glass-filled — hardened steel nozzle, higher HDT than unfilled |
| PPS-CF | 0% | 1.00–1.05 | Carbon-filled — ruby nozzle required, highest stiffness |
| PEI / Ultem | 0% | 1.00–1.05 | Extreme-temp only — no fan |
| PEKK | 0% | 1.00–1.05 | Print at 15–25 mm/s max |
| PEEK | 0% | 1.00–1.05 | Slowest of all — 15–20 mm/s typical |

---

### Strength Settings by Material

Wall count, top/bottom layers, infill pattern, and infill density all have a larger impact on part strength than print speed or temperature. These are recommended starting points — adjust up for structural parts, down for prototypes and display models.

> 💡 **Walls contribute more to strength than infill** for most functional parts. Adding walls is more effective than increasing infill percentage — 4 walls at 20% infill is stronger in most load cases than 2 walls at 50% infill.

| Material | Walls | Top / Bottom Layers | Infill Pattern | Infill % | Notes |
|---|---|---|---|---|---|
| PLA | 3–4 | 4–5 | Grid / Gyroid | 15–25% | General use. Gyroid for isotropic strength, grid for speed |
| PETG | 3–4 | 4–5 | Grid / Gyroid | 20–30% | Slightly more walls than PLA for better layer bonding |
| ABS | 4 | 5 | Grid / Gyroid | 20–40% | More infill compensates for lower layer adhesion vs PLA |
| ASA | 4 | 5 | Grid / Gyroid | 20–40% | Same as ABS — UV stable, use for outdoor parts |
| TPU | 3–4 | 4 | Gyroid / Concentric | 15–30% | Gyroid gives best flex behaviour — avoid rectilinear in flex parts |
| Nylon | 4–5 | 5–6 | Gyroid / Grid | 30–50% | High wall count critical — nylon inter-layer adhesion is excellent |
| PC | 4–5 | 5–6 | Gyroid / Grid | 40–60% | Maximum layer bonding matters more than infill — prioritise walls |
| PPS | 4–6 | 5–6 | Grid / Gyroid | 40–60% | Chemical resistance is in the material — strength from walls |
| PPS-GF | 4–6 | 5–6 | Grid | 40–60% | GF filled — grid infill handles fibre orientation better |
| PPS-CF | 4–6 | 5–6 | Grid | 40–60% | CF filled — avoid gyroid, fibres align better on rectilinear paths |
| PEI / Ultem | 5–6 | 6 | Grid / Gyroid | 50–80% | Extreme temp structural parts — maximum walls, high infill |
| PEKK | 5–6 | 6 | Grid / Gyroid | 50–80% | Same philosophy as PEI — walls first, infill second |
| PEEK | 5–6 | 6 | Grid / Gyroid | 50–80% | Anneal after printing for full strength — see PEEK Annealing guide |

#### Infill Pattern Reference

| Pattern | Strength | Speed | Best For |
|---|---|---|---|
| **Gyroid** | Isotropic — equal in all directions | Moderate | Functional parts with mixed load directions, flexible materials |
| **Grid** | Strong in XY, moderate in Z | Fast | General use — good balance of speed and strength |
| **Honeycomb** | Good XY, moderate Z | Moderate | Lightweight structural parts |
| **Rectilinear / Lines** | Directional | Fastest | Prototypes, non-structural parts, fibre-filled materials |
| **Cubic / 3D Honeycomb** | Good in all directions | Slow | High-strength structural parts where Z load matters |
| **Triangle** | Excellent XY — rigid and stiff | Moderate | High-load structural parts, brackets, and anything needing maximum in-plane rigidity |
| **Concentric** | Follows perimeter shape | Fast | Flexible materials — flex deforms along the lines |

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
| **Klipper** | [Join](https://discord.klipper3d.org) | The official Klipper firmware Discord — configuration help, macro support, bug reports, and development discussion direct from the community behind Klipper itself. |
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
| **Mainsail** | [Join](https://discord.com/invite/mainsail) | Official server for Mainsail — the Klipper web interface. Setup help, theming, feature requests, and support from the development team. |
| **OrcaSlicer** | [Join](https://discord.com/invite/P4VE9UY9gJ) | Official OrcaSlicer community — slicer help, profile sharing, calibration discussion, and feature feedback direct to the development team. |
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
├── LICENSE
├── CODE_OF_CONDUCT.md
├── CONTRIBUTING.md
├── SECURITY.md
├── .github/
│   ├── pull_request_template.md
│   └── ISSUE_TEMPLATE/
│       ├── config.yml
│       ├── incorrect-information.md
│       └── content-suggestion.md
├── materials/
│   ├── PLA.md
│   ├── PETG.md
│   ├── ABS.md
│   ├── ASA.md
│   ├── TPU.md
│   ├── Nylon.md
│   ├── PC.md
│   ├── PPS.md
│   ├── PEI.md
│   ├── PEKK.md
│   ├── PEEK.md
│   ├── PVDF.md
│   ├── CF-Composites.md
│   └── Support-Materials.md
├── tuning/
│   ├── Build-Surface-Prep.md
│   ├── First-Layer-Calibration.md
│   ├── Extruder-Calibration.md
│   ├── Temperature-Tower.md
│   ├── Pressure-Advance.md
│   ├── Retraction-Calibration.md
│   ├── Flow-Rate-Calibration.md
│   ├── Cooling-Layer-Times.md
│   ├── Input-Shaping.md
│   ├── PID-Tuning.md
│   ├── Max-Volumetric-Flow.md
│   ├── Max-Speed-Acceleration.md
│   └── Infill-Perimeter-Overlap.md
├── macros/
│   ├── Print-Start-End.md
│   ├── Pause-Resume-Filament.md
│   ├── Parking.md
│   ├── Conditional-Homing.md
│   ├── Temperature-Overrides.md
│   ├── Beeper.md
│   └── Utilities.md
├── troubleshooting/
│   ├── Stringing.md
│   ├── Warping.md
│   ├── Layer-Adhesion.md
│   ├── Clogged-Nozzle.md
│   ├── Moisture-Damage.md
│   ├── WiFi-Disconnecting.md
│   ├── General-Tips.md
│   ├── Printer-Adjustment.md
│   ├── Voron-Gantry-Squaring.md
│   └── Belt-Tension.md
├── post-processing/
│   ├── Sanding-Finishing.md
│   ├── Acetone-Smoothing.md
│   ├── Painting.md
│   ├── Heat-Set-Inserts.md
│   └── PEEK-Annealing.md
├── hardware/
│   ├── Nozzle-Guide.md
│   ├── All-Metal-Hotend.md
│   ├── Enclosure-Guide.md
│   └── Toolheads.md
├── klipper/
│   └── Automatic-Backup.md
├── images/
│   └── (drop your images here)
```

---

*Last updated: 2026 | Licensed under CC BY-SA 4.0*
