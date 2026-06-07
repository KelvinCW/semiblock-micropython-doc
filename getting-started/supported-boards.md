# Supported boards

SemiBlock generates MicroPython for **ESP32-class** microcontrollers. This page introduces the boards you can use and points out a few differences to keep in mind.

The toolbox even includes a dedicated **Machine** category and a **Waveshare 3.5"** category for board-specific setup blocks.

> [!NOTE]
> We can't test all ESP32 devices, basically any device can run micropython and support [mpremote](https://docs.micropython.org/en/latest/reference/mpremote.html) command will works

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

## Tested ESP32 boards

We suggest these devices:

### [ESP32-C3-Zero](https://www.waveshare.com/esp32-c3-zero.htm)

### [ESP32-C6-Zero](https://docs.waveshare.com/ESP32-C6-Zero)

### [ESP32 Touch LCD 3.5"](https://www.waveshare.com/esp32-touch-lcd-3.5.htm)

## Next

Continue to [Install](install.md)
