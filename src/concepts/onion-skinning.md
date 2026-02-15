# Onion Skinning

Onion skinning lets you see multiple frames at once, making it easier to create smooth animation. It's like holding paper up to a light table to see the drawings on the sheets underneath.

## What Is Onion Skinning?

In traditional animation, animators use a light table to see through multiple sheets of paper. This helps them:

- Keep track of where the animation is coming from
- See where it's going
- Maintain consistent volume and proportions
- Create smooth inbetweens

Celstomp recreates this digitally with onion skinning.

## How It Works

When you enable onion skinning, you see:

- **Your current frame** - Full opacity, normal colors
- **Previous frames** - Green tint, semi-transparent
- **Next frames** - Red tint, semi-transparent

The colors help you distinguish which direction in time each frame represents.

## Enabling Onion Skin

### Quick Toggle

Press **`O`** to turn onion skinning on or off.

### From the Menu

**View > Onion Skin** to toggle.

### Settings

Customize onion skin behavior:

**View > Onion Skin Settings**

## Onion Skin Settings

### Number of Frames

Choose how many frames to show:

- **Previous:** 1-5 frames (default: 1)
- **Next:** 1-5 frames (default: 1)

More frames = more context but more visual clutter.

### Opacity

Adjust how strongly onion frames appear:

- **Previous opacity:** 10-50% (default: 30%)
- **Next opacity:** 10-50% (default: 30%)

Higher opacity = easier to see but might distract from current frame.

### Colors

Customize the tint colors:

- **Previous color:** Default green (#00FF00)
- **Next color:** Default red (#FF0000)

Change these if you have color vision preferences or if the defaults clash with your artwork.

### Fade Mode

Choose how opacity decreases:

- **Linear:** Each frame back has equal opacity drop
- **Exponential:** Closer frames are stronger, distant frames fade quickly
- **Constant:** All onion frames have same opacity

## Using Onion Skin Effectively

### For Keyframing

When creating key poses:

1. Enable onion skin
2. See previous keyframe
3. Draw extreme pose with volume reference
4. Check both previous and next to ensure flow

### For Inbetweening

When filling in between keyframes:

1. Position between two keyframes
2. Enable onion skin (both directions)
3. See where you're coming from (green)
4. See where you're going (red)
5. Draw exactly in the middle

### For Arc Checking

To check motion arcs:

1. Enable 3-5 previous frames
2. Use exponential fade
3. The trail shows the motion path
4. Adjust if movement is too linear

## Advanced Techniques

### Onion Skin Range

Work with specific frame ranges:

- **Single frame:** Just previous/next (default)
- **Motion trail:** 3-5 frames for arc checking
- **Full context:** All frames in scene

### Solo Onion Direction

Sometimes you only need one direction:

- **Previous only:** Good for following through
- **Next only:** Good for anticipating
- **Both:** Good for inbetweens

Toggle individually in settings.

### Color Coding

Different colors for different purposes:

- **Green/Red:** Standard, good contrast
- **Blue/Orange:** Warmer alternative
- **Same color:** When color doesn't matter
- **Inverted:** For dark artwork on light backgrounds

## Best Practices

### When to Use Onion Skin

**Always use for:**
- Inbetweening (drawing between poses)
- First pass animation
- Checking arcs and spacing
- Maintaining volume

**Sometimes use for:**
- Cleanup (can be distracting)
- Final details (turn off for precision)
- Color work (can tint perception)

### When to Turn It Off

- Precise line work (can obscure)
- Color picking (tint affects perception)
- Final review (see clean animation)
- Performance issues (saves GPU)

### Managing Visual Clutter

If onion skin feels overwhelming:

1. Reduce number of frames shown
2. Lower opacity
3. Use exponential fade
4. Turn off when not needed

## Pro Tips

### The Blink Test

Flip between onion on/off:

1. Draw with onion skin on
2. Press `O` to toggle off
3. Check if drawing works without reference
4. Toggle back on if needed

This prevents over-dependence on onion frames.

### Frame Spacing Check

Use onion skin to check spacing:

1. Enable multiple previous frames
2. Look at the gaps between poses
3. Even spacing = even speed
4. Large gaps = fast movement
5. Small gaps = slow movement

### Volume Consistency

Keep character volume consistent:

1. Compare current frame to onion frames
2. Check proportions match
3. Ensure no accidental shrinking/growing
4. Adjust as needed

## Troubleshooting

**Onion frames not showing:**
- Check if onion skin is enabled (`O`)
- Verify there are frames before/after current
- Check opacity settings aren't at 0%
- Ensure onion color isn't same as background

**Onion too distracting:**
- Lower opacity
- Reduce number of frames
- Change colors to be less intense
- Use exponential fade

**Performance issues:**
- Onion skin uses more GPU
- Reduce number of onion frames
- Lower resolution while animating
- Turn off when not needed

**Colors look wrong:**
- Onion tint affects color perception
- Turn off onion skin for color work
- Adjust onion colors in settings

## Related Features

### Light Table Mode

**View > Light Table**

Similar to onion skin but shows all layers at 50% opacity. Good for:
- Seeing overall composition
- Checking layer alignment
- Working on complex multi-layer shots

### Ghosting

Some workflows use onion skin differently:

- **Traditional:** See before/after frames
- **Pose to pose:** See only keyframes
- **Straight ahead:** See only previous frames

Adjust settings to match your workflow.

## Exercises

### Exercise 1: Bouncing Ball

1. Draw ball at top (frame 1)
2. Draw ball at bottom (frame 5)
3. Enable onion skin
4. Draw inbetweens at frames 2, 3, 4
5. Check spacing and arcs

### Exercise 2: Follow-Through

1. Draw a tail wag at frame 1
2. Draw at frame 5
3. Use onion skin to draw overlapping action
4. Notice how parts move at different times

## See Also

- [Animation Workflow](../guides/animation-workflow.md) - Timing and spacing
- [Timeline & Frames](./timeline.md) - Frame management
- [Drawing Tools](../guides/drawing-tools.md) - Tools for drawing
