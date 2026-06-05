# Listing, removing, renaming files

These blocks manage individual files on the device. Each needs an
[`import os`](../language/imports.md) block, and path fields are inserted
**verbatim** — quote them.

## The `osListDir` block

- **Label:** `os.listdir(%1)` — input `path` (default `/`). Lists the names in a
  folder.

```python
os.listdir(/)
```

With a quoted path:

```python
os.listdir("/")
```

## The `osRemove` block

- **Label:** `os.remove(%1)` — input `path` (default `/file.txt`). Deletes a file.

```python
os.remove(/file.txt)
```

With a quoted path:

```python
os.remove("/file.txt")
```

## The `osRename` block

- **Label:** `os.rename(%1, %2)` — inputs `oldPath` (default `/old.txt`),
  `newPath` (default `/new.txt`). Renames or moves a file.

```python
os.rename(/old.txt, /new.txt)
```

With quoted paths:

```python
os.rename("/old.txt", "/new.txt")
```

## Worked example

```python
import os

print(os.listdir("/"))
os.rename("/log.txt", "/log_old.txt")
```

## Next

Continue to [Making and removing directories](dirs.md)
