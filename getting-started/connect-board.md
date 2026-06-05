# Connecting the board over USB / serial

Once MicroPython firmware is on your board, the next step is to connect it to
your computer so SemiBlock and your flashing tools can talk to it. The board
appears as a **serial port** (also called a COM port or `/dev` device).

## What the USB cable does

A single USB cable carries two things:

- **Power** — to run the board.
- **Serial data** — a two-way text channel between your computer and MicroPython.

> Use a cable that supports **data**, not a cheap charge-only cable. If your
> computer never sees a new serial port, the cable is the first thing to suspect.

## The USB-to-serial chip

Most ESP32 boards include a small bridge chip — usually **CP2102** or **CH340** —
that turns USB into a serial port. Your computer may need the matching driver:

- **CP210x** driver (Silicon Labs)
- **CH340/CH341** driver (WCH)

Native-USB boards like the ESP32-S3 often need no driver at all.

## Finding the serial port

### macOS

Open a terminal and run:

```bash
ls /dev/cu.*
```

Look for something like `/dev/cu.SLAB_USBtoUART` (CP2102) or `/dev/cu.usbserial-0001`
(CH340). On native-USB boards you may see `/dev/cu.usbmodem...`.

### Linux

```bash
ls /dev/ttyUSB* /dev/ttyACM*
```

CP2102/CH340 boards show up as `/dev/ttyUSB0`; native-USB boards as `/dev/ttyACM0`.
You may need to add yourself to the `dialout` group:

```bash
sudo usermod -a -G dialout $USER
```

Log out and back in for the change to take effect.

### Windows

Open **Device Manager → Ports (COM & LPT)**. Your board appears as
`Silicon Labs CP210x ... (COM5)` or `USB-SERIAL CH340 (COM5)`. Note the `COM`
number — you'll use it when flashing and uploading.

## Quick connection test

If you have the `mpremote` tool installed, you can open the live MicroPython
prompt (REPL):

```bash
mpremote connect /dev/ttyUSB0
```

Press **Enter** and you should see the `>>>` prompt. Type:

```python
>>> print("hello board")
hello board
```

Press **Ctrl-]** to exit. Seeing `>>>` confirms the board, firmware, and cable
all work.

## Troubleshooting

- **No port appears** → try another cable, then install the CP210x/CH340 driver.
- **Port appears then vanishes** → the board may be in bootloader mode; press the
  **RESET/EN** button.
- **Permission denied (Linux)** → add yourself to `dialout` and re-login.

## Try it yourself

Unplug and re-plug your board while watching `ls /dev/cu.*` (macOS) or Device
Manager (Windows). Watching the port appear and disappear tells you exactly which
device is your board.

## Next

[Opening the SemiBlock editor](open-editor.md)
