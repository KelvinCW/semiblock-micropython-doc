# RTC, Watchdog & Deep Sleep

> ![](img/hardblock_WatchDog.png){width=inherit}

This category groups three time- and power-related features of the ESP32:

- **RTC (Real-Time Clock)** — keeps track of the date and time.
- **Watchdog (WDT)** — automatically resets the board if your program hangs.
- **Deep sleep** — powers the chip down to save battery, then wakes after a
  set time.

All three come from the `machine` module.

## What's in this category

- **[Real-Time Clock](rtc.md)** — set and read the date/time, plus get the
  individual year, month, day, hour, minute, and second.
- **[Watchdog](wdt.md)** — start a watchdog timer and feed it to keep the board
  alive.
- **[Deep Sleep](deep-sleep.md)** — sleep for a number of milliseconds to save
  power.

## Quick mental model

```python
rtc = RTC()
rtc.datetime((2025, 1, 1, 0, 0, 0, 0, 0))
current_time = rtc.datetime()
```

> ![](img/wd1.png){width=inherit}

## Next

Continue to **[Real-Time Clock »](rtc.md)**
