# `getcwd`, `chdir`, `stat`, `uname`

> ![](img/info1.png){width=inherit}

These blocks report or change where you are in the file system and give
information about files and the device. Each needs an
[`import os`](../language/imports.md) block.

## The `osGetcwd` block

- **Label:** `os.getcwd()` — no inputs. Returns the current working directory.

```python
os.getcwd()
```

> ![](img/info2.png){width=inherit}

## The `osChdir` block

- **Label:** `os.chdir(%1)` — input `path` (default `/new_folder`). Changes the
  current directory. Quote the path.

```python
os.chdir(/new_folder)
```

> ![](img/info3.png){width=inherit}

With a quoted path:

```python
os.chdir("/new_folder")
```

> ![](img/info4.png){width=inherit}

## The `osStat` block

- **Label:** `os.stat(%1)` — input `path` (default `/file.txt`). Returns details
  about a file, such as its size.

```python
os.stat(/file.txt)
```

> ![](img/info5.png){width=inherit}

With a quoted path:

```python
os.stat("/file.txt")
```

> ![](img/info6.png){width=inherit}

## The `osUname` block

- **Label:** `os.uname()` — no inputs. Returns information about the MicroPython
  system and board.

```python
os.uname()
```

> ![](img/info7.png){width=inherit}

## Worked example

```python
import os

print(os.getcwd())
print(os.uname())
```

> ![](img/info8.png){width=inherit}

## Next

Continue to [`sync`, `system`, `urandom`](misc.md)
