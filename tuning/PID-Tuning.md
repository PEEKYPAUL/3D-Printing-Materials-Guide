# PID Tuning — Hotend & Bed (Klipper)

> Stable temperatures are the foundation of consistent prints. PID tuning teaches Klipper exactly how your hotend and bed heat up and hold temperature, eliminating the swings and overshoots that cause inconsistent extrusion and poor layer adhesion.

---

## What Is PID Tuning?

PID stands for **Proportional, Integral, Derivative** — three values that together control how aggressively Klipper drives power to your heaters to reach and hold a target temperature.

Without proper PID values, your hotend or bed will either:
- **Overshoot** — spike well above the target before settling, stressing components and risking thermal runaway
- **Undershoot and oscillate** — never quite reaching the target, causing temperature swings during printing

A well-tuned PID keeps the temperature rock-steady within ±0.5°C during a print.

---

## Before You Start

### Set Up Your Environment Realistically

This is the most important tip most guides skip: **tune under conditions that match real printing**.

- **Turn your part cooling fan on** at the speed you normally print with for that filament — typically 50–100% for PLA, 20–30% for PETG, 0% for ABS/ASA. The fan blows cold air directly across the hotend and significantly affects how hard the heater has to work to maintain temperature. Tuning with the fan off and then printing with it on will give you a poorly fitted PID result.
- **Position the nozzle close to the bed** — within 5–10 mm — before running the hotend tune. The heated bed radiates warmth upward and affects the thermal environment around the hotend during real prints. Replicating this during calibration gives a more accurate result.
- **Heat the bed to your normal printing temperature** before tuning the hotend. For the same reason as above — the bed's heat influences the hotend's thermal environment and should be present during the tune.

> 💡 Think of it this way: you want Klipper to learn how your hotend behaves in the exact conditions it will face during a real print — not in an empty, cold, fan-off environment.

---

## Part 1 — Hotend PID Tuning

### Step 1 — Prepare the Printer

1. Home all axes
2. Move the nozzle close to the bed — approximately **5–10 mm above the bed surface**
3. Heat the bed to your normal printing temperature (e.g. 60°C for PLA, 100°C for ABS)
4. Turn the part cooling fan on to the speed you normally use for this filament:

```gcode
M106 S128   ; 50% fan — adjust to your typical print fan speed
            ; S255 = 100%, S128 = 50%, S77 = 30%, S0 = off
```

Wait for the bed to fully reach temperature before proceeding.

### Step 2 — Run Hotend PID Tune

From the Mainsail or Fluidd console, run:

```gcode
PID_CALIBRATE HEATER=extruder TARGET=200
```

Replace `200` with **your actual printing temperature** for the filament you use most — for example `220` for PETG or `240` for ABS. Klipper will run several heat cycles automatically, which takes 3–5 minutes.

When complete you will see output similar to:

```
// PID parameters: pid_Kp=21.304 pid_Ki=1.212 pid_Kd=93.721
```

### Step 3 — Save the Result

Run the following to write the values into `printer.cfg`:

```gcode
SAVE_CONFIG
```

Klipper will restart automatically. The new PID values will appear at the bottom of `printer.cfg` under a `#*# [extruder]` block like this:

```ini
#*# [extruder]
#*# control = pid
#*# pid_kp = 21.304
#*# pid_ki = 1.212
#*# pid_kd = 93.721
```

> ⚠️ Do not manually edit the `#*#` section at the bottom of `printer.cfg` — Klipper manages this block automatically. Edit the main `[extruder]` section if you need to make manual changes.

---

## Part 2 — Bed PID Tuning

Klipper uses bang-bang control for the bed by default (simply switching the heater fully on or off). Switching to PID control gives a much more stable bed temperature, which improves first layer consistency — especially important for materials sensitive to temperature fluctuation like PETG and ABS.

### Step 1 — Enable PID Control for the Bed

In your `printer.cfg`, find the `[heater_bed]` section and change `control` from `watermark` (bang-bang) to `pid`:

```ini
[heater_bed]
heater_pin: PA3
sensor_type: EPCOS 100K B57560G104F
sensor_pin: PF3
min_temp: 0
max_temp: 130
control: pid          # change from watermark to pid
pid_kp: 54.027        # placeholder — will be replaced by SAVE_CONFIG
pid_ki: 0.770         # placeholder — will be replaced by SAVE_CONFIG
pid_kd: 947.220       # placeholder — will be replaced by SAVE_CONFIG
```

Do a **firmware restart** before running the tune.

### Step 2 — Run Bed PID Tune

From the console, run:

```gcode
PID_CALIBRATE HEATER=heater_bed TARGET=60
```

Replace `60` with **your actual bed printing temperature** — for example `100` for ABS/ASA or `85` for PETG. Bed PID tuning takes longer than hotend tuning — typically **8–15 minutes** depending on bed size and heater power.

When complete you will see output like:

```
// PID parameters: pid_Kp=54.027 pid_Ki=0.770 pid_Kd=947.220
```

### Step 3 — Save the Result

```gcode
SAVE_CONFIG
```

Klipper will restart and the calibrated bed PID values will be saved to the `#*# [heater_bed]` block at the bottom of `printer.cfg`.

---

## Tuning for Multiple Filaments

PID behaviour can vary slightly at different temperatures. If you print a wide range of materials, consider tuning at multiple temperatures and keeping notes:

| Material | Hotend Tune Temp | Bed Tune Temp | Fan Speed During Tune |
|---|---|---|---|
| PLA | 220°C | 60°C | 100% |
| PETG | 240°C | 85°C | 30% |
| ABS / ASA | 250°C | 110°C | 0% |
| Nylon | 260°C | 70°C | 0% |
| PC | 270°C | 110°C | 0% |

Klipper only stores one set of PID values per heater, so tune for your **most common** filament and note that values may be slightly off at extreme temperatures.

---

## Verifying Your Tune

After saving, heat the hotend and bed to your printing temperature and watch the temperature graph in Mainsail or Fluidd. A well-tuned PID should:

- Reach the target temperature without significant overshoot (< 3–5°C above target)
- Settle and hold within **±0.5°C** of the target
- Not oscillate up and down continuously after reaching temperature

If you see continuous oscillation, the tune may have been affected by interference — re-run `PID_CALIBRATE` making sure the environment is stable (no doors opening, no drafts) during the calibration cycles.

---

## Common Problems

| Problem | Likely Cause | Fix |
|---|---|---|
| Temperature oscillates ±2–5°C continuously | PID not tuned or poorly tuned | Re-run `PID_CALIBRATE` |
| Hotend overshoots badly on heat-up | Fan was off during tune, now on during print | Re-tune with fan at print speed |
| Bed takes very long to settle | Tune ran at wrong temperature | Re-tune at your actual print bed temp |
| `SAVE_CONFIG` not updating values | Klipper wrote to `#*#` block but old values in main section override | Remove old `control`, `pid_kp/ki/kd` lines from the main `[extruder]` section |
| Thermal runaway error during tune | Heater too weak or thermistor issue | Check heater cartridge and thermistor wiring |

---

*Back to [Tuning Guides](../README.md#tuning-guides) | [README](../README.md)*
