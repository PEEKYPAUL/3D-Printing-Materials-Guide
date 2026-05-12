# 🔧 Troubleshooting — Warping

## What Is Warping?
Warping occurs when a print lifts off the bed or corners curl upward during printing. It's caused by **thermal contraction** — as a material cools, it shrinks. If different areas cool at different rates, internal stresses build up and the part deforms.

---

## Quick Diagnosis

| Symptom | Likely Cause |
|---|---|
| Corners lifting off bed | Classic warping — thermal stress |
| First layer curling at edges | Bed too cool or drafty environment |
| Layer separation mid-print | Thermal shock — enclosure needed |
| Large flat parts warping | Insufficient bed adhesion + shrinkage |

---

## Solutions by Material

### PLA
- Raise bed to **55–60°C**
- Add **brim** (5–8mm)
- Eliminate draughts around printer
- Check first layer squish

### PETG
- Raise bed to **80–85°C**
- Add brim
- Reduce cooling fan slightly
- Check for draught

### ABS / ASA
- **Enclose the printer** — this is the #1 fix
- Bed at **105–110°C**
- Large brim (10–15mm)
- **ABS slurry** on glass bed
- Enable **draft shield** in slicer
- Reduce cooling to 0%

### Nylon
- Garolite/G10 bed surface
- Enclose printer
- Brim 10+ mm
- Print dry filament

### PC / PEEK / PEI
- Actively heated chamber (50–120°C)
- Max bed temperature
- Maximum brim
- Pre-heat chamber before printing

---

## General Anti-Warp Strategies

1. **Brim** — adds surface area to anchor the print. Use 5–15mm depending on material.
2. **Enclosure** — eliminates cold draughts and maintains ambient temp.
3. **Mouse ears** — small circles at sharp corners, added in slicer or model, to resist corner lift.
4. **Draft shield** — sacrificial wall printed around the model (slicer feature).
5. **Bed adhesives** — glue stick, hairspray, ABS slurry, or material-specific adhesive (Magigoo).
6. **Slow first layers** — give adhesion time to set; use 25–50% speed for first 3 layers.
7. **Increase first layer height** — a squishier first layer bonds better.

---

# 🔧 Troubleshooting — Stringing

## What Is Stringing?
Thin hairs or "strings" of plastic between separate parts of a print. Caused by filament oozing from the nozzle during travel moves.

---

## Primary Causes & Fixes

| Cause | Fix |
|---|---|
| Temperature too high | Reduce nozzle temp 5°C at a time |
| Retraction too low | Increase retraction distance/speed |
| Travel speed too slow | Increase travel speed (180–250 mm/s) |
| Wet filament | Dry filament |
| Pressure advance not tuned | Tune PA/LA in firmware |

---

## Tuning Approach

1. **Start with temperature** — print a temp tower and identify the lowest clean temperature.
2. **Tune retraction** — print a retraction calibration test. Increase in 0.5mm steps.
3. **Enable "avoid crossing perimeters"** — forces travel moves to stay within the model.
4. **Increase travel speed** — fast travel gives filament less time to ooze.
5. **Tune pressure advance** — eliminates pressure build-up that causes ooze.

### Material-Specific Notes
- **PETG** strings more than most — this is normal. Combine all fixes above.
- **TPU** — disable retraction, use high travel speed, accept some stringing.
- **PLA** — usually easy to fix. Start with temp reduction.

---

# 🔧 Troubleshooting — Moisture Damage

## Signs of Wet Filament

| Sign | Severity |
|---|---|
| Crackling/popping sound from hotend | Moderate — dry now |
| Rough, bubbly surface finish | Moderate |
| Excessive stringing | Mild |
| Steam/vapour from nozzle | Severe |
| Dramatically reduced part strength | Severe |
| Brittle filament snapping on spool | Severe (Nylon especially) |

---

## Drying Guide by Material

| Material | Temp | Duration |
|---|---|---|
| PLA | 45–50°C | 4–6 hours |
| PETG | 65°C | 4–6 hours |
| ABS | 60–70°C | 4–6 hours |
| ASA | 60–70°C | 4–6 hours |
| TPU | 50–60°C | 4–6 hours |
| Nylon (PA) | 75–80°C | **8–12 hours** |
| PC | 80°C | 6–8 hours |
| PEI/Ultem | 120°C | 4–6 hours |
| PEEK | 120–150°C | 6+ hours |

> ⚠️ Standard food dehydrators often don't reach above 75°C. For high-temp materials, use a **lab oven** or **purpose-built filament dryer** (e.g. Bambu AMS dryer, Polymaker PolyDryer Box).

---

## Prevention

- **Vacuum seal** with desiccant after each session.
- Use **colour-indicating silica gel** — replace when it turns pink.
- A **hygrometer in storage box** lets you monitor humidity. Target below 20% RH.
- Print directly from a dryer box for hygroscopic materials (Nylon, PC, PEI, PEEK).

---

*← [Back to README](../README.md)*
