# Layers System

Layers are essential for organizing complex artwork. Think of them as transparent sheets stacked on top of each other.

## Layer Types

Celstomp provides 5 built-in layer types, each designed for a specific purpose:

### LINE Layer

**Purpose:** Outlines, sketches, and line art

- Top of the layer stack (visible over everything)
- Best for: rough sketches, clean line art, details
- Default color: Black or dark colors
- Tip: Keep line work on its own layer for easy editing

### SHADE Layer

**Purpose:** Shadows, depth, and shading

- Second from top
- Best for: drop shadows, cell shading, gradients
- Blend mode: Multiply (default)
- Tip: Use darker versions of your base colors

### COLOR Layer

**Purpose:** Flat colors and base fills

- Middle layer
- Best for: solid color areas, base tones
- Usually filled with paint bucket or drawn with brush
- Tip: Keep colors flat for easy selection and editing

### FILL Layer

**Purpose:** Automatic fills and color areas

- Second from bottom
- Best for: paint bucket fills, selection fills
- Works with the Fill Brush tool
- Tip: Use this when you want fills separate from hand-drawn colors

### PAPER Layer

**Purpose:** Background and reference

- Bottom of the stack (behind everything)
- Best for: background art, reference images, paper texture
- Doesn't animate (unless you want it to)
- Tip: Import reference images here

## Layer Stack Order

The layer order (top to bottom) is:

```
1. LINE
2. SHADE
3. COLOR
4. FILL
5. PAPER
```

This order mimics traditional animation cels where line art sits on top of painted colors.

## Working with Layers

### Selecting Layers

Click a layer name in the layers panel to make it active:

- Active layer is highlighted
- New drawings appear on the active layer
- Each layer has its own set of cels per frame

### Layer Visibility

Click the eye icon to toggle layer visibility:

- Eye open = layer visible
- Eye closed = layer hidden
- Hidden layers don't export
- Shortcut: number keys (1-5) toggle layers

### Layer Opacity

Adjust opacity with the slider:

- 100% = fully opaque
- 0% = fully transparent
- Use for subtle effects
- Lower shade layer opacity for softer shadows

### Blend Modes

Change how layers interact:

| Mode | Effect |
|------|--------|
| Normal | Standard overlay |
| Multiply | Darkens (good for shadows) |
| Screen | Lightens (good for glows) |
| Overlay | Combines multiply and screen |
| Add | Adds colors (good for light effects) |

To change: **Layer menu** > "Blend Mode"

## Advanced Layer Features

### Solo Mode

Isolate one layer:

1. **Alt+click** layer name
2. **Or** click the solo button
3. Only that layer remains visible
4. Click again or select another layer to exit solo mode

Useful for focusing on specific layer work.

### Lock Layer

Prevent accidental changes:

1. **Click lock icon** on layer
2. Layer can't be drawn on or modified
3. Lock icon appears closed
4. Click again to unlock

Lock layers you're finished with.

### Layer Colors

Change the layer color indicator:

1. **Right-click layer** > "Layer Color"
2. Choose a color
3. Helps organize similar layers visually

### Rename Layers

While you can't rename the built-in types, you can work around this:

- Use layer colors to categorize
- Add notes in frame markers
- Organize by layer order

## Layer Strategies

### Character Animation

Typical setup for a character:

- **LINE** - Clean outlines
- **SHADE** - Body shadows
- **COLOR** - Skin and clothing colors
- **FILL** - Base fills (optional)
- **PAPER** - Background

### Effects and Particles

For special effects:

- **LINE** - Effect outlines
- **SHADE** - Shadow effects
- **COLOR** - Effect colors (glow, magic, etc.)
- **FILL** - Particle fills
- **PAPER** - Scene background

### Background Elements

For moving backgrounds:

- Animate background on PAPER layer
- Or create separate layer groups (if implementing custom layers)
- Keep foreground elements on upper layers

## Tips for Layer Management

### Keep It Organized

- Start with LINE for sketches
- Move to COLOR for fills
- Add SHADE last for depth
- Don't draw on wrong layers

### Merge When Done

For finished work:

- Flatten layers before final export (optional)
- Or keep layered for future edits
- JSON export preserves all layers

### Color Coordination

- Use consistent colors across layers
- Reference colors from your palette
- Consider how layers blend together

### Performance

More layers = more memory:

- Merge layers when possible
- Delete unused cels
- Flatten for very long animations

## Common Workflows

### From Sketch to Final

1. **Rough on LINE** - Quick motion sketches
2. **Clean up LINE** - Final line art
3. **Add COLOR** - Flat fills
4. **Add SHADE** - Shadows and depth
5. **Refine** - Adjust and polish

### Quick Coloring

1. **Select COLOR layer**
2. **Use Fill Brush** on enclosed areas
3. **Switch to LINE** for details
4. **Add SHADE** for dimension

### Background Integration

1. **Import to PAPER** - File > Import > Image
2. **Lower opacity** - To trace over
3. **Draw on upper layers** - Character on LINE/COLOR
4. **Restore opacity** - Or replace with final bg

## Troubleshooting

**Drawing not showing up:**
- Check if you're on the right layer
- Verify layer visibility (eye icon)
- Check layer opacity isn't zero
- Ensure no selection is hiding it

**Colors look wrong:**
- Check blend mode (Multiply darkens)
- Verify you're on intended layer
- Check for overlapping layers

**Can't draw on layer:**
- Layer might be locked
- Check layer visibility
- Make sure cel is exposed on current frame

## See Also

- [Drawing Tools](../guides/drawing-tools.md) - Tools for each layer
- [Color & Palette](../guides/color-palette.md) - Working with colors
- [Canvas & Viewport](./canvas.md) - Viewing your layers
