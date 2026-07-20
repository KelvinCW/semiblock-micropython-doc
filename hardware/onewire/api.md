# One-Wire API

These four blocks set up a One-Wire bus and exchange single bytes with devices
on it.

## `oneWireInit` — create the bus

Creates a `OneWire` object on a single GPIO pin.

**Inputs / parameters**

- **var_name** — variable name (default `ow`).
- **pin** — the data pin (default `4`).

**Generated MicroPython**

```python
ow = OneWire(Pin(4))
```

> ![](img/ow1.png){width=inherit}


## `oneWireScan` — find devices

Scans the bus and returns a list of device IDs (each a `bytearray`).

**Inputs / parameters**

- **var_name** — variable for the list (default `devices`).
- **ow_name** — the One-Wire variable (default `ow`).

**Generated MicroPython**

```python
devices = ow.scan()
```

> ![](img/ow2.png){width=inherit}

## `oneWireRead` — read a byte

Reads a single byte from the bus.

**Inputs / parameters**

- **var_name** — variable for the result (default `data`).
- **ow_name** — the One-Wire variable (default `ow`).

**Generated MicroPython**

```python
data = ow.readbyte()
```

> ![](img/ow3.png){width=inherit}

## `oneWireWrite` — write a byte

Writes a single byte to the bus.

**Inputs / parameters**

- **ow_name** — the One-Wire variable (default `ow`).
- **data** — the byte to send (default `0xFF`).

**Generated MicroPython**

```python
ow.writebyte(0xFF)
```

> ![](img/ow4.png){width=inherit}

## Wiring notes

- A One-Wire device needs three connections: **3.3 V**, **GND**, and **DQ**
  (data) to the GPIO you chose.
- Add a **4.7 kΩ pull-up resistor** from the data line to **3.3 V** — without it
  the bus will not work reliably.
- For temperature probes, the `ds18x20` driver builds on `OneWire` to do the
  decoding for you.

## Next

Continue to **[RMT overview »](../rmt/index.md)**
