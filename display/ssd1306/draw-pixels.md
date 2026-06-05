# `drawPixels`

The **`drawPixels`** block takes a bitmap array — usually the one made by the
[`imageEditor`](image-editor.md) block — and draws every "on" pixel onto the SSD1306
screen. It is the companion that turns your painted image into actual light.

## What it does

It loops over the array row by row, then column by column. For every cell whose value
is truthy (`1`), it sets that pixel on the display. Cells that are `0` are skipped, so
the background is left untouched.

**Inputs:**

- `VAR` — the variable holding the bitmap array (default `image`).

## Generated code

```python
for y, row in enumerate(image):
    for x, pixel in enumerate(row):
        if pixel:
            display.pixel(x, y, 1)
```

The variable name comes from the block's `VAR` field, so if your image is stored in
`logo`, the loop reads `for y, row in enumerate(logo):` instead.

## Full example

Paint a shape with `imageEditor`, then render it with `drawPixels`:

```python
display = ssd1306.SSD1306_I2C(128, 64, SoftI2C(sda=Pin(21), scl=Pin(22)))
display.fill(0)
image = [
[1,0,1],
[0,1,0],
[1,0,1]
]
for y, row in enumerate(image):
    for x, pixel in enumerate(row):
        if pixel:
            display.pixel(x, y, 1)
display.show()
```

> The image variable must already exist before `drawPixels` runs. Place the
> `imageEditor` block (or any list-of-rows variable) **above** the `drawPixels` block.

## Next

Continue to [LVGL (Light & Versatile Graphics Library)](../lvgl/index.md).
