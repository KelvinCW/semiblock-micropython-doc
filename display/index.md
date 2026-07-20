# Display Overview

> ![](img/hardblock_Display.png){width=inherit}

SemiBlock MicroPython can drive two very different kinds of screens. Both live in
the toolbox, but they use different firmware and different drawing styles.

## The two display families

- **SSD1306 OLED** — a tiny monochrome screen (typically 128×64 pixels) wired over
  **I2C**. It uses MicroPython's built-in `framebuf` drawing primitives through the
  `ssd1306` driver. Great for text, simple shapes, and small bitmaps. Works on
  **standard MicroPython firmware**.
- **LVGL TFT** — full-colour graphics using **LVGL** (Light & Versatile Graphics
  Library). You build real UI widgets (buttons, sliders, charts) on a colour TFT.
  This requires special **`lv_micropython`** firmware that bundles `import lvgl as lv`.
- **Waveshare 3.5"** — an all-in-one ESP32 board with a built-in 3.5" colour TFT.
  A single block wires up the whole LVGL display pipeline for you.

## Which one should I use?

| Feature           | SSD1306 OLED            | LVGL TFT                         |
| ----------------- | ----------------------- | -------------------------------- |
| Colour            | Monochrome (on/off)     | Full colour (RGB565)             |
| Connection        | I2C (2 wires)           | SPI / QSPI                       |
| Firmware          | Standard MicroPython    | `lv_micropython` (custom build)  |
| Best for          | Text, icons, small graphs | Touch UIs, dashboards, widgets |
| Driver import     | `import ssd1306`        | `import lvgl as lv`              |

> SemiBlock automatically adds `import ssd1306` to your program when it detects an
> SSD1306 block, so you rarely need to import it by hand.

## In this part

- [SSD1306 OLED](ssd1306/index.md) — setup, drawing, effects, and the image editor.
- [LVGL (Light & Versatile Graphics Library)](lvgl/index.md) — colour widgets and screens.
- [Waveshare 3.5" all-in-one display board](waveshare35.md) — one block to boot the screen.

## Next

Continue to [SSD1306 OLED](ssd1306/index.md).
