# Supported boards

SemiBlock generates MicroPython for **ESP32-class** microcontrollers. This page introduces the boards you can use and points out a few differences to keep in mind.

The toolbox even includes a dedicated **Machine** category and a **Waveshare 3.5"** category for board-specific setup blocks.

> [!NOTE]
> Information to highlight.

## ESP32 (classic)

The original ESP32 is the most common board for SemiBlock projects.

- Dual-core processor with built-in **Wi-Fi** and **Bluetooth**.
- Many **GPIO** pins for LEDs, buttons, sensors, and motors.
- On most dev boards, a built-in LED is wired to **GPIO 2**.

It is affordable, widely available, and well supported by MicroPython.

## ESP32-S3

The ESP32-S3 is a newer member of the same family.

- Extra memory and processing power, great for heavier projects.
- Native **USB** support, which often makes flashing and connecting simpler.
- More GPIO pins and better support for cameras and AI workloads.

One difference to remember: many S3 boards use an **addressable (NeoPixel) LED** for their onboard light instead of a plain GPIO LED. For S3 onboard LEDs you may use the **Pin** category's NeoPixel blocks rather than simple on/off.

## Waveshare 3.5" board

SemiBlock includes special support for the **Waveshare 3.5"** display board, which pairs an ESP32 with a touchscreen.

- Find its setup block in the **Waveshare 3.5"** toolbox category.
- Use it to initialize the display before drawing to the screen.

Board-level helpers like reset, sleep, and Wi-Fi live in the **Machine** category (see `toolboxMachine.js`), and apply to all of these boards.

## Choosing a board

| If you want to... | Pick |
|-------------------|------|
| Start cheap and simple | ESP32 (classic) |
| Do more / use native USB | ESP32-S3 |
| Build a touchscreen project | Waveshare 3.5" |

Any of them works for the tutorials in this guide. Where a step differs by board (for example, the onboard LED pin), we will call it out.

## Pins are not always the same

GPIO numbers can differ between boards. A pin that is safe to use on one board might be reserved on another. When in doubt:

- Check your board's pinout diagram.
- Start with GPIO 2 for a classic ESP32 LED test.

## Try it yourself

Find the printed labels on your board (look for "IO2", "GND", "3V3"). Locating these now will make wiring your first circuit much easier later.

## Next

Continue to [Install](install.md)
