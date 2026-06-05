# Init, start, and stop a timer

These three blocks create a hardware timer, start it running with a callback,
and stop it again. A **callback** is simply the name of a function you have
defined elsewhere; the timer calls it for you on every tick.

## `timerInit` — create a timer

Creates a `Timer` object with a numeric ID.

**Inputs / parameters**

- **var_name** — variable name for the timer (default `timer1`).
- **timer_id** — hardware timer ID, e.g. `0`–`3` (default `0`).

**Generated MicroPython**

```python
timer1 = Timer(0)
```

## `timerStart` — start with a period and callback

Starts the timer. You set how often it fires, whether it repeats, and which
function to call.

**Inputs / parameters**

- **var_name** — the timer variable (default `timer1`).
- **period** — interval in milliseconds (default `1000`).
- **mode** — `Timer.ONE_SHOT` (fire once) or `Timer.PERIODIC` (repeat).
- **callback** — the function name to call each tick (default
  `callback_function`).

**Generated MicroPython**

```python
timer1.init(period=1000, mode=Timer.ONE_SHOT, callback=callback_function)
```

Switching the mode dropdown to `Timer.PERIODIC` makes it repeat forever:

```python
timer1.init(period=1000, mode=Timer.PERIODIC, callback=callback_function)
```

> The callback function receives one argument (the timer itself), so define it
> like `def callback_function(t):`.

## `timerStop` — stop the timer

Deinitialises the timer so it stops firing and frees the hardware.

**Inputs / parameters**

- **var_name** — the timer variable (default `timer1`).

**Generated MicroPython**

```python
timer1.deinit()
```

## Putting it together

```python
timer1 = Timer(0)
timer1.init(period=500, mode=Timer.PERIODIC, callback=blink)
```

## Next

Continue to **[PWM overview »](../pwm/index.md)**
