# Widgets — Image, LED, Keyboard, Tabview

These widgets cover pictures, status lights, on-screen typing, and multi-page layouts.

## `lvglImageCreate` — image

**Inputs:** image name, parent.

```python
image1 = lv.image(scr)
```

## `lvglImageSetSrc` — set image source

Point the image at a file path or symbol.

**Inputs:** image name, src.

```python
image1.set_src("S:logo.png")
```

## `lvglImageSetSrcCostume` — set image from a costume file

Loads from the SemiBlock costume filesystem (drive `S:`).

**Inputs:** image name, costume file.

```python
image1.set_src("S:cat.png")
```

## `lvglLedCreate` — LED

A round status light widget.

**Inputs:** led name, parent.

```python
led1 = lv.led(scr)
```

## `lvglLedOn` / `lvglLedOff` / `lvglLedToggle`

**Inputs:** led name.

```python
led1.on()
```

```python
led1.off()
```

```python
led1.toggle()
```

## `lvglLedSetBrightness` — LED brightness

**Inputs:** led name, brightness (0–255).

```python
led1.set_brightness(200)
```

## `lvglKeyboardCreate` — on-screen keyboard

**Inputs:** keyboard name, parent.

```python
keyboard1 = lv.keyboard(scr)
```

## `lvglKeyboardSetTextarea` — link keyboard to a text area

Sends the keyboard's keystrokes into a text area.

**Inputs:** keyboard name, textarea name.

```python
keyboard1.set_textarea(textarea1)
```

## `lvglTabviewCreate` — tabbed view

**Inputs:** tabview name, parent, direction.

```python
tabview1 = lv.tabview(scr, lv.DIR.TOP)
```

## `lvglTabviewAddTab` — add a tab

Returns the tab's content object so you can add widgets to it.

**Inputs:** tab name, tabview name, title.

```python
tab1 = tabview1.add_tab("Home")
```

## Next

Continue to [Widgets — Chart, Meter, Canvas](widgets-data.md).
