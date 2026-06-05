# Initialization: `lvglInit`, LCD bus, framebuffer

These blocks bring LVGL online and prepare the low-level plumbing — the import, the
SPI bus to the panel, and the memory buffers LVGL draws into. On an all-in-one board
you may not need them (see [Waveshare 3.5"](../waveshare35.md)), but on a custom wiring
you set them up by hand.

> All of these require **`lv_micropython`** firmware with the `lvgl` and `lcd_bus`
> modules built in.

## `lvglInit` — import LVGL

```python
import lvgl as lv
```

## `importLcdBus` — import the LCD bus module

```python
import lcd_bus
```

## `lcdSpiBusInit` — create an SPI bus

Creates the SPI bus that connects the ESP32 to the display panel.

**Inputs:** var name, spi bus, freq, dc pin, cs pin.

```python
display_bus = lcd_bus.SPIBus(spi_bus=spi_bus, freq=40000000, dc=8, cs=9)
```

## `allocateFramebuffer` — allocate a draw buffer

Allocates a framebuffer in SPIRAM for LVGL to render into. Most drivers want **two**
buffers for smooth double-buffered drawing.

**Inputs:** var name, display bus, size.

```python
fb1 = display_bus.allocate_framebuffer(32768, lcd_bus.MEMORY_SPIRAM)
```

## Typical start

```python
import lvgl as lv
import lcd_bus
display_bus = lcd_bus.SPIBus(spi_bus=spi_bus, freq=40000000, dc=8, cs=9)
fb1 = display_bus.allocate_framebuffer(32768, lcd_bus.MEMORY_SPIRAM)
fb2 = display_bus.allocate_framebuffer(32768, lcd_bus.MEMORY_SPIRAM)
```

Once the bus and buffers exist, hand them to a display driver — see
[Drivers](drivers.md).

## Next

Continue to [Drivers: ST7796, ST7735, generic `displayInit`](drivers.md).
