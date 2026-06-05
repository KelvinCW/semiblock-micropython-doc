# `pass` statement

`pass` is the "do nothing" block. It is a placeholder that lets you write a loop,
function, or condition that is syntactically complete but has no body yet.

## The `pass` block

- **Label:** `pass`
- **Inputs:** none.

It always generates exactly one line:

```python
pass
```

## Why would you want to do nothing?

In MicroPython, blocks like `if`, `while`, and `def` **must** contain at least
one line. If you are not ready to fill one in, `pass` keeps the program valid:

```python
def todo_later():
	pass
```

This defines a function that does nothing for now — you can replace `pass` with
real blocks later.

## Worked example

An empty branch you plan to finish:

```python
if button_pressed:
	pass
else:
	print("waiting")
```

The `if` branch is reserved with `pass`; the `else` branch already prints a
message.

## Next

Continue to [Variables](variables.md)
