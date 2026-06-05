# `startswith`, `endswith`, `length`

These blocks answer questions about a string: does it begin or end with certain
text, and how long is it? Each is a **value block**.

Text fields are inserted **verbatim** — type quotes around literal text.

## The `stringStartsWith` block

- **Label:** `%1.startswith(%2)` — inputs `value` (default `text`), `prefix`
  (default `t`). Returns `True` if the string starts with the prefix.

```python
text.startswith(t)
```

## The `stringEndsWith` block

- **Label:** `%1.endswith(%2)` — inputs `value` (default `text`), `suffix`
  (default `t`). Returns `True` if the string ends with the suffix.

```python
text.endswith(t)
```

## The `stringLength` block

- **Label:** `len(%1)` — input `value` (default `text`). Counts the characters.

```python
len(text)
```

## Worked example

With quoted literals:

```python
filename = "report.csv"
if filename.endswith(".csv"):
	print("It is a CSV file")
print(len(filename))
```

`startswith` and `endswith` return `True` or `False`, which makes them perfect
inputs for an [`if`](../language/if-else.md) block.

## Next

Continue to [List](../list/index.md)
