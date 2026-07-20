# Pin

> ![](img/hardblock_Pin.png){width=inherit}

The **Pin** category is the foundation of all hardware control. A *pin* (short
for GPIO) is a single electrical connection on your ESP32 that you can switch on
and off, read as an input, or use to talk to other chips.

Everything in this category maps to MicroPython's `machine.Pin` class plus a few
related helpers (`UART` for serial, `neopixel` for addressable LEDs).

## What's in this category

### **[Digital IN / OUT](digital-io.md)** — create a pin as an input or output.

#### `pin` — choose direction `OUT` or `IN`.

> ![](img/out_in.png){width=inherit}

#### `pin2` — input pin with an internal `PULL_UP` / `PULL_DOWN` resistor.
  
> ![](img/pull.png){width=inherit}

### **[On / off / read](on-off.md)** — drive a pin and read its state.
#### `on` — set the pin HIGH.

> ![](img/on.png){width=inherit}

#### `off` — set the pin LOW.

> ![](img/off.png){width=inherit}

#### `pinValue` — read the current value of a pin.

> ![](img/value.png){width=inherit}

### **[UART serial](uart.md)** — send and receive bytes over a serial port.

#### `uartInit` — open a UART with baud rate and TX/RX pins.

> ![](img/init.png){width=inherit}
 
#### `uartRead` — read a number of bytes.

> ![](img/read.png){width=inherit}

#### `uartWrite` — write a string.

> ![](img/write.png){width=inherit}

### **[NeoPixel LEDs](neopixel.md)** — drive WS2812 addressable RGB LEDs.

#### `neoPixel` — create a NeoPixel strip object.

> ![](img/pixel.png){width=inherit}

#### `neoPixelWrite` — set a colour and push it to the strip.

> ![](img/pixel_write.png){width=inherit}

## Quick mental model

1. **Create** a pin object once (`pin`, `pin2`, `uartInit`, `neoPixel`).
2. **Use** it many times (`on`, `off`, `pinValue`, `uartRead`, etc.).

The "create" blocks assign to a **variable name** you choose (like `led` or
`p0`); the "use" blocks refer back to that same name.

## Next

Continue to **[Digital IN / OUT »](digital-io.md)**
