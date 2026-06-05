# DAC — write analog values

A **DAC** does the opposite of an ADC: it turns a number into a real output
**voltage**. The ESP32's DAC is 8-bit, so values run from `0` (0 V) to `255`
(~3.3 V). You can use it for simple waveforms, analog control signals, or basic
audio.

The DAC class comes from `machine` but is not in the default imports — add it:

```python
from machine import DAC
```

## `dacInit` — attach a DAC to a pin

Creates a `DAC` object on a GPIO pin.

**Inputs / parameters**

- **var_name** — variable name for the DAC (default `dac1`).
- **pin_number** — GPIO to output on (default `25`).

**Generated MicroPython**

```python
dac1 = DAC(Pin(25))
```

## `dacWrite` — output a voltage

Writes an 8-bit value (`0`–`255`) to the DAC, producing a proportional voltage.

**Inputs / parameters**

- **dac_name** — the DAC variable (default `dac1`).
- **value** — output level `0`–`255` (default `128`).

**Generated MicroPython**

```python
dac1.write(128)
```

`128` produces roughly half of 3.3 V (about 1.65 V).

## Sweeping the output

```python
dac1 = DAC(Pin(25))
for i in range(256):
	dac1.write(i)
	sleep_ms(5)
```

## Wiring notes

- The ESP32 has exactly **two** DAC channels: **GPIO 25** and **GPIO 26**. No
  other pin can output analog.
- The DAC can only source a tiny current — buffer it with an op-amp or
  transistor if you need to drive a real load.

## Next

Continue to **[SPI overview »](../spi/index.md)**
