# Tools Overview

Celstomp provides a focused set of tools designed for 2D animation. Each tool serves a specific purpose in the animation workflow.

## Tool Categories

Tools are organized by function:

### Drawing Tools
Create and modify artwork:
- Brush
- Eraser
- Fill Brush
- Fill Eraser

### Selection Tools
Select and manipulate areas:
- Lasso
- Rectangle Select
- Eyedropper

### View Tools
Navigate the canvas:
- Hand (pan)
- Zoom

## Tool Selection

### Keyboard Shortcuts

| Tool | Shortcut |
|------|----------|
| Brush | `1` |
| Eraser | `2` |
| Fill Brush | `3` |
| Fill Eraser | `4` |
| Lasso | `5` |
| Rectangle Select | `6` |
| Eyedropper | `7` or hold `Alt` |
| Hand/Pan | `Space` (hold) |

### Tool Panel

Click tool icons in the left panel:
- Active tool is highlighted
- Tool options appear below
- Some tools have sub-modes

## Tool Options

Most tools have adjustable settings:

### Size

Adjust tool size with:
- `[` and `]` keys
- Size slider in tool options
- Scroll wheel (if enabled)

Range: 1-200 pixels

### Opacity/Strength

For brushes and erasers:
- 1-100% opacity
- Lower = more transparent
- Affects how strongly tool applies

### Shape

Brush tool supports different shapes:
- Round (default)
- Square
- Custom shapes (if loaded)

### Pressure

With a drawing tablet:
- Enable pressure sensitivity
- Pressure affects size and/or opacity
- Adjust pressure curve in settings

## Tool-Specific Features

### Brush Tool

The primary drawing tool:

- **Freehand drawing** - Draw any shape
- **Straight lines** - Shift+drag for straight lines
- **Pressure support** - Tablet pressure control
- **Anti-aliasing** - Smooth edges
- **Blend modes** - How new paint mixes with existing

**Tips:**
- Use for outlines, sketches, details
- Adjust size for line weight variation
- Enable pressure for natural feel

### Eraser Tool

Remove pixels:

- **Soft eraser** - Anti-aliased edges
- **Hard eraser** - Sharp edges
- **Size variation** - Same as brush
- **Partial opacity** - Can soften instead of fully erase

**Tips:**
- Use for corrections and cleanup
- Lower opacity for softening
- Be careful on wrong layers

### Fill Brush

Paint bucket with brush behavior:

- **Fills enclosed areas** - Like paint bucket
- **Brush-sized** - Fills within brush radius
- **Tolerance** - How different colors can be
- **Anti-aliased** - Smooth fill edges

**Tips:**
- Good for flat color work
- Use on COLOR or FILL layer
- Adjust tolerance for line art gaps

### Fill Eraser

Erase fills while preserving lines:

- **Smart detection** - Targets fill areas
- **Preserves lines** - Won't erase LINE layer content
- **Tolerance** - Controls detection sensitivity

**Tips:**
- Clean up color spills
- Remove unwanted fills
- Safer than regular eraser for color work

### Lasso Tool

Freehand selection:

- **Draw selection boundary** - Any shape
- **Add to selection** - Shift+lasso
- **Subtract from selection** - Alt+lasso
- **Move selection** - Drag inside

**Tips:**
- Use for organic shapes
- Good for irregular areas
- Combine with modifiers

### Rectangle Select

Box selection:

- **Click and drag** - Create rectangle
- **Square** - Shift+drag
- **From center** - Alt+drag
- **Move** - Drag inside selection

**Tips:**
- Quick selections
- Good for hard edges
- Use for canvas areas

### Eyedropper

Sample colors:

- **Click** - Sample single pixel
- **Average** - Sample average of area
- **All layers** - Or current layer only
- **Shortcut** - Hold `Alt` with any tool

**Tips:**
- Maintain color consistency
- Sample from reference
- Use averaged for smoother colors

## Working with Selections

### Creating Selections

1. Choose Lasso or Rectangle tool
2. Draw selection area
3. Marching ants show selection boundary

### Selection Operations

Once you have a selection:

- **Draw inside only** - Brush/eraser affects selection only
- **Delete contents** - Press Delete
- **Move** - Drag selection
- **Cut/Copy/Paste** - Standard shortcuts
- **Deselect** - `Esc` or click outside

### Selection Modifiers

- **Shift** - Add to selection
- **Alt** - Subtract from selection
- **Shift+Alt** - Intersect selections

## Advanced Tool Usage

### Modifier Keys

Common modifiers work across tools:

- **Shift** - Constrain (straight lines, squares)
- **Alt** - Alternate behavior (eyedropper, from center)
- **Ctrl** - Special functions (copy while dragging)
- **Space** - Pan while drawing

### Tool Presets

Save tool configurations:

1. Adjust tool settings
2. **Tool menu** > "Save Preset"
3. Name the preset
4. Access from preset list

Useful for:
- Consistent brush sizes
- Specific eraser settings
- Project-specific configurations

### Temporary Tool Switch

Hold a key to temporarily switch tools:

- **Space** - Hand tool (pan)
- **Alt** - Eyedropper
- **Shift** - Straight line constraint

Release to return to previous tool.

## Tool Tips by Workflow

### Sketching Phase

- Use **Brush** at 50% opacity
- Large size for gestures
- Work on LINE layer
- Don't worry about cleanup

### Cleanup Phase

- Use **Brush** at 100% opacity
- Smaller, consistent size
- Clean, confident strokes
- Use **Eraser** for corrections

### Coloring Phase

- **Fill Brush** for large areas
- **Brush** for details
- Work on COLOR layer
- Use **Eyedropper** for consistency

### Animation Phase

- Use onion skin
- **Brush** for drawings
- **Lasso** for adjustments
- Test frequently with playback

## Troubleshooting

**Tool not working:**
- Check if correct layer is selected
- Verify layer isn't locked
- Ensure no modal dialog is open
- Check if tool is disabled

**Brush looks wrong:**
- Check size setting
- Verify opacity
- Check blend mode
- Ensure correct layer

**Selection issues:**
- `Esc` to clear selection
- Check if selection is active (marching ants)
- Verify selection mode (add/subtract)

**Pressure not working:**
- Check tablet drivers
- Verify pressure enabled in settings
- Test in other apps
- Try different browser

## See Also

- [Drawing Tools](../guides/drawing-tools.md) - Detailed brush guide
- [Selection Tools](../guides/selection-tools.md) - Selection techniques
- [Keyboard Shortcuts](../guides/shortcuts.md) - All shortcuts
