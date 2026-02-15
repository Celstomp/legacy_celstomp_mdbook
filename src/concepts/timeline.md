# Timeline & Frames

The timeline is where you control timing and organize your animation sequence.

## Timeline Overview

### The Interface

The timeline sits at the bottom of the screen and shows:

- **Frame numbers** across the top (1, 2, 3...)
- **Layer tracks** showing which cels are exposed
- **Playhead** indicating current frame (red line)
- **Frame controls** for playback and editing

### Key Concepts

- **Frame** - A single unit of time (like a moment in a film)
- **Cel** - The drawing exposed on that frame
- **Exposure** - How long a cel remains visible
- **Playhead** - Shows which frame you're currently viewing

## Working with Frames

### Navigation

| Action | Shortcut | Button |
|--------|----------|--------|
| Next frame | `E` or `→` | Right arrow |
| Previous frame | `Q` or `←` | Left arrow |
| First frame | `Home` | | |
| Last frame | `End` | | |
| Jump to frame | Click timeline | | |

### Adding Frames

To add new frames:

1. **Press `E`** - Adds frame after current
2. **Right-click timeline** > "Insert frame"
3. **Timeline menu** > "Add Frame"

New frames start empty (no cels exposed).

### Deleting Frames

To remove frames:

1. **Select frame(s)** - Click to select one, Shift+click for range
2. **Press `Delete`** or right-click > "Delete Frame"
3. **Confirm** - Option to shift remaining frames or leave gap

### Duplicating Frames

Copy a frame:

1. **Select the frame**
2. **Right-click** > "Duplicate Frame"
3. **Or** `Ctrl+D` (duplicate) or `Ctrl+C`, `Ctrl+V` (copy/paste)

This copies all exposed cels on that frame.

## Managing Cels

### Exposing Cels

A cel must be "exposed" on a frame to be visible:

1. **Select the frame** in timeline
2. **Select the layer** in layers panel
3. **Draw** - Automatically creates and exposes a cel
4. **Or** right-click frame > "Expose Cel" > Choose existing cel

### Holding a Drawing

To make a cel visible across multiple frames:

1. **Select the cel** on the first frame
2. **Drag the right edge** to extend exposure
3. **Or** right-click > "Extend Exposure" > Enter frame count

### Moving Cels

Drag cels in the timeline:

- **Drag cel** - Move to different frame
- **Shift+drag** - Copy cel to new location
- **Alt+drag** - Move cel to different layer

### Deleting Cels

To remove a cel from a frame:

- **Right-click cel** > "Delete Cel" (removes exposure only)
- **Right-click cel** > "Delete Drawing" (removes cel entirely)

## Timeline Controls

### Playback

| Action | Shortcut | Control |
|--------|----------|---------|
| Play/Stop | `Space` | Play button |
| Loop | `L` | Loop toggle |
| Ping-pong | `P` | Ping-pong toggle |

### Loop Modes

- **Play once** - Runs from start to end, stops
- **Loop** - Repeats continuously
- **Ping-pong** - Plays forward, then backward, repeats

### Frame Rate

Adjust playback speed:

1. **Timeline menu** > "Frame Rate"
2. Choose from presets:
   - 12 fps (classic animation)
   - 24 fps (film standard)
   - 30 fps (video standard)
   - 60 fps (smooth motion)
3. **Or** enter custom rate

**Note:** Frame rate affects playback only, not individual frames.

## Advanced Timeline Features

### Multi-Select

Select multiple frames for batch operations:

- **Shift+click** - Select range
- **Ctrl+click** - Add/remove from selection
- **Click and drag** - Select range

### Frame Ranges

Work with specific sections:

- **Set In Point** (`I`) - Mark start of work area
- **Set Out Point** (`O`) - Mark end of work area
- Playback respects In/Out points
- Export uses In/Out points as default range

### Markers

Add markers to the timeline:

1. **Press `M`** at playhead position
2. **Name the marker** (optional)
3. **Click marker** to jump to that frame
4. **Right-click marker** to delete

Use markers for:
- Scene changes
- Key poses
- Timing notes
- Revision markers

### Waveform Display

If importing audio:

- Audio appears as waveform in timeline
- Scrub playhead to hear audio
- Lock audio to prevent accidental editing

## Timeline Views

### Zoom

Zoom the timeline horizontally:

- **Ctrl+scroll** (on timeline) - Zoom in/out
- **Fit button** - Show all frames
- **Zoom to selection** - Focus on selected range

### Compact Mode

Toggle compact timeline:

- **Timeline menu** > "Compact View"
- Shows more frames in less space
- Good for long animations

### Layer Colors

Each layer track has a color:

- LINE - Blue
- SHADE - Purple
- COLOR - Green
- FILL - Yellow
- PAPER - Orange

Colors help distinguish layers in the timeline.

## Best Practices

### Organizing Long Animations

For animations over 100 frames:

- Use markers for scene breaks
- Work in sections (export chunks)
- Use compact view
- Name your cels descriptively

### Timing Techniques

- **Ones** (1 frame per drawing) - Smooth, 24fps
- **Twos** (2 frames per drawing) - Standard, 12fps
- **Threes** (3 frames per drawing) - Slow, 8fps

Mix these within the same animation for emphasis and timing.

### Testing Playback

- Test frequently (every few frames)
- Watch at full speed
- Check both directions (ping-pong)
- Test on target frame rate

## Troubleshooting

**Frames not advancing:**
- Check if playback is stopped
- Verify playhead isn't locked
- Make sure no modal is open

**Missing cels:**
- Check layer visibility
- Verify cel is exposed on current frame
- Check if cel is on wrong layer

**Wrong playback speed:**
- Check frame rate setting
- Browser might be throttling
- Close other tabs for better performance

## See Also

- [Onion Skinning](./onion-skinning.md) - See frames in context
- [Animation Workflow](../guides/animation-workflow.md) - Timing techniques
- [Layers System](./layers.md) - How cels relate to layers
