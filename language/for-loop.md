# `for` loops

A **`for` loop** repeats the blocks inside it a fixed number of times. It is the
go-to block when you know exactly how many rounds you want.

## The `forLoop` block

- **Label:** `for %1 in range(%2):`
- **Inputs:**
  - `var1` — the counter variable name (default `x`).
  - `var2` — how many times to repeat (default `10`).
- **Body:** a stack of statement blocks that run each round.

With the defaults and a `print` block inside, SemiBlock generates:

```python
for x in range(10):
	print(x)
```

The counter `x` starts at `0` and counts up to `9` (ten values in total). The
body is indented with a tab, which is how Python knows those lines belong to the
loop.

## Counting tips

- `range(10)` gives `0, 1, 2, … 9` — it stops **before** the number you give.
- Change `var1` to any name you like, such as `i` or `step`.
- You can use the counter inside the loop, for example to index a list.

## Worked example: blink three times

Combine a `for` loop with hardware blocks:

```python
for i in range(3):
	led.on()
	sleep(1)
	led.off()
	sleep(1)
```

This turns an LED on and off three times, pausing one second between each
change.

## Next

Continue to [`while` loops](while-loop.md)
