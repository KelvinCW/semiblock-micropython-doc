# Timer

A **hardware timer** runs in the background and calls a function of yours at a
fixed interval — without you writing a `while` loop. This is perfect for jobs
that must happen regularly: blinking an LED, sampling a sensor, or updating a
clock, while your main program does other things.

Timers map to MicroPython's `machine.Timer` class. Because `Timer` is **not** in
the default imports, add it yourself with a free-code or import block:

```python
from machine import Timer
```

## What's in this category

- **[Init / start / stop](init-start-stop.md)**
  - `timerInit` — create a timer with an ID.
  - `timerStart` — set the period, mode, and callback function.
  - `timerStop` — stop the timer and free it.

## Quick mental model

1. **Create** the timer once with `timerInit`.
2. **Start** it with `timerStart`, pointing it at a function to run.
3. **Stop** it with `timerStop` when you no longer need it.

```python
timer1 = Timer(0)
timer1.init(period=1000, mode=Timer.PERIODIC, callback=tick)
```

## Next

Continue to **[Init, start, and stop a timer »](init-start-stop.md)**
