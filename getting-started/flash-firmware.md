# Flash firmware

Before your board can run MicroPython, it needs the MicroPython **firmware**
installed once. This is called *flashing*. After this, you can upload your
SemiBlock programs as often as you like without flashing again.

> You only do this once per board (unless you upgrade MicroPython later).

## Where to get the firmware

Download the official MicroPython firmware `.bin` file for your exact board
from the MicroPython downloads page:

- <https://micropython.org/download/>

Pick your chip (for example **ESP32** or **ESP32-S3**), then download the latest
stable `.bin` file. Save it somewhere easy to find, like your Downloads folder.

## Step 1: Find your board's serial port

Plug the board in with a **data** USB cable, then identify its port:

- **macOS:** looks like `/dev/cu.usbserial-0001` or `/dev/cu.SLAB_USBtoUART`
- **Linux:** looks like `/dev/ttyUSB0`
- **Windows:** looks like `COM3`

We explain how to list ports in [Connect your board](connect-board.md). Replace
`PORT` below with your actual port.

## Step 2: Erase the old flash

Start clean by erasing the chip:

```bash
esptool.py --port PORT erase_flash
```

You should see "Chip erase completed successfully".

> Tip: if `esptool` cannot connect, hold the board's **BOOT** button while the
> command starts, then release it.

## Step 3: Write the MicroPython firmware

Now write the `.bin` you downloaded. For a classic ESP32:

```bash
esptool.py --port PORT --baud 460800 write_flash -z 0x1000 esp32-firmware.bin
```

For **ESP32-S3**, the firmware usually flashes at offset `0x0`:

```bash
esptool.py --port PORT --baud 460800 write_flash -z 0x0 esp32s3-firmware.bin
```

Use the actual filename you downloaded in place of the example name above, and
check your board's download page for the correct offset.

## Step 4: Confirm it worked

After flashing, MicroPython is running on the board. You can verify by opening a
serial connection and pressing **Enter** — you should see the `>>>` prompt.
We cover connecting next.

## Troubleshooting

- **"Failed to connect":** try a different USB cable or port; hold **BOOT**.
- **Wrong offset:** double-check the offset on the firmware download page.
- **Permission denied (Linux):** add your user to the `dialout` group.

## Try it yourself

Run just the `erase_flash` step. If it completes, your computer can talk to the
board — the hardest part is done.

## Next

Continue to [Connect your board](connect-board.md)
