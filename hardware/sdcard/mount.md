# Mounting an SD Card

Before you can read or write files, you set up the card on its SPI pins and
**mount** it into the filesystem. When you are done, unmount it so the card can
be removed safely.

```python
from machine import SDCard
import os
```

## `sdCardInit` — set up the card

Creates an `SDCard` object on the SPI slot and pins.

**Inputs / parameters**

- **var_name** — variable name (default `sd`).
- **slot** — SPI slot number (default `1`).
- **sck** — clock pin (default `18`).
- **mosi** — data-out pin (default `23`).
- **miso** — data-in pin (default `19`).
- **cs** — chip-select pin (default `5`).

**Generated MicroPython**

```python
sd = SDCard(slot=1, sck=Pin(18), mosi=Pin(23), miso=Pin(19), cs=Pin(5))
```

## `sdCardMount` — attach to a folder

Mounts the card so its contents appear under a folder, usually `/sd`.

**Inputs / parameters**

- **sd_name** — the SDCard variable (default `sd`).
- **mount_point** — where to mount it (default `/sd`).

**Generated MicroPython**

```python
os.mount(sd, "/sd")
```

## `sdCardUnmount` — detach safely

Unmounts the card. Always do this before removing it to avoid corrupting data.

**Inputs / parameters**

- **mount_point** — the folder to unmount (default `/sd`).

**Generated MicroPython**

```python
os.umount("/sd")
```

## Wiring notes

- Connect the card's **SCK, MOSI, MISO, CS** to the pins above, plus **3.3 V**
  and **GND**.
- Use a proper SD-card breakout with a 3.3 V regulator and level shifting; do
  not wire a bare card directly to 5 V.

## Next

Continue to **[Reading & writing files »](files.md)**
