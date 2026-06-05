# `sync`, `system`, `urandom`

A few extra `os` blocks handle flushing data to storage, running system
commands, and generating random bytes. Each needs an
[`import os`](../language/imports.md) block.

## The `osSync` block

- **Label:** `os.sync()` — no inputs. Flushes pending writes to the file system so
  nothing is lost.

```python
os.sync()
```

## The `osSystem` block

- **Label:** `os.system(%1)` — input `command` (default `ls`). Runs a system
  command. The field is inserted **verbatim**, so quote it.

```python
os.system(ls)
```

With a quoted command:

```python
os.system("ls")
```

> Note: not every MicroPython build supports `os.system`. Test it on your board.

## The `osUrandom` block

- **Label:** `os.urandom(%1)` — input `n` (default `16`). Returns `n` random
  bytes — useful for keys or tokens.

```python
os.urandom(16)
```

## Worked example

```python
import os

with open("/data.txt", "w") as f:
	f.write("hello")
os.sync()
```

Calling `os.sync()` after writing makes sure the data is safely stored.

## Next

Continue to [CSV files](../csv/index.md)
