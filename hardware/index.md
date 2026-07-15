# Hardware Overview

Part III is where SemiBlock MicroPython stops being "just Python" and starts
controlling the real world: blinking LEDs, reading sensors, spinning motors,
and talking to chips. Every hardware block you drag onto the workspace turns
into a small piece of MicroPython that runs directly on your ESP32 board.

## The `machine` module

Almost all ESP32 hardware is reached through MicroPython's built-in **`machine`**
module. It gives you classes that wrap the chip's peripherals:

| Class | What it controls | SemiBlock category |
| ----- | ---------------- | ------------------ |
| `Pin` | A single GPIO line (digital in/out) | [Pin](pin/index.md) |
| `UART` | Serial TX/RX communication | [Pin → UART](pin/uart.md) |
| `Timer` | Hardware timers / callbacks | [Timer](timer/index.md) |
| `PWM` | Pulse-width modulation (dimming, tones) | [PWM](pwm/index.md) |
| `ADC` / `DAC` | Analog read / analog write | [ADC & DAC](adc/index.md) |
| `SPI` | High-speed 4-wire bus | [SPI](spi/index.md) |
| `I2C` | 2-wire bus for many sensors | [I²C](i2c/index.md) |
| `OneWire` | Single-wire bus (DS18B20, etc.) | [One-Wire](onewire/index.md) |
| `RMT` | Precise pulse generation (IR, LEDs) | [RMT](rmt/index.md) |
| `TouchPad` | Capacitive touch sensing | [Capacitive Touch](touch/index.md) |
| `RTC` / `WDT` | Real-time clock / watchdog | [RTC & WatchDog](rtc-wdt/index.md) |
| `SDCard` | SD card storage over SPI | [SD Card](sdcard/index.md) |

When you build a program, SemiBlock automatically adds the common imports at the
top of the generated file:

```python
from machine import Pin, SoftI2C, ADC, PWM, UART
from time import sleep, sleep_ms, sleep_us
import network
import math
```

Other classes (`Timer`, `SPI`, `I2C`, `RTC`, `WDT`, `SDCard`, `RMT`, `OneWire`,
`TouchPad`, `DAC`) come from the same `machine` module, and `os` / `neopixel`
are standard MicroPython modules — drag the matching blocks and SemiBlock emits
the correct calls for you.

## Hardware categories

### **[Pin](pin/index.md)** — digital I/O, UART serial, NeoPixel LEDs.

> ![](hardblocks/hardblock_Pin.png){width=inherit}

### **[Timer](timer/index.md)** — periodic and one-shot background callbacks.

> ![](hardblocks/hardblock_Timer.png){width=inherit}

### **[PWM](pwm/index.md)** — dim LEDs, drive motors, make tones.

> ![](hardblocks/hardblock_PWM.png){width=inherit}

### **[ADC & DAC](adc/index.md)** — read analog voltages, output analog voltages.

> ![](hardblocks/hardblock_ADC.png){width=inherit}

### **[SPI](spi/index.md)** — fast bus for displays and SD cards.

> ![](hardblocks/hardblock_SPI.png){width=inherit}

### **[I²C](i2c/index.md)** — two-wire bus shared by many sensors.

> ![](hardblocks/hardblock_I2C.png){width=inherit}

### **[One-Wire](onewire/index.md)** — single-pin bus for temperature probes.

> ![](hardblocks/hardblock_OneWire.png){width=inherit}

### **[RMT](rmt/index.md)** — precise pulse trains for IR remotes and LEDs.

> ![](hardblocks/hardblock_RMT.png){width=inherit}

### **[Capacitive Touch](touch/index.md)** — turn a bare pin into a touch button.

> ![](hardblocks/hardblock_Touch.png){width=inherit}

### **[RTC & WatchDog](rtc-wdt/index.md)** — keep time, auto-recover, deep sleep.

> ![](hardblocks/hardblock_WatchDog.png){width=inherit}

### **[SD Card](sdcard/index.md)** — store and read files on removable storage.

> ![](hardblocks/hardblock_SDcard.png){width=inherit}

## Before you wire anything

Two short concept pages will save you from fried pins and confusing bugs:

### **[Pin numbering & pinouts](pinout.md)** — what a GPIO number means and which
  pins are safe to use.
### **[Powering sensors safely](power.md)** — 3.3 V vs 5 V logic and level shifting.

## Next

Continue to **[Pin numbering and board pinouts »](pinout.md)**
