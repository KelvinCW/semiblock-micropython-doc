# Deep Sleep

**Deep sleep** powers most of the ESP32 down to save battery. The chip stops
running your program, waits for the time you set, then **resets and starts
over** from the top of your script. It is the key to running a project for weeks
on a small battery.

The function lives in the `machine` module, so you can call it as
`machine.deepsleep(...)`.

## `deepSleep` — sleep for a while

Puts the board to sleep for a number of milliseconds.

**Inputs / parameters**

- **time_ms** — sleep duration in milliseconds (default `10000`).

**Generated MicroPython**

```python
machine.deepsleep(10000)
```

> ![](img/wd14.png){width=inherit}

## Typical pattern

```python
# take a reading, then sleep 10 seconds to save power
value = adc1.read()
print(value)
machine.deepsleep(10000)
```

> ![](img/wd15.png){width=inherit}

Because the board **restarts** after waking, any code that should run every
cycle must be near the top of your script — execution does not resume where it
left off.

## Notes

- During deep sleep, normal variables are lost. Store anything you need across
  cycles in RTC memory or on flash/SD.
- Current draw drops dramatically (often to microamps), which is what makes
  long battery life possible.

## Next

Continue to **[SD Card overview »](../sdcard/index.md)**
