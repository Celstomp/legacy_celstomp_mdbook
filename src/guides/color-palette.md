# Color & Palette

Understanding the color system helps you create cohesive, professional-looking animations.

## Color Picker

Celstomp offers two color picker modes to suit your workflow.

### Wheel Mode

The default circular color picker:

- **Outer ring** - Select hue (color family)
- **Inner triangle** - Adjust saturation and brightness
- **Current color** - Shows selected color
- **Previous color** - Shows last used color

**How to use:**
1. Click outer ring for base hue
2. Drag in triangle for exact shade
3. Click to confirm

### Triangle Mode

Alternative layout:

- **Triangle** - Hue on one axis, saturation/brightness on others
- **More compact** - Good for smaller screens
- **Same functionality** - Just different layout

Switch modes: **Color menu** > "Picker Mode"

## Working with Color

### Basic Selection

1. Click color picker to open
2. Choose your color
3. Click canvas to close
4. Start drawing

### Recent Colors

The palette shows recently used colors:

- **Last 8 colors** appear below picker
- Click to quickly reselect
- Saves time vs. recreating colors

### Eyedropper

Sample colors from your artwork:

- **Eyedropper tool** - Shortcut `7`
- **Alt+click** - With any tool
- **Samples from** - Current layer or all layers
- **Average option** - Sample averaged area

### Opacity

Control color transparency:

- **0%** - Fully transparent
- **100%** - Fully opaque
- **Slider** - In color picker
- **Brush opacity** - Separate control

**Difference:**
- Color opacity: permanent transparency
- Brush opacity: temporary while drawing

## Color Palette

Save and organize your colors for consistent projects.

### Saving Colors

Add colors to palette:

1. Select color in picker
2. Click "+" in palette panel
3. Or drag color to palette area
4. Color is now saved

### Organizing Palettes

Arrange your colors:

- **Drag to reorder** - Arrange by preference
- **Group by function** - Skin, hair, clothing, etc.
- **Delete** - Right-click > Remove
- **Clear all** - Palette menu > Clear

### Multiple Palettes

Create different palettes:

1. **Palette menu** > "New Palette"
2. Name your palette
3. Add colors
4. Switch between palettes

### Palette Management

**Rename:**
1. Right-click palette name
2. Select "Rename"
3. Enter new name

**Duplicate:**
1. Palette menu > "Duplicate"
2. Creates copy with all colors
3. Modify without losing original

**Delete:**
1. Right-click palette name
2. Select "Delete"
3. Confirm removal

## Import and Export

### Export Palette

Share or backup your colors:

1. **Palette menu** > "Export"
2. Choose format:
   - **JSON** - Full data, reimportable
   - **ASE** - Adobe Swatch Exchange
   - **GPL** - GIMP palette format
3. Save file

### Import Palette

Load existing palettes:

1. **Palette menu** > "Import"
2. Select file (.json, .ase, .gpl)
3. Colors load into new palette
4. Edit as needed

### Preset Palettes

Celstomp includes starter palettes:

- **Basic** - Common colors
- **Skin tones** - Variety of flesh colors
- **Grayscale** - Black to white
- **Rainbow** - Full spectrum

Load: **Palette menu** > "Load Preset"

## Color Theory for Animation

### Color Consistency

Maintain consistent colors:

- **Save character palettes** - One per character
- **Use eyedropper** - Sample from existing art
- **Document colors** - Export palettes with projects
- **Limit palette** - Fewer colors = more cohesive

### Color Organization

Organize palettes logically:

```
Character Palette:
- Skin tones (3-5 colors)
- Hair colors (2-3 colors)
- Clothing (3-5 colors)
- Accessories (2-3 colors)
- Eyes (1-2 colors)
```

### Harmony

Create pleasing color schemes:

- **Complementary** - Opposite colors (blue/orange)
- **Analogous** - Adjacent colors (blue/green/yellow)
- **Triadic** - Three evenly spaced colors
- **Monochromatic** - One hue, varying brightness

### Contrast

Ensure readability:

- **Value contrast** - Light vs. dark
- **Hue contrast** - Different colors
- **Saturation contrast** - Bright vs. muted
- **Test** - Squint to check values

## Layer Color Interaction

### Blend Modes

Layers affect color appearance:

- **Normal** - Standard overlay
- **Multiply** - Darkens (shadows)
- **Screen** - Lightens (highlights)
- **Overlay** - Combined effect

### Shadow Colors

Best practices for shadows:

- **Use SHADE layer** - On multiply blend
- **Desaturate** - Shadows are less colorful
- **Cool shadows** - Blue/purple undertones
- **Warm lights** - Orange/yellow highlights

### Color Testing

Test colors before committing:

1. Create test layer
2. Paint color samples
3. Compare to reference
4. Adjust in picker
5. Apply when satisfied

## Advanced Color Features

### Color Replacement

Replace one color with another:

1. **Edit > Color Replacement**
2. Select color to replace
3. Choose new color
4. Set tolerance
5. Apply to current layer or all

### Color Balance

Adjust overall colors:

1. **Edit > Color Balance**
2. Adjust sliders:
   - Cyan/Red
   - Magenta/Green
   - Yellow/Blue
3. Preview changes
4. Apply to selection or layer

### Hue/Saturation

Fine-tune colors:

1. **Edit > Hue/Saturation**
2. Adjust:
   - Hue - Shift color family
   - Saturation - Color intensity
   - Lightness - Brightness
3. Apply selectively

## Troubleshooting

**Colors look different:**
- Check layer blend mode
- Verify layer opacity
- Check if onion skin is tinting
- Monitor calibration varies

**Can't pick exact color:**
- Zoom in for precision
- Use triangle picker mode
- Check if sampling from all layers
- Try averaged sampling

**Palette colors lost:**
- Did you clear the palette?
- Check if you switched palettes
- Reload from backup if exported
- Palettes save with project

**Export/import not working:**
- Check file format compatibility
- Verify file isn't corrupted
- Try different format (JSON is safest)
- Check file permissions

**Colors print differently:**
- Screens use RGB, prints use CMYK
- Convert palette to CMYK first
- Expect some color shift
- Test print before final

## Best Practices

### Project Setup

1. Create palette before starting
2. Limit to 16-32 colors max
3. Organize by function
4. Export palette with project

### Character Design

1. Define base colors
2. Add shadow variants (darker)
3. Add highlight variants (lighter)
4. Test on background color

### Consistency

- Use palette for all colors
- Eyedropper from existing work
- Document unusual colors
- Review palette periodically

## Tips and Tricks

### Quick Color Access

- Number keys (1-8) select recent colors
- Middle-click color in palette to select
- Double-click palette color to edit

### Color Variations

Create variations easily:

1. Select base color
2. Adjust saturation slightly
3. Save as new swatch
4. Repeat for range

### Palette Inspiration

Find palettes online:

- **Adobe Color** - color.adobe.com
- **Coolors** - coolors.co
- **Color Hunt** - colorhunt.co
- Import to Celstomp

### Dark Theme Colors

For dark interfaces:

- Use lighter color values
- Increase saturation slightly
- Test on actual dark background
- Ensure sufficient contrast

## See Also

- [Drawing Tools](./drawing-tools.md) - Applying color
- [Layers System](../concepts/layers.md) - Color and layers
- [Animation Workflow](./animation-workflow.md) - Color in motion
