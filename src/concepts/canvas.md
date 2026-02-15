# Canvas & Viewport

The canvas is where you create your artwork. Understanding how to navigate and configure it speeds up your workflow.

## Canvas Basics

### Default Setup

When you open Celstomp:

- **Aspect ratio:** 16:9 (widescreen)
- **Resolution:** Depends on your browser window
- **Background:** Transparent checkered pattern
- **Center point:** Marks the middle of your composition

### The Checkered Background

The checkered pattern represents transparency. When you export:

- **MP4/GIF** - Checkers become the background color (usually white or black)
- **Image sequence** - Checkers become transparent if using PNG

To change the background, use the PAPER layer.

## Navigation

### Zoom Controls

| Method | Action |
|--------|--------|
| Scroll wheel | Zoom in/out |
| `Ctrl +` / `Ctrl -` | Zoom in/out |
| Fit button | Zoom to fit window |
| 100% button | Actual size |

### Panning

| Method | Action |
|--------|--------|
| Middle-click drag | Pan around canvas |
| Space + drag | Pan around canvas |
| Scrollbars | Pan horizontally/vertically |

### Center View

Press `Home` or click the center button to return to the canvas center at 100% zoom.

## Canvas Settings

### Aspect Ratio Presets

Celstomp offers common aspect ratios:

| Ratio | Use Case |
|-------|----------|
| 16:9 | YouTube, modern video |
| 4:3 | Classic TV, presentations |
| 1:1 | Instagram, social media |
| 21:9 | Cinematic widescreen |
| 9:16 | TikTok, vertical video |

To change aspect ratio: **View > Aspect Ratio**

**Note:** Changing aspect ratio crops or adds to your canvas. Existing artwork adjusts position.

### Custom Dimensions

For specific pixel dimensions:

1. Go to **View > Canvas Size**
2. Enter width and height in pixels
3. Choose anchor point (which corner stays fixed)
4. Click Apply

### Flip Canvas

Flip horizontally to check your drawing:

- **View > Flip Horizontal** or press `H`
- This is a view-only flip (doesn't affect export)
- Helps spot proportion issues

## Working with the Viewport

### Safe Zones

Enable safe zones to keep important content visible:

- **Action safe:** 5% inset (keep all important motion here)
- **Title safe:** 10% inset (keep text and titles here)

**View > Safe Zones** to toggle.

### Grid

Turn on grid for precise alignment:

- **View > Grid** to toggle
- **View > Grid Size** to adjust spacing
- Grid doesn't appear in export

### Rulers

Show rulers along canvas edges:

- **View > Rulers** to toggle
- Click and drag from rulers to create guides
- Right-click ruler to change units (pixels, inches, centimeters)

## Drawing Area

### Canvas vs. Window

- **Canvas:** The actual animation resolution
- **Window:** Your browser viewport

The canvas can be larger or smaller than your window. Use zoom to see the whole canvas or focus on details.

### Full Screen Mode

Press `F11` (browser full screen) for maximum drawing space.

### Multi-Monitor Setup

For dual monitors:

1. Open Celstomp on your primary display
2. Use the secondary display for reference images
3. Or detach the timeline to its own window (if browser supports it)

## Performance Considerations

### Large Canvases

Very large canvases (4K+) can slow down:

- **Solution 1:** Work at a smaller resolution
- **Solution 2:** Close other browser tabs
- **Solution 3:** Use Chrome or Firefox (better canvas performance)

### Memory Usage

Canvas size affects memory:

- 1920x1080 canvas = ~8MB per layer
- 3840x2160 canvas = ~32MB per layer

For complex projects with many layers, stay under 2K resolution.

## Tips and Tricks

### Quick Zoom to Selection

If you have a selection active, press `Z` to zoom to fit the selection.

### Reset View

Lost your canvas? Press `Ctrl+0` (zero) to reset zoom and center.

### Pixel Perfect

At 100% zoom (1:1), one screen pixel equals one canvas pixel. This is useful for pixel art.

### Reference Images

Import reference images to the PAPER layer:

1. Create or select PAPER layer
2. Use File > Import > Image
3. Position and scale as needed
4. Lower opacity to draw over it

## Troubleshooting

**Canvas appears blank:**
- Check if you're on the right layer
- Verify layer opacity isn't zero
- Make sure no selection is hiding content

**Zoom not working:**
- Check browser zoom (Ctrl+0 to reset)
- Some touchpads interfere - try using keyboard shortcuts

**Canvas looks blurry:**
- You're zoomed in beyond 100%
- Check browser zoom level
- Try a different browser

## See Also

- [Drawing Tools](../guides/drawing-tools.md) - Tools for the canvas
- [Layers System](./layers.md) - How layers interact
- [Timeline & Frames](./timeline.md) - Frame management
