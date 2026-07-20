# Touch API

These two blocks attach a touch pad and read its value.

## `touchInit` — attach a touch pad

Creates a `TouchPad` object on a touch-capable pin.

**Inputs / parameters**

- **var_name** — variable name (default `touch1`).
- **pin** — the touch pin (default `4`).

**Generated MicroPython**

```python
touch1 = TouchPad(Pin(4))
```

> ![](img/touch1.png){width=inherit}

## `touchRead` — read the value

Reads the current capacitance value. The number is large when untouched and
**drops** when a finger is near.

**Inputs / parameters**

- **var_name** — variable for the result (default `value`).
- **touch_name** — the touch pad variable (default `touch1`).

**Generated MicroPython**

```python
value = touch1.read()
```

> ![](img/touch2.png){width=inherit}

## Using it as a button

```python
touch1 = TouchPad(Pin(4))
baseline = touch1.read()
while True:
	if touch1.read() < baseline // 2:
		print("Touched!")
	sleep_ms(100)
```

> ![](img/touch4.png){width=inherit}

## Wiring notes

- Only **touch-capable** pins work: **GPIO 0, 2, 4, 12, 13, 14, 15, 27, 32,
  33**.
- Connect the pin to a small pad of copper, foil, or conductive tape — no
  resistor or external part is required.
- Keep the wire short; long leads pick up noise and make the reading jittery.

## Next

Continue to **[RTC & Watchdog overview »](../rtc-wdt/index.md)**
