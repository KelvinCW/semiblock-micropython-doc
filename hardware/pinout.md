# Pin numbering and board pinouts

Before you can blink an LED you need to know **which physical pin** a block is
talking to. On the ESP32 this is always done by **GPIO number**, not by the
position of the pin on the header.

## What is a GPIO number?

GPIO stands for **General-Purpose Input/Output**. Each GPIO line on the ESP32
has a number — `GPIO0`, `GPIO1`, `GPIO2`, and so on. In MicroPython you select a
line by passing that number to `Pin(...)`:

```python
led = Pin(2, Pin.OUT)
```

> ![](block_led_2.png){width=inherit}

This means *"control the GPIO2 line as an output."* In SemiBlock the **Pin**
block has a dropdown of GPIO numbers (0–49) — pick the one wired to your
component. The number printed silk-screened on your board (sometimes `D2`, `IO2`)
is what you select.

## Safe, general-purpose pins

Most ESP32 boards expose many usable GPIOs. As a rule of thumb:

- **Good for general use:** GPIO 4, 5, 13, 14, 16, 17, 18, 19, 21, 22, 23, 25,
  26, 27, 32, 33. These can be input or output and have no special boot role.
- **Input-only (no output, no pull-ups):** GPIO 34, 35, 36, 39. Great for
  reading sensors and analog inputs, but you cannot drive an LED with them.
- **Used for flash (avoid):** GPIO 6–11 are connected to the SPI flash chip on
  most modules. Using them will usually crash the board.

> Pin maps vary between ESP32 variants (ESP32, ESP32-S3, etc.). Always check the
> pinout diagram printed for *your* specific board.

## Strapping pins (use with care)

A few GPIOs are read at boot to decide how the chip starts. These are called
**strapping pins**: GPIO 0, 2, 5, 12, 15. They still work as normal I/O *after*
boot, but if an attached component pulls them to the wrong level at power-on the
board may fail to start or refuse to flash.

- **GPIO0** — must be high to boot normally (low = flash mode).
- **GPIO2** — often tied to the on-board LED; fine for output.
- **GPIO12** — must be low at boot on many boards.

If a project behaves strangely only at power-up, a strapping pin is a common
culprit — move that signal to a plain GPIO.

## Picking a pin in SemiBlock

1. Drag a **Pin** block (Pin category).
2. Set the variable name (e.g. `led`).
3. Choose the **GPIO number** from the dropdown.
4. Choose the direction (`OUT` to drive, `IN` to read).

The block emits exactly:

```python
led = Pin(2, Pin.OUT)
```

> ![](block_led_2.png){width=inherit}

## Next

Continue to **[Powering sensors safely (3.3 V vs 5 V) »](power.md)**
