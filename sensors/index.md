# Sensors Overview

**Part IV — Sensors** covers the ready-made blocks SemiBlock MicroPython provides for reading
real-world data and driving small actuators on your ESP32. Instead of writing driver code by
hand, you drag a block, fill in the GPIO pin, and the editor emits correct MicroPython for you.

These blocks live in three toolbox categories:

- **DHT** — temperature & humidity from a single digital pin.
- **HC-SR04 Sonar** — ultrasonic distance measurement (trigger + echo).
- **Sensors** — a grab-bag of extra peripherals: a thermistor temperature reader,
  a 4-digit display, a DC motor, and a servo.

## What's in this section

- **[DHT11 / DHT22 (Temperature & Humidity)](dht.md)** — initialize a DHT sensor and read
  temperature (°C) and humidity (%) using `dht_sensor.measure()`.
- **[HC-SR04 Ultrasonic Distance Sensor](hc-sr04.md)** — measure distance in centimetres or
  millimetres using trigger/echo pulse timing.
- **[Temperature sensor block](temperature.md)** — read an analog thermistor through the ADC and
  convert the reading to °C with a built-in helper.
- **[4-Digit 7-Segment Display](four-digit.md)** — drive a TM1637 module and show a number.
- **[DC Motor (on / off / control)](motor.md)** — switch a DC motor on and off through a digital
  output pin.
- **[Servo (angle control)](servo.md)** — set a servo to a specific angle.

## Before you wire anything

- **Check the voltage.** Many sensors run on 3.3 V; some (HC-SR04, some motors) expect 5 V.
  Never feed 5 V into a 3.3 V-only GPIO. See
  [Powering sensors safely](../hardware/power.md).
- **Match the pin numbers.** The numbers in each block (e.g. `Pin(4)`) are *GPIO* numbers, not
  the physical header position. See [Pin numbering](../hardware/pinout.md).
- **Share a common ground.** Every sensor's `GND` must connect to the board's `GND`.

## How a sensor block becomes code

Every sensor block is a *statement* block: you stack them inside your main program, and SemiBlock
turns each one into one or two lines of MicroPython. Required `import` lines (such as `import dht`
or `from servo import Servo`) are added automatically at the top of the generated program when a
matching block is present — you do not add them yourself.

## Next

Start with the most common sensor: [DHT11 / DHT22 (Temperature & Humidity)](dht.md).
