# Core Concepts Overview

Understanding these fundamental concepts helps you work faster and more effectively in Celstomp.

## How Celstomp Thinks About Animation

Celstomp follows traditional animation workflows. If you've ever worked with physical animation cels or used software like TVPaint or Krita, these concepts will feel familiar.

### Frames vs. Cels

In Celstomp:

- **Frame** - A single point in time in your animation timeline
- **Cel** - The actual artwork drawn on that frame

Think of it like traditional animation: the frame is the number on your exposure sheet, and the cel is the transparent plastic sheet with the drawing on it.

You can have multiple cels on the same frame (like holding a drawing for several frames), or extend a cel across multiple frames.

### The Layer Stack

Animation in Celstomp uses a layer stack:

```
Top → LINE layer (outlines)
      SHADE layer (shadows)
      COLOR layer (flat colors)
      FILL layer (filled areas)
Bottom → PAPER layer (background)
```

Each layer can contain different parts of your artwork. This separation makes it easier to edit specific elements without affecting everything else.

### Onion Skinning

Onion skinning shows frames before and after your current position as semi-transparent overlays. It works like holding paper up to a light table to see the drawings on the sheets below.

In Celstomp:
- **Green** = previous frames
- **Red** = next frames
- Opacity adjusts how strongly they appear

### Keyframes and Inbetweens

Traditional animation uses:

- **Keyframes** - The main poses (extreme positions)
- **Inbetweens** - The drawings between keyframes

Celstomp doesn't enforce this distinction, but understanding it helps your workflow:

1. Draw keyframes first (every 4-8 frames)
2. Fill in the inbetweens
3. Adjust timing by adding or removing frames

### Playback and Timing

Celstomp plays your animation at your chosen frame rate:

- **12 fps** - Classic animation timing
- **24 fps** - Standard film rate
- **30 fps** - Common for video
- **60 fps** - Smooth motion

Change frame rate in the timeline settings.

## Project Organization

### The Timeline Grid

The timeline displays frames horizontally. Each vertical column represents one frame. The timeline shows:

- Frame numbers
- Which cels are exposed on each frame
- Current playhead position
- Selected frames

### Scenes and Shots

While Celstomp doesn't have built-in scene management, you can organize work by:

1. Creating separate project files for each scene
2. Using naming conventions: `scene01_shot01.json`
3. Keeping related files in the same folder

### File Structure

Celstomp saves everything in a single `.json` file containing:

- All layer data
- Frame information
- Color palettes
- Project settings

This makes projects portable - just share the JSON file.

## Best Practices

### Planning Your Animation

Before drawing:

1. **Sketch thumbnails** - Plan the motion
2. **Set your frame rate** - 12fps is good for most work
3. **Create a layer strategy** - Which layers for what?
4. **Block in keyframes** - Rough poses first
5. **Refine and inbetween** - Add detail progressively

### Efficient Workflow

- Use keyboard shortcuts (press `?` to see them)
- Enable onion skin when animating
- Save versions regularly
- Test playback frequently
- Work rough first, detail later

### Color Strategy

- Start with the PAPER layer for background
- Use LINE layer for rough sketches
- Add COLOR layer for flat fills
- Use SHADE layer for depth
- Keep palette organized and consistent

## Next Steps

Deep dive into specific concepts:

- [Canvas & Viewport](./canvas.md) - Navigate your workspace
- [Timeline & Frames](./timeline.md) - Master timing
- [Layers System](./layers.md) - Organize your artwork
- [Onion Skinning](./onion-skinning.md) - See through time
