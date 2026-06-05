# UART serial

**UART** (Universal Asynchronous Receiver/Transmitter) is the classic two-wire
serial port. It sends bytes one bit at a time over a **TX** (transmit) line and
receives them on an **RX** (receive) line. It is used to talk to GPS modules,
GSM modems, other microcontrollers, and many serial sensors.

`UART` is already imported for you at the top of every program:

```python
from machine import Pin, SoftI2C, ADC, PWM, UART
```

## `uartInit` — open a serial port

Creates a `UART` object on one of the ESP32's hardware UARTs.

**Inputs / parameters**

- **var_name** — variable name for the port (default `var1`).
- **uartNo** — UART number `0`, `1`, or `2`.
- **baudrate** — speed, e.g. `9600` … `256000`.
- **tx** — GPIO used for transmit (default `16`).
- **rx** — GPIO used for receive (default `17`).

**Generated MicroPython**

```python
var1 = UART(0, baudrate=9600, tx=16, rx=17)
```

## `uartRead` — read bytes

Reads up to a given number of bytes from the port. The result is a `bytes`
object (or `None` if nothing has arrived yet).

**Inputs / parameters**

- **var_name** — the UART variable to read from (default `var1`).
- **noOfByte** — how many bytes to read (default `8`).

**Generated MicroPython**

```python
var1.read(8)
```

## `uartWrite` — write text

Sends a string out of the TX pin. The text you type is wrapped in quotes
automatically.

**Inputs / parameters**

- **var_name** — the UART variable to write to (default `var1`).
- **value** — the text to send (default `hello`).

**Generated MicroPython**

```python
var1.write("hello")
```

## Wiring notes

- Cross the wires: your board's **TX** goes to the other device's **RX**, and
  **RX** goes to the other device's **TX**.
- Both devices must use the **same baud rate**.
- Connect the two **GND** pins together so they share a common ground.
- UART is 3.3 V logic — see [Powering sensors safely](../power.md) before
  connecting 5 V devices.

## Next

Continue to **[NeoPixel LEDs »](neopixel.md)**
