# Input Shaping — Klipper Resonance Compensation

> Eliminate ringing, ghosting, and echoing artefacts from your prints by measuring and cancelling frame vibration with Klipper's built-in resonance testing tools.

---

## What Is Ringing?

Ringing (also called ghosting or echoing) appears as rippling waves in the print surface, usually radiating outward from sharp corners and direction changes. It is caused by the printer frame vibrating when the toolhead changes direction rapidly. Those vibrations get recorded into the plastic layer by layer.

![Example of ringing artefact on a printed part](../images/input-shaping-01-ringing.jpg)
*Ringing artefact — the rippling pattern near the corner is caused by frame resonance. Input shaping eliminates this.*

Input shaping works by measuring the resonant frequencies of your specific printer, then applying a digital filter that pre-cancels those vibrations before they reach the steppers. The result is clean, ringing-free output at higher speeds.

---

## What You Need

| Item | Notes |
|---|---|
| ADXL345 accelerometer | ~£3–£5 from any electronics supplier. The standard choice for Klipper. |
| Raspberry Pi or Klipper host | The accelerometer connects to the Pi via SPI — built-in on all Pi models |
| Klipper + Mainsail or Fluidd | Any recent Klipper version supports `TEST_RESONANCES` and `SHAPER_CALIBRATE` |
| `numpy` installed on the Pi | Required for graph generation — installed once via SSH |

> 💡 Some toolhead boards (e.g. EBB36, Mellow Fly SHT) have an ADXL345 built in — if yours does, skip the wiring step.

---

## Step 1 — Install numpy on Your Pi

Connect to your Pi via SSH and run:

```bash
~/klippy-env/bin/pip install numpy
```

This only needs to be done once. Restart Klipper after installing:

```bash
sudo systemctl restart klipper
```

---

## Step 2 — Wire the ADXL345

The ADXL345 connects to the Raspberry Pi's SPI bus:

| ADXL345 Pin | Raspberry Pi Pin | GPIO |
|---|---|---|
| VCC | 3.3V | Pin 1 |
| GND | GND | Pin 6 |
| CS | CE0 | GPIO 8 (Pin 24) |
| SDO/MISO | MISO | GPIO 9 (Pin 21) |
| SDA/MOSI | MOSI | GPIO 10 (Pin 19) |
| SCL/CLK | SCLK | GPIO 11 (Pin 23) |

![ADXL345 accelerometer mounted to printhead](../images/input-shaping-03-adxl.jpg)
*ADXL345 mounted rigidly to the toolhead. Use the hotend fan screws or a printed mount — it must not wobble at all.*

> ⚠️ **Rigid mounting is critical.** Any movement between the sensor and the toolhead produces false readings. Use screws, not tape.

For the **Y axis measurement**, remount the accelerometer to the bed (on a flat spot near the centre). You are measuring the bed's resonant frequency, not the toolhead's.

---

## Step 3 — Add to printer.cfg

Add the following sections to your `printer.cfg`. The `probe_points` should be set to the centre of your build plate:

```ini
[mcu rpi]
serial: /tmp/klipper_host_mcu

[adxl345]
cs_pin: rpi:None

[resonance_tester]
accel_chip: adxl345
probe_points:
    150, 150, 20  # adjust to your bed centre — X, Y, Z height
```

Save and do a **firmware restart** from Mainsail or Fluidd before proceeding.

---

## Step 4 — Run the Resonance Tests

From the Mainsail / Fluidd console, run each axis test separately:

```gcode
TEST_RESONANCES AXIS=X
TEST_RESONANCES AXIS=Y
```

Klipper will move the toolhead through a resonance sweep for each axis and write the results to `/tmp/` on the Pi. You will see output like:

```
Resonance measurements:
X: Fitted shaper 'mzv' frequency = 48.2 Hz (vibrations = 4.3%, smoothing ~= 0.047)
Y: Fitted shaper 'mzv' frequency = 39.8 Hz (vibrations = 3.1%, smoothing ~= 0.062)
```

To generate the frequency graphs, run:

```bash
~/klipper/scripts/calibrate_shaper.py /tmp/resonances_x_*.csv -o /tmp/shaper_calibrate_x.png
~/klipper/scripts/calibrate_shaper.py /tmp/resonances_y_*.csv -o /tmp/shaper_calibrate_y.png
```

Then copy the `.png` files to your computer to view them (via WinSCP, FileZilla, or `scp`).

---

## Step 5 — Read Your Graphs

The graphs will look similar to these. Replace these placeholders with your own output graphs:

### X Axis — Resonance Graph

> 📸 **[Placeholder — add your X axis resonance graph here]**
>
> *Copy your `/tmp/shaper_calibrate_x.png` here after running the test.*

---

### Y Axis — Resonance Graph

> 📸 **[Placeholder — add your Y axis resonance graph here]**
>
> *Copy your `/tmp/shaper_calibrate_y.png` here after running the test.*

---

### How to Read the Graph

The graph shows vibration amplitude (Y axis) against frequency (X axis) for each available shaper type. What to look for:

- **The recommended shaper is highlighted** — Klipper picks the best balance between vibration reduction and smoothing
- **Lower vibration % = better** — aim for under 5% if possible
- **Smoothing value** — higher smoothing reduces ringing more but softens fine detail at high speeds; lower smoothing preserves detail
- **The peak frequency** is where your printer resonates most — this is the number that goes into `printer.cfg`

---

## Step 6 — Apply to printer.cfg

Use the values from your test output to fill in the `[input_shaper]` section. Add this to your `printer.cfg`:

```ini
[input_shaper]
shaper_freq_x: 48.2         # replace with your X result
shaper_freq_y: 39.8         # replace with your Y result
shaper_type_x: mzv          # replace with the recommended shaper for X
shaper_type_y: mzv          # replace with the recommended shaper for Y
damping_ratio_x: 0.1        # default — see smoothing section below
damping_ratio_y: 0.1        # default — see smoothing section below
```

> 💡 You can use different shaper types for X and Y — Klipper supports `shaper_type_x` and `shaper_type_y` independently. Use `shaper_type` only if both axes use the same type.

Save `printer.cfg` and do a **firmware restart**.

### Example — completed section:

> 📸 **[Placeholder — add a screenshot of your printer.cfg input_shaper section here]**
>
> *Show the completed `[input_shaper]` block with your real values filled in.*

---

## Understanding Smoothing

Smoothing is the trade-off at the heart of input shaping. Every shaper filter that reduces ringing also introduces a small amount of smoothing — a slight softening of fine surface detail at high speeds. The stronger the filter, the more smoothing it applies.

### What the smoothing value means

When Klipper reports a result like:

```
X: Fitted shaper 'mzv' frequency = 48.2 Hz (vibrations = 4.3%, smoothing ~= 0.047)
```

The `smoothing ~= 0.047` figure tells you how much the filter rounds off sharp features. As a rough guide:

| Smoothing Value | Effect on Print Quality |
|---|---|
| < 0.05 | Minimal — virtually no visible impact at normal speeds |
| 0.05 – 0.10 | Slight — fine detail may soften slightly at very high speeds |
| 0.10 – 0.15 | Moderate — noticeable at high speeds; reduce speed if detail matters |
| > 0.15 | High — significant softening; switch to a less aggressive shaper or reduce speed |

Lower is better, but a higher smoothing value is still preferable to ringing. If your smoothing is high, consider:
1. Trying a less aggressive shaper type (e.g. `mzv` instead of `ei`)
2. Reducing print speed rather than changing the shaper
3. Addressing the mechanical cause — loose belts or a resonant frame

---

### damping_ratio_x and damping_ratio_y

These values tell Klipper how damped your printer's vibrations are — how quickly the frame naturally stops ringing after a direction change. The default of `0.1` is a reasonable estimate for most printers and is fine to leave as-is.

```ini
damping_ratio_x: 0.1   # default — suitable for most printers
damping_ratio_y: 0.1   # default — suitable for most printers
```

If your printer has **significant damping** (e.g. a heavy enclosure, foam-mounted components, or rubber feet that absorb vibration well), you may get a slightly more accurate result by increasing this to `0.15` or `0.2`. Most users never need to change it.

> ⚠️ Do not blindly increase damping ratios — an inaccurate value produces a less effective shaper. Only adjust if you have a specific reason.

---

### Controlling Smoothing When Using SHAPER_CALIBRATE

When running the automatic calibration, you can set a maximum acceptable smoothing limit. Klipper will then only recommend shapers that stay within that limit:

```gcode
SHAPER_CALIBRATE MAX_SMOOTHING=0.05
```

This is useful if you find the auto-selected shaper produces more softening than you want on detailed prints. Setting a lower `MAX_SMOOTHING` forces Klipper to pick a less aggressive shaper — but if ringing is not fully eliminated, lower it further only in small steps.

A good starting point:

| Print Focus | Suggested MAX_SMOOTHING |
|---|---|
| Speed priority | 0.10 – 0.15 (default — let Klipper decide) |
| Balanced | 0.06 – 0.08 |
| Fine detail priority | 0.04 – 0.05 |

---

## Shaper Types Reference

| Shaper | Characteristics | Best For |
|---|---|---|
| `zv` | Least smoothing, fastest | Low resonance frequencies, very stiff frames |
| `mzv` | Good balance — Klipper's most common recommendation | Most printers — well-tuned CoreXY and bed-slingers |
| `ei` | More smoothing than MZV | Higher resonance frequencies |
| `2hump_ei` | Aggressive smoothing | Printers with poorly-controlled or very high frequencies |
| `3hump_ei` | Maximum smoothing | Last resort — will noticeably reduce print detail |

---

## Or — Let Klipper Do It Automatically

Instead of steps 4–6 above, you can run a single command that tests both axes and writes the values directly into `printer.cfg`:

```gcode
SHAPER_CALIBRATE
```

Klipper runs both sweeps, selects the best shaper and frequency for each axis, and saves the result automatically. After it completes, run `SAVE_CONFIG` and Klipper will restart with the new values applied.

> ⚠️ `SHAPER_CALIBRATE` overwrites any existing `[input_shaper]` values. Review the result in `printer.cfg` after it runs.

---

## Tips

- **Fix mechanical issues first** — input shaping cannot compensate for loose belts, worn bearings, or a wobbly frame. Those must be resolved before calibration.
- **Equal belt tension matters** — uneven belt tension on X and Y will give inconsistent results. Tension both belts before running the test.
- **Re-run calibration after any physical change** — changing the hotend, adding a camera, replacing the bed, moving the printer, or adding a spool holder all change the resonant frequency.
- **Higher frequency = stiffer printer** — a well-built CoreXY typically measures 60–100 Hz on X/Y. A bed-slinger often measures 30–50 Hz.
- **After calibration, increase your print speed** — input shaping allows significantly higher speeds without ringing. Test with a speed tower after applying the shaper.
- **The accelerometer stays on during normal printing** — there is no need to remove it. It is only active during resonance tests.

---

*Back to [Tuning Guides](../README.md#tuning-guides) | [README](../README.md)*
