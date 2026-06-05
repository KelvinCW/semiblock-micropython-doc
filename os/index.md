# Operating System (`os` module)

The **os** category talks to the device's file system and system functions:
listing files, making folders, checking the current directory, and more. The
blocks use MicroPython's `os` module.

Add an [`import os`](../language/imports.md) block to your program so these
blocks work. Path fields are inserted **verbatim**, so quote them (e.g.
`"/data.txt"`).

## What you will learn

- [Listing, removing, renaming files](files.md)
- [Making and removing directories](dirs.md)
- [`getcwd`, `chdir`, `stat`, `uname`](info.md)
- [`sync`, `system`, `urandom`](misc.md)

## A quick taste

```python
import os

os.listdir("/")
```

## Next

Continue to [Listing, removing, renaming files](files.md)
