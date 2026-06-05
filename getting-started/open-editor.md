# Opening the SemiBlock editor

With your board flashed and connected, it's time to open the **SemiBlock
MicroPython editor** — the visual canvas where you'll build programs from blocks.

## What the editor is

The editor is a web app built on **Blockly**. It runs in your browser and shows
three main areas side by side:

- A **toolbox** of categorized blocks on the left.
- A **workspace** canvas in the middle where you assemble blocks.
- A **code pane** that shows the generated MicroPython, updating live.

You'll explore each area in the [editor walkthrough](editor-tour.md).

## Running the editor locally

SemiBlock is a standard Node.js web project. From the project folder:

```bash
npm install
npm start
```

The `start` script launches a development server and opens the editor in your
browser automatically. Under the hood it runs Webpack in development mode.

To create an optimized build you can host yourself:

```bash
npm run build
```

This produces the static editor files (under the build output folder) that you
can upload to any web server.

## What you should see

When the page loads you'll see three buttons across the top —
**Clear**, **load**, and **Save** — followed by the split view:

```text
[ Clear ] [ load ] [ Save ]
┌───────────────────────────┬───────────────────────┐
│  Generated MicroPython     │                       │
│  (read-only code pane)     │     Block workspace    │
│                            │     (drag blocks here) │
└───────────────────────────┴───────────────────────┘
```

The code pane starts empty because there are no blocks yet. As soon as you drag a
block in, MicroPython appears.

## First thing to try

1. Click a category in the toolbox to open its flyout of blocks.
2. Drag any block onto the workspace.
3. Watch the **Generated MicroPython** pane fill in.

Don't worry about getting it right — you can always press **Clear** to start over.

## Try it yourself

Open the editor, then click the **Machine** category and drag the
**createMainMethod** block onto the canvas. This block is the usual starting
point for a program — everything you snap inside it becomes your main code.

## Next

[Your First Program: Blink an LED](first-program.md)
