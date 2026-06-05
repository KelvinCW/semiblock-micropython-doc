# PWM API

These four blocks create a PWM channel, tune its frequency and duty cycle, and
release it again.

## `pwmInit` — attach PWM to a pin

Creates a `PWM` object on a GPIO pin.

**Inputs / parameters**

- **var_name** — variable name for the PWM (default `pwm1`).
- **pin_number** — GPIO to drive (default `15`).

**Generated MicroPython**

```python
pwm1 = PWM(Pin(15))
```

## `pwmSetFreq` — set the frequency

Sets how many on/off cycles happen per second (Hz). For LEDs and motors,
`1000` Hz is a good default; for tones, use the note's frequency.

**Inputs / parameters**

- **var_name** — the PWM variable (default `pwm1`).
- **frequency** — frequency in Hz (default `1000`).

**Generated MicroPython**

```python
pwm1.freq(1000)
```

## `pwmSetDuty` — set the duty cycle

Sets the duty cycle from `0` to `1023`. `0` is fully off, `1023` is fully on,
and `512` is roughly half power.

**Inputs / parameters**

- **var_name** — the PWM variable (default `pwm1`).
- **duty** — duty value `0`–`1023` (default `512`).

**Generated MicroPython**

```python
pwm1.duty(512)
```

## `pwmDeinit` — release the PWM

Turns the PWM off and frees the channel so the pin can be used for something
else.

**Inputs / parameters**

- **var_name** — the PWM variable (default `pwm1`).

**Generated MicroPython**

```python
pwm1.deinit()
```

## Wiring notes

- Drive an LED through a series resistor (≈330 Ω) just like a normal output.
- For motors and buzzers that draw more current, switch them with a transistor
  or motor driver — do not connect them directly to the GPIO pin.

## Next

Continue to **[Worked example: fade an LED »](led-dim.md)**
