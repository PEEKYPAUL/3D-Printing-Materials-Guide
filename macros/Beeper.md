# Beeper Macro

> Make your printer audibly useful. A configurable beep macro lets you add audio notifications to any macro — print done, filament runout, heat soak complete, or anything else worth knowing about without staring at the screen.

---

## Overview

Most LCD displays — including the popular MINI12864 — have a small piezo buzzer wired to the board. By default Klipper doesn't expose this as anything useful. The `BEEP` macro takes control of it, letting you fire single or repeated tones at custom frequencies and durations from any macro or the console.

There are two versions depending on whether your display supports PWM on the beeper pin.

---

## Version 1 — PWM Beeper (MINI12864 and most modern displays)

```ini
[output_pin beeper]
pin: EXP1_1            ; check your board's pinout — this is correct for most SKR boards with MINI12864
value: 0
shutdown_value: 0
pwm: True
cycle_time: 0.0005     ; 1 / 0.0005 = 2000 Hz default tone
```

```ini
[gcode_macro BEEP]
description: Beep the buzzer. I=iterations, DUR=duration ms, FREQ=frequency Hz
gcode:
    {% set i    = params.I|default(1)|int %}
    {% set dur  = params.DUR|default(100)|int %}
    {% set freq = params.FREQ|default(2000)|int %}

    {% for _ in range(i) %}
        SET_PIN PIN=beeper VALUE=0.8 CYCLE_TIME={ 1.0 / freq if freq > 0 else 1 }
        G4 P{dur}
        SET_PIN PIN=beeper VALUE=0
        G4 P{dur}
    {% endfor %}
```

---

## Version 2 — Non-PWM Beeper (Ender 3 stock display and similar)

If your display only supports on/off (no frequency control), use this instead. You lose pitch control but keep the rest.

```ini
[output_pin beeper]
pin: P1.30             ; adjust to match your board
value: 0
shutdown_value: 0
```

```ini
[gcode_macro BEEP]
description: Beep the buzzer. I=iterations, DUR=duration ms
gcode:
    {% set i   = params.I|default(1)|int %}
    {% set dur = params.DUR|default(100)|int %}

    {% for _ in range(i) %}
        SET_PIN PIN=beeper VALUE=1
        G4 P{dur}
        SET_PIN PIN=beeper VALUE=0
        G4 P{dur}
    {% endfor %}
```

---

## Usage

| Command | Result |
|---|---|
| `BEEP` | Single 100ms beep at 2kHz |
| `BEEP I=3` | Three beeps |
| `BEEP I=2 DUR=500` | Two long beeps |
| `BEEP I=5 DUR=50 FREQ=1000` | Five short low-pitched beeps |
| `BEEP I=1 FREQ=4000` | Single high-pitched beep |

---

## Adding to Other Macros

The real value is dropping beeps into your workflow so the printer tells you when something needs attention:

```gcode
; End of print_start — heat soak done, printing starting
BEEP I=2 DUR=200

; End of PRINT_END — print is done
BEEP I=3 DUR=300 FREQ=1500

; Filament runout — urgent, get attention fast
BEEP I=10 DUR=100 FREQ=3000
```

---

## Finding Your Beeper Pin

The correct pin depends on your board and display combination. Check your board's pinout diagram or the [Klipper config reference](https://github.com/Klipper3d/klipper/tree/master/config) for your specific board file — search for `beeper` or `EXP1_1` in the example config for your mainboard.

---

*Back to [Macro Guides](../README.md#️-klipper-macros) | [README](../README.md)*
