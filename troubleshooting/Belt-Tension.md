# Belt Tension — XY and Z

> **Applies to:** Voron 2.4, Trident, and CoreXY printers generally | **Difficulty:** ⭐⭐ Beginner | **Check this when:** Ringing / ghosting, layer shifting, inconsistent QGL, or after any belt replacement

---

## Why Belt Tension Matters

Belts that are too loose cause the toolhead to wobble during direction changes — this shows up as ringing artefacts, ghosting, and layer shifts. Belts that are too tight accelerate wear on the drive gears, idler bearings, and motor shafts, and can actually make ringing worse by raising the resonant frequency into the range your printer operates at.

Getting belt tension right — and keeping A and B equal to each other — is one of the highest-impact mechanical adjustments on a CoreXY printer. It directly affects print quality and the validity of input shaping results.

---

## Target Tensions

### XY / A-B Belts (CoreXY Motion System)

| Target | Value |
|---|---|
| Frequency (150mm span) | **110 Hz** |
| Approximate force | ~2 lbf / ~9 N |

110 Hz is the Voron-recommended starting point — it's on the lower end of the acceptable range, which keeps belt stress manageable while still providing solid toolhead control. Both A and B belts must match each other as closely as possible. Uneven tension between them causes diagonal print artefacts and affects CoreXY motion accuracy.

### Z Belts (Voron 2.4)

| Target | Value |
|---|---|
| Frequency (150mm span) | **140 Hz** |

Z belts run under higher static load because they're supporting the gantry weight, so they're tensioned slightly tighter than the XY belts. All four Z belts should be as equal as possible to each other — uneven Z belt tension is a common cause of QGL corrections being inconsistent from run to run.

---

## How to Measure

There are two approaches — a phone app for a quick check, and a printed mechanical tension meter for precise, repeatable measurements.

### Method 1 — Phone App (Frequency)

![Phone app showing belt frequency spectrum — 110Hz peak highlighted for AB belt](../images/belt-tension-01-phone-app.jpg)

1. Position the toolhead so you have a clear **150mm span** of belt between idler centres
2. Pluck the belt like a guitar string — a short, firm pluck gives the cleanest reading
3. Hold the phone mic close to the belt and read the peak frequency

**Recommended apps:**

| App | Platform | Notes |
|---|---|---|
| Gates Carbon Drive | iOS & Android | Shows single dominant frequency — easiest to read |
| Spectroid | Android | Full spectrum graph — shows all harmonics |
| Sound Spectrum Analysis | iOS | Full spectrum graph — good for seeing belt health |

The Gates app is the simplest — it gives you one number. The spectrum apps are more informative: a clean belt produces a single clean peak. Multiple peaks or a broad spread can indicate a worn, kinked, or unevenly tensioned belt.

> ⚠️ **The 150mm span is the reference distance.** Measuring over a different span gives a different frequency for the same tension. Always use the same reference distance each time you check, and be consistent between A and B belts.

---

### Method 2 — GT2 Belt Tension Meter (Recommended)

![GT2 Belt Tension Meter by Diyshift mounted on an AB belt showing dial reading](../images/belt-tension-02-tension-meter.jpg)

For repeatable, tool-based measurements that don't depend on phone placement or acoustic environment, the **GT2 Belt Tension Meter by Diyshift** is the recommended tool.

**[→ Diyshift GT2 Belt Tension Meter — GitHub](https://github.com/Diyshift/3D-Printer/tree/main/GT2%20Belt%20Tension%20Meter)**

This is a 3D-printed mechanical deflection meter that physically presses on the belt and reads the tension via a needle and dial — no phone, no apps, no acoustic interference. Accuracy is approximately ±1.0N on a carefully built unit.

**Compatibility:** Voron 2.4, Trident, V0, Salad Fork, Switchwire — requires at least 150mm of accessible belt span.

**Print settings for the meter itself:**

| Setting | Value |
|---|---|
| Material | ABS or ASA — required for dimensional accuracy |
| Layer height | 0.2mm |
| Infill | 40% grid |
| Perimeters | 4 |
| Top / bottom layers | 5 |
| Nozzle | 0.4mm |

> ⚠️ The needle and slide gear teeth must have **no seams** on the functional surfaces. Orient these parts accordingly in your slicer before printing.

**Hardware required:**

| Part | Qty |
|---|---|
| M3×7 button head cap screw | 1 |
| M3×25 socket head cap screw | 1 |
| M3×8×0.6mm washer | 1 |
| M2×10 self-tapping screws | 2 |
| 0.81mm × 100mm tempered steel music wire | 1 |
| 6mm OD compression spring (0.35 N/mm, 50mm free length) | 1 |

Pre-assembled meters and hardware kits are available from vendors in the UK, US, Europe, and Australia — check the GitHub page for current stockists.

#### Using the Meter

![Measurement position — meter depressed and placed on belt at 150mm span](../images/belt-tension-03-meter-position.jpg)

1. Printer should be **cold** — belt tension changes when the printer is hot
2. Centre the toolhead so idler centres are **150mm apart**
3. Depress the plunger fully and place the meter jaws on the belt
4. Slowly release the plunger and let the needle settle
5. Read the dial value
6. Repeat **three times** and average the readings — consistency between readings confirms the belt is straight and the meter is calibrated

**Dial target values:**

| Belt type | Target reading |
|---|---|
| Standard GT2 rubber belt | **2.1** |
| EPDM high-temp belt | **2.2** |

---

## Measuring AB Belt Locations

![AB belt tensioner location on Voron 2.4 — front of the gantry showing A and B tensioner blocks](../images/belt-tension-04-ab-tensioners.jpg)

On a Voron 2.4 or Trident, the A and B belt tensioner blocks sit at the front of the gantry. Access the belt span between the front idlers and the XY joint on each side. Both sides should be measured and tensioned to match before re-running input shaping.

**Iterative tensioning:** Because the A and B belts share the drive system, tightening one affects the other slightly. Tension A, then check B, then re-check A. Repeat until both read equal — usually 2–3 rounds.

---

## Measuring Z Belt Locations

![Z belt tensioner locations on Voron 2.4 — four corners of the lower gantry](../images/belt-tension-05-z-tensioners.jpg)

The four Z belt tensioners sit at the bottom corners of the frame on a Voron 2.4. Each drives one of the four Z motors. Measure each belt individually over a consistent 150mm span where accessible — the exact position matters less than using the same position each time you re-check.

All four should match. Z belts are typically tensioned with the gantry sitting at mid-height so there's enough accessible span to measure.

---

## Symptoms by Problem

| Symptom | Likely Cause |
|---|---|
| Ringing / ghosting in X direction | A or B belt loose, or unequal between A and B |
| Ringing / ghosting in Y direction | A or B belt loose, or unequal between A and B |
| Layer shifting under fast moves | Belt too loose — slipping under acceleration |
| Increased ringing after tightening | Belt now over-tensioned — back off slightly |
| QGL corrections inconsistent run to run | Z belts unequal — re-tension all four to match |
| Grinding or squealing from idlers | Over-tensioned — idler bearings under excessive load |
| Belt skipping teeth under load | Way too loose, or belt has stretched significantly — replace |
| Print quality suddenly worse after a long run | Belt has relaxed — re-check tension after first 20–30 hours on new belts |

---

## When to Re-Check Tension

| Situation | Re-check? |
|---|---|
| New printer build | ✅ Yes — new belts stretch in the first hours of use |
| After first 20–30 print hours | ✅ Yes — new belts settle |
| After any belt replacement | ✅ Yes |
| After gantry disassembly | ✅ Yes |
| After input shaping (if results seem off) | ✅ Yes — tension affects resonance results |
| After re-running gantry squaring | ✅ Yes — belts were backed off during the process |
| Routine check (every few months) | ✅ Recommended |

> 💡 **Always re-run input shaping after adjusting belt tension.** Belt tension changes the resonant frequency of the system — your shaper values are only valid at the tension they were calibrated at.

---

## Related Guides

- [Voron V2 Gantry Squaring](Voron-Gantry-Squaring.md) — belt tension is backed off during gantry squaring and must be re-set afterwards
- [Input Shaping](../tuning/Input-Shaping.md) — re-run after any belt tension change

---

*Back to [Troubleshooting Guides](../README.md#️-troubleshooting-guides) | [README](../README.md)*
