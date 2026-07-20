# RMT API

These three blocks create an RMT channel, send pulses, and release it.

## `rmtInit` — create a channel

Creates an `RMT` object on a channel and pin.

**Inputs / parameters**

- **var_name** — variable name (default `rmt1`).
- **channel** — RMT channel number (default `0`).
- **pin** — output pin (default `18`).
- **clock_div** — clock divider that sets the tick length (default `80`).

**Generated MicroPython**

```python
rmt1 = RMT(0, pin=Pin(18), clock_div=80)
```

> ![](img/rmt1.png){width=inherit}

## `rmtWrite` — send pulses

Sends a list of pulse durations. The numbers alternate **on, off, on, off…**,
each measured in ticks (1 µs each with `clock_div=80`).

**Inputs / parameters**

- **rmt_name** — the RMT variable (default `rmt1`).
- **pulses** — a list of durations (default `[10, 20, 30, 40]`).
- **start** — begin immediately, `True` or `False`.

**Generated MicroPython**

```python
rmt1.write_pulses([10, 20, 30, 40], start=True)
```

> ![](img/rmt2.png){width=inherit}

## `rmtDeinit` — release the channel

Frees the RMT channel.

**Inputs / parameters**

- **rmt_name** — the RMT variable (default `rmt1`).

**Generated MicroPython**

```python
rmt1.deinit()
```

> ![](img/rmt3.png){width=inherit}

## Wiring notes

- Connect the chosen **pin** to the signal input of your device (for example an
  IR LED driver or an addressable LED's data line).
- Share **GND** between the ESP32 and the device.
- For an IR LED, drive it through a transistor and series resistor rather than
  straight from the GPIO.

## Next

Continue to **[Capacitive Touch overview »](../touch/index.md)**
