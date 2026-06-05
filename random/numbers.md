# `random`, `randint`, `randrange`, `uniform`

These blocks generate random numbers in different ways. Each is a **value
block**, and each needs an [`import random`](../language/imports.md) block in
your program.

## The `random` block

- **Label:** `random()` — no inputs. A random decimal between 0.0 and 1.0.

```python
random.random()
```

## The `randint` block

- **Label:** `randint(%1, %2)` — inputs `a` (default `0`), `b` (default `10`).
  A whole number from `a` to `b`, inclusive.

```python
random.randint(0, 10)
```

## The `randrange` block

- **Label:** `randrange(%1, %2, %3)` — inputs `start` (default `0`), `stop`
  (default `10`), `step` (default `1`). A whole number from `start` up to (but
  not including) `stop`, counting by `step`.

```python
random.randrange(0, 10, 1)
```

## The `uniform` block

- **Label:** `uniform(%1, %2)` — inputs `a` (default `0`), `b` (default `1`).
  A random decimal between `a` and `b`.

```python
random.uniform(0, 1)
```

## Worked example

```python
import random

coin = random.randint(0, 1)
even = random.randrange(0, 100, 2)
temp = random.uniform(20.0, 25.0)
print(coin, even, temp)
```

## Next

Continue to [`choice`, `shuffle`, `sample`](sequence.md)
