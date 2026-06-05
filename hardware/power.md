# Powering sensors safely (3.3 V vs 5 V)

The ESP32 is a **3.3 volt** device. Every GPIO pin expects signals in the
0 V – 3.3 V range. Many popular sensors and modules, however, were designed for
the older **5 volt** Arduino world. Mixing the two without thinking can damage
your board, so this page covers the basics.

## Logic levels in plain English

A digital pin only understands two states:

- **LOW** — close to 0 V (a logical `0`).
- **HIGH** — close to the supply voltage (a logical `1`).

On the ESP32, HIGH means about **3.3 V**. On a 5 V device, HIGH means about
**5 V**. The danger is feeding a 5 V HIGH signal *into* a 3.3 V ESP32 input pin —
that extra voltage can stress or destroy the pin.

## Three common situations

1. **3.3 V sensor → ESP32.** Easy and safe. Power the sensor from the board's
   `3V3` pin and connect signals directly.

2. **ESP32 output → 5 V device input.** Usually fine. Most 5 V chips read 3.3 V
   as a valid HIGH. No conversion needed for the signal, but power the device
   from `5V`/`VIN` if it needs 5 V to run.

3. **5 V sensor output → ESP32 input.** **Not safe directly.** You must lower the
   signal voltage first (see level shifting below).

## Powering rules of thumb

- Use the **`3V3`** pin to power 3.3 V sensors.
- Use the **`5V` / `VIN`** pin (USB power) for devices that need 5 V.
- Always connect a **common ground (`GND`)** between the board and every module —
  signals need a shared reference or nothing works.
- Don't draw heavy current (motors, LED strips, servos) from the board's `3V3`
  regulator; give them their own supply and share ground.

## Level shifting basics

To safely connect a 5 V signal to a 3.3 V input you "shift" the level down:

- **Resistor divider** — two resistors split a 5 V signal to ~3.3 V. Cheap and
  fine for slow, one-direction signals (e.g. a sensor's digital output).
- **Dedicated level-shifter module** — a small bidirectional board (often used
  for I²C). Required when the line must work in *both* directions.

> For I²C and One-Wire you also need **pull-up resistors** (typically 4.7 kΩ to
> 3.3 V). See the [I²C](i2c/api.md) and [One-Wire](onewire/api.md) pages.

When in doubt, prefer sensors sold as "3.3 V compatible" — they connect straight
to the ESP32 with no extra parts.

## Next

Continue to **[Pin category overview »](pin/index.md)**
