# Editor Walkthrough

Now that you've run your first program, let's slow down and get comfortable with
the SemiBlock editor itself. Knowing your way around makes every future project
faster and less frustrating.

## The three-button toolbar

Across the top of the editor are three buttons:

- **Clear** — empties the workspace so you can start fresh.
- **load** — restores a previously saved workspace.
- **Save** — stores your current blocks so you can come back later.

You'll use these in [Save / Load / Clear](save-load.md).

## The split layout

Below the toolbar the screen is split into two panes:

```text
┌───────────────────────────┬───────────────────────┐
│  Generated MicroPython     │   Block workspace      │
│  (read-only code pane)     │   (drag & arrange)     │
└───────────────────────────┴───────────────────────┘
```

- **Generated MicroPython (code pane)** — read-only, updates live as you build.
- **Block workspace** — the canvas where you drag, snap, and arrange blocks.

The toolbox of categories lives along the edge of the workspace.

## The workspace canvas

The workspace is an infinite canvas. You can:

- **Pan** by dragging empty space.
- **Zoom** with the mouse wheel or trackpad pinch.
- **Right-click** a block for options like duplicate, add comment, or delete.

More on this in [Workspace, toolbox, and code pane](workspace.md).

## The toolbox

The toolbox holds every block, grouped into categories and separated into
**Python**, **Hardware Blocks**, and **Sensor & AI Blocks** sections. Click a
category to reveal its flyout of blocks.

## The live code pane

The code pane is your constant feedback loop. Whatever you build on the right
appears as MicroPython on the left:

```python
led = Pin(2, Pin.OUT)
led.on()
```

Because it's read-only, you can trust it always matches your blocks exactly.

## A built-in simulator

SemiBlock also includes a **simulator** so you can test ideas — like moving a
sprite — without hardware. The **Motion**, **Looks**, and **Events** categories
feed it. See [Built-in simulator](simulator.md).

## A good habit

Keep one eye on the code pane while you work. Every block you touch teaches you a
little more MicroPython, and you'll spot mistakes the moment they appear.

## Try it yourself

Drag three different blocks onto the workspace, then practice panning and zooming
the canvas. Right-click one block and explore its menu. Finally press **Clear**
to reset — you now know the whole editor surface.

## Next

[Workspace, toolbox, and code pane](workspace.md)
