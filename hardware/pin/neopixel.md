# NeoPixel LEDs

A **NeoPixel** (WS2812 / WS2812B) is an addressable RGB LED: each LED has a tiny
chip inside, so a single GPIO pin can control the colour and brightness of one
or many LEDs chained together. Many ESP32 boards have one NeoPixel built in.

When your program uses a NeoPixel block, SemiBlock automatically adds the import:

```python
import neopixel
```

## `neoPixel` — create a NeoPixel

Creates a one-pixel `NeoPixel` object on an output pin.

**Inputs / parameters**

- **var_name** — variable name for the strip (default `pixel`).
- **pinNo** — GPIO connected to the NeoPixel data line (default `8`).

**Generated MicroPython**

```python
pixel = neopixel.NeoPixel(Pin(8, Pin.OUT), 1)
```

The trailing `1` is the number of LEDs on the strip.

## `neoPixelWrite` — set a colour

Sets the colour of the first LED and pushes it out to the strip. Colours are
**RGB** values from `0`–`255` (here written in hex as `0xff` = 255).

**Inputs / parameters**

- **var_name** — the NeoPixel variable (default `pixel`).
- **r** — red value (default `0xff`).
- **g** — green value (default `0xff`).
- **b** — blue value (default `0xff`).

**Generated MicroPython**

```python
pixel[0] = (0xff, 0xff, 0xff)
pixel.write()
```

`(0xff, 0xff, 0xff)` is full white. `(0xff, 0, 0)` is red; `(0, 0xff, 0)` green.
Nothing changes on the LED until `.write()` runs — that is the second line.

## Wiring notes

- NeoPixels need three connections: **5 V** (or 3.3 V on small strips), **GND**,
  and **DIN** (data) to the GPIO you chose.
- For long strips, power the LEDs from a separate 5 V supply and join the
  grounds — the ESP32 pin cannot supply enough current for many LEDs.
- A 300–500 Ω resistor in series with the data line improves reliability.

## Next

Continue to **[Timer overview »](../timer/index.md)**
