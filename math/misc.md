# `random`, `randint`, `divmod`, `hex`, `ord`

A handful of useful odds and ends live in the Math category. Each is a **value
block**.

The two random blocks below use the `random` module, so add an
[`import random`](../language/imports.md) block to your program. The rest are
built in.

## The `mathRandom` block

- **Label:** `random()` — no inputs. A random decimal between 0.0 and 1.0.

```python
random.random()
```

## The `mathRandomInt` block

- **Label:** `randomInt(%1, %2)` — inputs `A` (default `0`), `B` (default `10`).
  A random whole number from `A` to `B`, inclusive.

```python
random.randint(0, 10)
```

## The `divmod` block

- **Label:** `divmod(%1, %2)` — inputs `A` (default `10`), `B` (default `3`).
  Returns the quotient and remainder together.

```python
divmod(10, 3)
```

## The `hex` block

- **Label:** `hex(%1)` — input `value` (default `255`). Hexadecimal text of a number.

```python
hex(255)
```

## The `ord` block

- **Label:** `ord(%1)` — input `value` (default `A`). The character's code number.

The field is inserted verbatim, so quote the character to pass a letter:

```python
ord("A")
```

This returns `65`.

## Worked example

```python
import random

roll = random.randint(1, 6)
print(roll)
```

## Next

Continue to [String](../string/index.md)
