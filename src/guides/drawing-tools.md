# Drawing Tools

Master the brush system in Celstomp to create smooth, expressive line work.

## The Brush Tool

The brush is your primary drawing tool. Understanding its capabilities helps you work more efficiently.

### Basic Usage

1. Select the Brush tool (shortcut: `1`)
2. Adjust size with `[` and `]` keys
3. Pick a color from the color picker
4. Draw on the canvas

### Size Control

**Keyboard shortcuts:**
- `[` - Decrease size
- `]` - Increase size
- `Shift + [` - Decrease size faster
- `Shift + ]` - Increase size faster

**Size range:** 1 to 200 pixels

### Brush Shapes

Celstomp supports multiple brush shapes:

- **Round** - Standard circular brush (default)
- **Square** - Hard-edged square
- **Custom** - Load custom shapes

Change shape in the tool options panel.

### Pressure Sensitivity

With a drawing tablet, enable pressure for natural feel:

**Pressure affects:**
- **Size** - Light touch = small, hard press = large
- **Opacity** - Light touch = transparent, hard press = opaque
- **Both** - Combined effect

**Enable pressure:**
1. Tool options > Pressure
2. Check "Enable pressure"
3. Adjust pressure curve if needed

### Anti-Aliasing

Brushes use anti-aliasing for smooth edges:

- **Enabled** - Smooth, blended edges (recommended)
- **Disabled** - Hard, pixelated edges (pixel art)

Toggle in tool options.

## Advanced Brush Techniques

### Straight Lines

Draw perfect straight lines:

1. Click starting point
2. Hold `Shift`
3. Click ending point
4. Or Shift+drag for constrained angles

**Constrained angles:**
- 0° - Horizontal
- 45° - Diagonal
- 90° - Vertical

### Quick Eyedropper

Sample colors without switching tools:

1. Hold `Alt` key
2. Click to sample color
3. Release `Alt` to continue drawing

### Pan While Drawing

Navigate while drawing:

1. Hold `Space` key
2. Drag to pan canvas
3. Release `Space` to resume drawing

### Blend Modes

Change how brush strokes blend:

| Mode | Effect |
|------|--------|
| Normal | Standard overlay |
| Multiply | Darkens underlying colors |
| Screen | Lightens underlying colors |
| Overlay | Combines multiply and screen |

Good for:
- **Multiply** - Shadows, line work over colors
- **Screen** - Highlights, glow effects
- **Overlay** - Texture, lighting

## Eraser Tool

Clean up and refine your drawings.

### Basic Erasing

1. Select Eraser tool (shortcut: `2`)
2. Adjust size
3. Erase unwanted pixels

### Soft vs Hard Eraser

- **Soft** - Anti-aliased edges (smooth)
- **Hard** - Sharp edges (pixelated)

Use soft for natural blending, hard for precise cleanup.

### Partial Erasing

Lower eraser opacity to soften rather than remove:

1. Set opacity to 50%
2. Erase over area
3. Creates partial transparency

Good for:
- Softening hard edges
- Creating gradients
- Subtle corrections

## Fill Tools

### Fill Brush

The Fill Brush combines brush control with paint bucket functionality:

**How it works:**
1. Select Fill Brush (shortcut: `3`)
2. Set size (affects fill area)
3. Click in enclosed area
4. Fills area with current color

**Tolerance:**
- Low tolerance - Fills only very similar colors
- High tolerance - Fills broader color range
- Adjust for line art with gaps

**Tips:**
- Use on COLOR or FILL layer
- Close gaps in line art first
- Lower tolerance for precise fills

### Fill Eraser

Remove fills intelligently:

**How it works:**
1. Select Fill Eraser (shortcut: `4`)
2. Click on fill to remove
3. Preserves line art
4. Smart detection of fill areas

**Use for:**
- Cleaning up color spills
- Removing unwanted fills
- Adjusting color areas

## Brush Workflows

### Gesture Drawing

For quick motion sketches:

1. **Large brush** (50-100px)
2. **50% opacity**
3. **Quick, loose strokes**
4. **Focus on motion, not details**
5. **Work on LINE layer**

### Line Art

For clean outlines:

1. **Medium brush** (3-10px)
2. **100% opacity**
3. **Smooth, confident strokes**
4. **Consistent line weight**
5. **Use straight lines (Shift) for hard edges**

### Detailing

For fine details:

1. **Small brush** (1-3px)
2. **Zoom in to 200%**
3. **Steady hand or tablet**
4. **Take your time**

### Shading

For shadows and depth:

1. **Switch to SHADE layer**
2. **Large, soft brush**
3. **Lower opacity (20-50%)**
4. **Build up gradually**
5. **Consider light source**

## Brush Settings Reference

### Optimal Settings by Task

| Task | Size | Opacity | Shape | Anti-alias |
|------|------|---------|-------|------------|
| Gesture | 50-100 | 50% | Round | Yes |
| Line art | 3-10 | 100% | Round | Yes |
| Details | 1-3 | 100% | Round | Yes |
| Shading | 20-50 | 20-50% | Round | Yes |
| Fills | 10-50 | 100% | Round | Yes |
| Cleanup | 5-20 | 100% | Hard | No |
| Texture | 10-30 | 50% | Custom | Yes |

### Pressure Curves

Adjust how pressure affects output:

- **Linear** - Direct 1:1 mapping
- **Soft** - More sensitive at light touch
- **Hard** - More sensitive at firm press
- **Custom** - Define your own curve

Experiment to find what feels natural.

## Troubleshooting

**Brush feels laggy:**
- Close other browser tabs
- Reduce brush size
- Disable anti-aliasing
- Check browser performance

**Lines look jagged:**
- Enable anti-aliasing
- Use larger brush size
- Draw faster (less point sampling)
- Check browser zoom level

**Pressure not working:**
- Verify tablet drivers installed
- Check pressure enabled in settings
- Test in other applications
- Try different browser

**Colors look wrong:**
- Check blend mode
- Verify correct layer
- Check layer opacity
- Ensure no selection active

**Can't draw:**
- Verify correct layer selected
- Check layer not locked
- Ensure layer visible
- Check tool not disabled

## Tips from the Pros

### Line Weight

Vary line weight for visual interest:

- **Thick** - Ground planes, heavy objects
- **Medium** - General outlines
- **Thin** - Details, light objects
- **Variable** - Organic, natural feel

### Line Quality

Good line art has:

- **Confidence** - Commit to the stroke
- **Consistency** - Similar lines look similar
- **Variety** - Different weights for interest
- **Purpose** - Every line serves a reason

### Brush Economy

Don't overwork:

- **Single stroke** when possible
- **Fewer lines** = cleaner art
- **Let mistakes go** - Perfectionism kills flow
- **Work loose first** - Details come later

## Exercises

### Exercise 1: Straight Lines

Practice straight lines:

1. Draw 10 horizontal lines
2. Draw 10 vertical lines
3. Draw 10 diagonal lines
4. Focus on confident, single strokes

### Exercise 2: Circles

Practice circular motion:

1. Draw 10 circles clockwise
2. Draw 10 circles counter-clockwise
3. Vary sizes
4. Focus on smooth motion

### Exercise 3: Line Weight

Practice varying weight:

1. Draw the same object 3 times
2. Use thin lines for one
3. Use thick lines for another
4. Use variable weight for the third
5. Compare results

## See Also

- [Selection Tools](./selection-tools.md) - Combine with brush
- [Color & Palette](./color-palette.md) - Working with color
- [Animation Workflow](./animation-workflow.md) - Drawing in motion
