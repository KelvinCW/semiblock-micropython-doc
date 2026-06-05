# Variables

A **variable** is a name that stores a value so you can use it again later. The
variable block names the box on the left and plugs a value into the right.

## The `variable` block

- **Label:** `%1 = %2`
- **Inputs:**
  - `var_name` — the name of the variable (default `var1`).
  - `statements` — a **value block** plugged into the right side.

The block joins the name and the connected value with `=`. For example, if you
plug an [integer block](../math/arithmetic.md) holding `100` into a variable
named `var1`:

```python
var1 = 100
```

## Choosing the value

The right-hand side accepts any value-producing block, such as:

- an integer or string block,
- a math expression like [`mathAdd`](../math/arithmetic.md),
- a function result like [`mathRandomInt`](../math/misc.md).

```python
score = 0
total = 5 + 3
```

## Worked example

Store a sensor reading, then print it:

```python
reading = 512
print(reading)
```

The first line is a variable block (with a value block attached); the second is
a [`print`](print-comment.md) block that shows what you stored.

> Tip: pick clear names like `temperature` or `count` instead of `var1`. Future
> you will thank present you.

## Next

Continue to [Defining functions (`def`)](def.md)
