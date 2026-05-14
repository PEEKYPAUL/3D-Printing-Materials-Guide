# Toolheads — Community Designs for Klipper Printers

> A curated selection of community-designed toolheads for Voron, CoreXY, and micro-format printers. All are open-source and Klipper-native.

---

## Voron Stealthburner

[![Stealthburner](https://raw.githubusercontent.com/VoronDesign/Voron-Stealthburner/main/Images/Voron_Stealthburner.JPG)](https://github.com/VoronDesign/Voron-Stealthburner)

**[→ GitHub: VoronDesign/Voron-Stealthburner](https://github.com/VoronDesign/Voron-Stealthburner)**

The Stealthburner is the official toolhead for Voron 2.4 and Trident printers and is the most widely used community toolhead in existence. It replaced the older Afterburner design with improved aerodynamics, a cleaner cowl, integrated Neopixel LEDs, and better hotend accessibility. It uses the Clockwork 2 (CW2) extruder by default.

| Feature | Detail |
|---|---|
| **Compatible Printers** | Voron 2.4, Voron Trident, Switchwire |
| **Extruder** | Clockwork 2 (default) — third-party adapters available |
| **Part Cooling** | Dual 5015 blower fans |
| **Hotend Cooling** | Single 2510 axial fan |
| **Probe Support** | Voron TAP, Klicky, Beacon, Cartographer |
| **LEDs** | Integrated Neopixel status lighting |
| **License** | GPL-3.0 |

---

## Xol Toolhead — Armchair Heavy Industries

[![Xol Toolhead](https://raw.githubusercontent.com/Armchair-Heavy-Industries/Xol-Toolhead/main/docs/assets/images/Xol-Toolhead.both.png)](https://github.com/Armchair-Heavy-Industries/Xol-Toolhead)

**[→ GitHub: Armchair-Heavy-Industries/Xol-Toolhead](https://github.com/Armchair-Heavy-Industries/Xol-Toolhead)**

The Xol Toolhead is the evolution of the Mantis Xol 2 design, rebuilt from the ground up by Armchair Heavy Industries with a focus on modularity, installation quality of life, and serviceability. It is designed to be hotend and extruder agnostic, supporting a wide range of configurations through a modular mounting system.

| Feature | Detail |
|---|---|
| **Compatible Printers** | Voron 2.4, Voron Trident (front-rail carriages) |
| **Extruder** | Sherpa Mini, Orbiter 2.0, Wrist Watch BMG, and others |
| **Part Cooling** | Dual 4010 blower fans |
| **Hotend Support** | Dragon, Rapido, Revo Voron, Bambu and more via modular mounts |
| **Probe Support** | TAP, Beacon, Cartographer, Klicky PCB |
| **Design Focus** | Modularity and serviceability — swap hotends without full disassembly |
| **License** | CC BY-NC-SA 4.0 |

---

## A4T — Another 4010 Toolhead

[![A4T Render](https://raw.githubusercontent.com/Armchair-Heavy-Industries/A4T/main/docs/images/A4T_render.png)](https://github.com/Armchair-Heavy-Industries/A4T)

**[→ GitHub: Armchair-Heavy-Industries/A4T](https://github.com/Armchair-Heavy-Industries/A4T)**

The A4T (Another 4010 Toolhead) is a ground-up design by DW-Tas, built specifically around dual 4010 blower fans with CFD-optimised ducts for exceptional part cooling. It prioritises easy assembly with integrated support structures and features Neopixel LEDs positioned for excellent print visibility. Originally developed around the Dragon HF hotend with an extender configuration.

| Feature | Detail |
|---|---|
| **Compatible Printers** | Voron front-rail printers — Xol-Carriage, TAP carriage, CW2 carriage |
| **Extruder** | Wrist Watch BMG, Sherpa Mini, Orbiter 2.0 |
| **Part Cooling** | Dual 4010 blower fans — CFD validated |
| **Hotend Cooling** | 2510 axial fan |
| **Hotend Support** | Dragon HF/UHF, Rapido HF/UHF, Chube Compact, Bambu, and others |
| **Probe Support** | TAP, Beacon (note: not Cartographer CNC carriage without modification) |
| **LEDs** | Integrated Neopixel — positioned for print illumination |
| **License** | CC BY-NC-SA 4.0 |

---

## AntHead — PrintersForAnts

[![AntHead](https://github.com/user-attachments/assets/aeba7a5b-7b23-4ddc-95bf-e3ce7ebd24ae)](https://github.com/PrintersForAnts/AntHead)

**[→ GitHub: PrintersForAnts/AntHead](https://github.com/PrintersForAnts/AntHead)**

The AntHead is a purpose-built toolhead for micro-format printers — primarily the Micron, Stealth Forge, and Pandora — while also supporting larger 2020-based printers with appropriate carriages. It follows the same design philosophy as the full-size community toolheads but scaled and optimised for the unique constraints of mini-format CoreXY machines. A Printed Part Configurator simplifies choosing the right combination of extruder and hotend.

| Feature | Detail |
|---|---|
| **Compatible Printers** | Micron, Stealth Forge, Pandora (primary) — Voron V0, V2, Trident with adapters |
| **Extruder** | BMG kit, G2 extruder kit |
| **Part Cooling** | Dual 4010 blower fans |
| **Hotend Cooling** | 2510 axial fan |
| **Hotend Support** | Dragon-compatible, Revo Voron, Rapido, TZV6, Dragon Ace, ReVolcano |
| **Design Focus** | Micro-format optimised — low mass, compact footprint |
| **Extras** | Printed Part Configurator tool, LED logo variants |
| **License** | Open source |

---

## Reaper — APD Machine

[![Reaper Toolhead](https://github.com/APDMachine/Reaper/assets/5345379/0867423c-27bd-4cb8-a8d3-a0b3279f5672)](https://github.com/APDMachine/Reaper)

**[→ GitHub: APDMachine/Reaper](https://github.com/APDMachine/Reaper)**

The Reaper is a community-maintained toolhead inspired by the original Mantis design. It uses a 3010 hotend cooling fan paired with dual 5015 blower fans for part cooling, and supports an exceptionally wide range of hotends and extruders — making it a strong choice for builders who want maximum hardware flexibility. The project is community-driven with active Discord support.

| Feature | Detail |
|---|---|
| **Compatible Printers** | Voron-style front-rail printers |
| **Extruder** | Balrog, Sherpa Mini, Orbiter V2, Hextrudort, LGX Lite, Hummingbird, G2SA |
| **Part Cooling** | Dual 5015 blower fans |
| **Hotend Cooling** | 3010 fan |
| **Hotend Support** | Dragon series, Rapido, Dropeffect NextG, Mosquito, Bambu, Revo Voron |
| **Probe Support** | TAP, Beacon, Cartographer, Klicky PCB |
| **Design Focus** | Maximum hotend and extruder compatibility |
| **License** | Community open source |

---

## K3 Mods — Annex K3 Community Collection

**[→ GitHub: everycoloryouare/K3_Mods](https://github.com/everycoloryouare/K3_Mods)**

A curated community collection of modifications and toolhead configurations for the **Annex Engineering K3** printer — a high-speed, enclosed CoreXY machine. Rather than a single toolhead design, this repository aggregates the best community-contributed upgrades covering hotend swaps, cooling solutions, extruder modifications, and structural improvements. It also includes Klipper configuration guidance and pinout documentation for the K3rabiner toolhead board.

| Feature | Detail |
|---|---|
| **Target Printer** | Annex Engineering K3 |
| **Hotend Options** | Dragon, Rapido, Chube Compact |
| **Extruder Options** | Sherpa series variants |
| **Probe Support** | Beacon eddy-current probe (featured prominently) |
| **Extras** | K3rabiner toolhead board pinouts, alignment tools, Klipper configs |
| **Design Focus** | Curated community upgrades — not a single design |
| **License** | Various per mod |

---

*← [Back to README](../README.md)*
