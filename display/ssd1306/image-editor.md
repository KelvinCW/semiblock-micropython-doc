# Image Editor block: drawing bitmaps inside SemiBlock

The **`imageEditor`** block lets you paint a bitmap by hand inside SemiBlock and turn
it into a Python variable you can draw on the OLED. The canvas is fixed at
**128×64** pixels — exactly the size of a standard SSD1306 screen.

## How it works

When you drop the block in, SemiBlock shows a small grid editor. Each cell you click
toggles a pixel on (`1`) or off (`0`). The drawing is stored on the block and, at code
generation time, flattened into a **2D Python list** — one inner list per row, 64 rows
of 128 values.

**Inputs:**

- `VAR` — the variable name to store the bitmap in (default `image`).
- `IMAGE_EDITOR` — the pixel grid you paint in the UI.

## Generated code

The block emits the variable assigned to a list of rows. Each row is a list of `0`/`1`
values. (Shortened here — the real output has 64 rows of 128 values.)

```python
image = [
[0,0,0,0,1,1,0,0,0,0],
[0,0,0,1,1,1,1,0,0,0],
[0,0,1,1,1,1,1,1,0,0]
]
```

If you never paint anything, the grid defaults to all zeros, so you still get a valid
(blank) list of the right size.

## Drawing the bitmap

The `imageEditor` block only **creates** the array. To put it on screen, pair it with
the [`drawPixels`](draw-pixels.md) block, which walks the array and lights up each
pixel that is `1`.

```python
display = ssd1306.SSD1306_I2C(128, 64, SoftI2C(sda=Pin(21), scl=Pin(22)))
display.fill(0)
image = [
[0,1,0],
[1,1,1],
[0,1,0]
]
for y, row in enumerate(image):
    for x, pixel in enumerate(row):
        if pixel:
            display.pixel(x, y, 1)
display.show()
```

## Next

Continue to [`drawPixels`](draw-pixels.md).
