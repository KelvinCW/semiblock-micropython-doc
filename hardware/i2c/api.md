# I²C API

These four blocks create an I²C bus and exchange data with devices on it.

## `i2cInit` — create the bus

Creates an `I2C` object on a pair of clock/data pins.

**Inputs / parameters**

- **var_name** — variable name (default `i2c1`).
- **i2c_id** — hardware I²C ID (default `0`).
- **scl** — clock pin (default `22`).
- **sda** — data pin (default `21`).
- **freq** — bus speed in Hz (default `400000`).

**Generated MicroPython**

```python
i2c1 = I2C(0, scl=Pin(22), sda=Pin(21), freq=400000)
```

> ![](img/i2c1.png){width=inherit}

## `i2cScan` — find devices

Scans the bus and returns a list of the 7-bit addresses that respond.

**Inputs / parameters**

- **var_name** — variable for the list (default `devices`).
- **i2c_name** — the I²C variable (default `i2c1`).

**Generated MicroPython**

```python
devices = i2c1.scan()
```

> ![](img/i2c2.png){width=inherit}

## `i2cRead` — read from a device

Reads a number of bytes from a device at a given address.

**Inputs / parameters**

- **var_name** — variable for the result (default `data`).
- **i2c_name** — the I²C variable (default `i2c1`).
- **address** — device address (default `0x3C`).
- **length** — number of bytes (default `10`).

**Generated MicroPython**

```python
data = i2c1.readfrom(0x3C, 10)
```

> ![](img/i2c3.png){width=inherit}

## `i2cWrite` — write to a device

Writes a `bytes` object to a device at a given address.

**Inputs / parameters**

- **i2c_name** — the I²C variable (default `i2c1`).
- **address** — device address (default `0x3C`).
- **data** — bytes to send (default `b"\x01\x02\x03"`).

**Generated MicroPython**

```python
i2c1.writeto(0x3C, b"\x01\x02\x03")
```

> ![](img/i2c4.png){width=inherit}

## Wiring notes

- I²C needs **pull-up resistors** (typically 4.7 kΩ) from **SDA→3.3 V** and
  **SCL→3.3 V**. Most breakout boards already include them.
- Connect **SDA→SDA**, **SCL→SCL**, plus shared **3.3 V** and **GND**.
- Many devices can share the same two wires as long as each has a different
  address.

## Next

Continue to **[One-Wire overview »](../onewire/index.md)**
