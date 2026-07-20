# Digital IN / OUT

A digital pin is the simplest piece of hardware: it is either **HIGH** (on) or
**LOW** (off). Before you can use a GPIO line you must create a `Pin` object and
tell MicroPython whether it is an **output** (you drive it) or an **input** (you
read it). SemiBlock provides two blocks for this: `pin` and `pin2`.

## `pin` — output or input

Creates a `Pin` with an explicit direction.

**Inputs / parameters**

- **var_name** — the variable name for the pin (default `p0`).
- **pinNo** — GPIO number, chosen from a dropdown of `0`–`49`.
- **pinDirection** — `OUT` (drive the pin) or `IN` (read the pin).

**Generated MicroPython**

With `var_name = p0`, `pinNo = 2`, `pinDirection = OUT`:

```python
p0 = Pin(2, Pin.OUT)
```

> ![](img/pin2_out.png){width=inherit}

Switching the dropdown to `IN`:

```python
p0 = Pin(2, Pin.IN)
```

> ![](img/pin2_in.png){width=inherit}

Use `OUT` to control LEDs, relays, or motor drivers. Use `IN` to read a button
or a digital sensor output.

## `pin2` — input with a pull resistor

A floating input pin (one with nothing actively driving it) reads random noise.
To fix this, the ESP32 has built-in **pull-up** and **pull-down** resistors that
gently tie the pin to a known level. `pin2` always creates an **input** and lets
you pick which internal resistor to enable.

**Inputs / parameters**

- **var_name** — variable name (default `p0`).
- **pinNo** — GPIO number (`0`–`29`).
- **pinType** — `PULL_UP` or `PULL_DOWN`.

**Generated MicroPython**

With `var_name = p0`, `pinNo = 2`, `pinType = PULL_UP`:

```python
p0 = Pin(2, Pin.IN, Pin.PULL_UP)
```

> ![](img/pin2_pullup.png){width=inherit}

- **PULL_UP** — pin idles HIGH; a button to GND reads LOW when pressed.
- **PULL_DOWN** — pin idles LOW; a button to 3.3 V reads HIGH when pressed.

## Wiring notes

- For an **output** LED: GPIO → resistor (≈330 Ω) → LED → GND.
- For a **button** with `PULL_UP`: one side to the GPIO, the other side to GND.
  No external resistor needed.
- Remember GPIO 34–39 are **input only** and have **no** internal pull
  resistors — use `pin2` only on pins that support pulls.

## Next

Continue to **[Turning pins on/off, reading pin value »](on-off.md)**
