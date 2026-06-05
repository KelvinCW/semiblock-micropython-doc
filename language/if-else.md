# `if` / `elif` / `else`

Decisions let your program react. The **if**, **elif**, and **else** blocks run
different code depending on whether a condition is true.

## The `ifLoop` block

- **Label:** `if %1:`
- **Input:** `conditions` — the test (default `1==1`).
- **Body:** runs only when the test is true.

```python
if 1==1:
	print("yes")
```

## The `elseIfLoop` block

- **Label:** `elif %1:`
- **Input:** `conditions` — another test (default `1==1`).
- **Body:** runs when the previous `if` was false **and** this test is true.

```python
elif 1==1:
	print("maybe")
```

## The `elseLoop` block

- **Label:** `else:`
- **Body:** runs when every test above it was false.

```python
else:
	print("no")
```

## Stacking them together

Place an `if`, then optional `elif` block(s), then an optional `else` directly
below one another. Each generates one part of the chain:

```python
if temp > 30:
	print("hot")
elif temp > 20:
	print("warm")
else:
	print("cool")
```

The board checks each test from top to bottom and runs the **first** matching
block, then skips the rest.

## Next

Continue to [`print` and comments](print-comment.md)
