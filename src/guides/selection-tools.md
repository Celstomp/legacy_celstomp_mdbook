# Selection Tools

Selection tools let you isolate and manipulate specific areas of your artwork with precision.

## Lasso Tool

The lasso creates freehand selections of any shape.

### Basic Usage

1. Select Lasso tool (shortcut: `5`)
2. Click and drag to draw selection boundary
3. Release to close selection
4. Marching ants indicate active selection

### Selection Modes

Modify selections with modifier keys:

- **New selection** - Default (replaces current)
- **Add to selection** - Hold `Shift` while drawing
- **Subtract from selection** - Hold `Alt` while drawing
- **Intersect** - Hold `Shift+Alt`

### Moving Selections

Once selected:

- **Drag inside** - Move selection contents
- **Arrow keys** - Nudge by 1 pixel
- **Shift+arrows** - Nudge by 10 pixels

### Closing the Selection

The lasso automatically closes:

- **Release mouse** - Draws line to start point
- **Double-click** - Closes with straight line
- **Return to start** - Click to close

### Tips for Lasso

- Draw slowly for precision
- Use for organic, irregular shapes
- Combine multiple selections for complex areas
- Great for isolating characters from backgrounds

## Rectangle Select

Create rectangular or square selections quickly.

### Basic Usage

1. Select Rectangle tool (shortcut: `6`)
2. Click and drag to create rectangle
3. Release to complete selection

### Constrained Selections

- **Square** - Hold `Shift` while dragging
- **From center** - Hold `Alt` while dragging
- **Square from center** - Hold `Shift+Alt`

### Precise Selections

For exact dimensions:

1. Create rough selection
2. **Selection menu** > "Transform Selection"
3. Enter exact width/height
4. Or drag handles to resize

### Moving and Resizing

With selection active:

- **Drag inside** - Move contents
- **Drag handles** - Resize selection
- **Shift+drag handles** - Constrain proportions
- **Esc** - Cancel

## Working with Selections

### Drawing Within Selections

When you have a selection:

- **Brush/Eraser** - Affects only selected area
- **Fill** - Fills only selected area
- **Clear** - Deletes selected pixels

This is useful for:
- Coloring specific areas
- Erasing precisely
- Protecting finished work

### Copy and Paste

Standard clipboard operations:

- **Ctrl+C** - Copy selection
- **Ctrl+X** - Cut selection
- **Ctrl+V** - Paste
- **Ctrl+D** - Duplicate

Pasted content:
- Appears as floating selection
- Can be moved before committing
- Press `Enter` or click to commit

### Inverting Selections

Select the opposite area:

**Select > Invert** or `Ctrl+Shift+I`

Useful for:
- Selecting backgrounds
- Isolating negative space
- Quick area reversal

### Deselecting

Clear the selection:

- **Esc** key
- **Ctrl+D** (deselect)
- Click outside selection
- **Select > Deselect**

### Feathering

Soften selection edges:

1. Create selection
2. **Select > Feather**
3. Enter pixel radius (1-50)
4. Edges become gradually transparent

Good for:
- Soft shadows
- Glow effects
- Smooth transitions

## Advanced Selection Techniques

### Magic Wand

Select similar colors:

1. **Select > Magic Wand**
2. Click on color to select
3. Adjust tolerance
4. Add/subtract to refine

### Color Range

Select specific colors:

1. **Select > Color Range**
2. Choose color
3. Adjust fuzziness
4. Preview selection

### Transform Selection

Modify selection boundary:

- **Scale** - Resize selection area
- **Rotate** - Rotate selection
- **Skew** - Slant selection
- **Perspective** - Add depth

Access via **Select > Transform** or `Ctrl+T`

### Save and Load Selections

Save complex selections:

1. **Select > Save Selection**
2. Name the selection
3. **Select > Load Selection** to restore

Useful for:
- Reusing complex selections
- Character outlines
- Background elements

## Selection Workflows

### Character Isolation

Separate character from background:

1. Use **Lasso** to trace character
2. **Ctrl+C** to copy
3. **Ctrl+V** to paste
4. Move to new layer if needed
5. Original layer now has hole (fill or delete)

### Color Area Selection

Select specific color regions:

1. **Magic Wand** on color area
2. Adjust tolerance if needed
3. Add more areas with Shift+click
4. Modify color within selection

### Detail Work

Isolate areas for detail:

1. **Rectangle** select area
2. Zoom in
3. Work on details
4. Deselect when done

### Animation Cleanup

Clean up rough animation:

1. **Lasso** select messy area
2. **Delete** or **Cut**
3. Redraw cleanly
4. Repeat as needed

## Selection Shortcuts

### Essential Shortcuts

| Action | Shortcut |
|--------|----------|
| Select all | `Ctrl+A` |
| Deselect | `Ctrl+D` or `Esc` |
| Invert | `Ctrl+Shift+I` |
| Copy | `Ctrl+C` |
| Cut | `Ctrl+X` |
| Paste | `Ctrl+V` |
| Duplicate | `Ctrl+J` |
| Transform | `Ctrl+T` |
| Fill | `Alt+Delete` (foreground) |
| Fill bg | `Ctrl+Delete` (background) |

### Nudge Shortcuts

| Action | Shortcut |
|--------|----------|
| Nudge 1px | Arrow keys |
| Nudge 10px | Shift+arrows |

## Troubleshooting

**Can't create selection:**
- Check if layer is locked
- Verify layer is visible
- Ensure not in text edit mode

**Selection disappears:**
- Did you deselect? (Esc)
- Was selection too small?
- Check if selection is hidden

**Can't move selection:**
- Make sure you're clicking inside selection
- Check if layer is locked
- Verify selection is active

**Selection moves whole layer:**
- You may have selected the layer, not pixels
- Ensure you have pixel selection (marching ants)
- Check if you clicked the layer thumbnail

**Magic wand selects too much:**
- Lower tolerance
- Check if contiguous is enabled
- Try clicking a different spot

## Tips and Tricks

### Selection Precision

For precise work:

- Zoom in to 200-400%
- Use small brush for selection edges
- Take your time with lasso
- Use Shift to add small areas

### Combining Selections

Build complex selections:

1. Lasso main shape
2. Shift+lasso to add details
3. Alt+lasso to remove areas
4. Result is precise selection

### Temporary Selection

Quick selections without tools:

- **Ctrl+click layer thumbnail** - Select all non-transparent
- **Ctrl+Alt+click** - Subtract from selection
- **Ctrl+Shift+click** - Add to selection

### Selection Borders

Use selections for effects:

1. Create selection
2. **Edit > Stroke**
3. Choose color and width
4. Creates border around selection

## Exercises

### Exercise 1: Basic Shapes

Practice selections:

1. Rectangle select a box
2. Fill with color
3. Lasso select a circle
4. Fill with different color
5. Practice adding and subtracting

### Exercise 2: Character Cutout

Isolate a character:

1. Open a drawing with clear subject
2. Use lasso to trace character
3. Copy and paste
4. Verify clean separation

### Exercise 3: Complex Selection

Build complex selection:

1. Rectangle select large area
2. Shift+lasso add details
3. Alt+lasso remove holes
4. Result should be precise shape

## See Also

- [Drawing Tools](./drawing-tools.md) - Draw within selections
- [Color & Palette](./color-palette.md) - Fill selections
- [Animation Workflow](./animation-workflow.md) - Selections in motion
