# Install

Getting set up for SemiBlock has two parts: the tools on your **computer**, and
the firmware on your **board**. This page covers the computer side; the board
side is covered in [Flash firmware](flash-firmware.md).

## What you need to install

For the full experience you will want:

1. **A modern web browser** — to run the SemiBlock editor. That is all you need
   to build blocks and generate code.
2. **Python 3** — used to run `esptool`, the tool that flashes firmware.
3. **esptool** — the official Espressif tool for flashing ESP32 boards.
4. **A USB serial driver** — so your computer can see the board (often already
   installed).

You only need items 2–4 to put code *onto* a board. To just explore the editor,
a browser alone is enough.

## Step 1: Install Python 3

Check whether Python is already installed by opening a terminal and running:

```bash
python3 --version
```

If you see a version number (for example `Python 3.11.0`), you are ready. If
not, download Python from [python.org](https://www.python.org/downloads/) and
install it.

## Step 2: Install esptool

`esptool` installs through Python's package manager, `pip`:

```bash
pip install esptool
```

Verify it works:

```bash
esptool.py version
```

You should see a version number printed. We use this tool in the next chapter.

## Step 3: USB serial drivers

Most ESP32 boards use a USB-to-serial chip (such as **CP2102** or **CH340**).

- **macOS / Linux:** usually works with no extra driver.
- **Windows:** if the board does not appear, install the driver for your board's
  chip from the manufacturer's website.

We confirm the board is detected in [Connect your board](connect-board.md).

## Step 4: Open the editor

The SemiBlock editor itself runs in your browser — there is nothing to install
for it. We open it in [Open the editor](open-editor.md).

## Quick checklist

- [ ] `python3 --version` prints a version
- [ ] `esptool.py version` prints a version
- [ ] USB cable that supports **data** (not charge-only)

## Try it yourself

Run both version commands above. If both print a number, your computer is fully
prepared to flash a board.

## Next

Continue to [Flash firmware](flash-firmware.md)
