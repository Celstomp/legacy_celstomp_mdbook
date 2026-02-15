# Animation Workflow

Professional animation follows a structured process. Understanding this workflow helps you work more efficiently and produce better results.

## The Animation Pipeline

Traditional animation follows these stages:

1. **Planning** - Storyboards, animatics
2. **Blocking** - Rough key poses
3. **Inbetweening** - Filling gaps
4. **Cleanup** - Clean line art
5. **Color** - Adding color
6. **Compositing** - Final assembly

Celstomp supports all these stages.

## Phase 1: Planning

Before drawing your first frame:

### Thumbnails

Sketch tiny versions:

- **Size:** 2-3 inches wide
- **Focus:** Composition and action
- **Quantity:** 4-6 variations
- **Time:** 5-10 minutes each

These rough sketches plan the motion without detail.

### Animatic

Timing test with rough drawings:

1. Draw key poses (every 8-12 frames)
2. Set timing by holding frames
3. Test playback
4. Adjust until motion feels right

This catches timing issues early.

### Exposure Sheet

Plan your animation:

| Frame | LINE | COLOR | Notes |
|-------|------|-------|-------|
| 1 | Key 1 | | Hold for 2 frames |
| 3 | Inbetween | | |
| 5 | Key 2 | | |
| 7 | | | Camera move |

While Celstomp doesn't have exposure sheets, you can use frame markers.

## Phase 2: Blocking (Keyframes)

Establish the main poses.

### What Are Keyframes?

Keyframes are the extreme poses:

- **Starting position** - Where action begins
- **Ending position** - Where action ends
- **Extreme poses** - Furthest points of motion
- **Contact poses** - When things touch

### Setting Keyframes

In Celstomp:

1. **Frame 1** - Draw starting pose
2. **Jump to frame 12** - Draw ending pose
3. **Add middle key at frame 6** - Extreme pose
4. **Test playback** - See rough motion

### Spacing Keys

Common keyframe spacing:

- **Fast action** - Every 4-6 frames
- **Medium action** - Every 8-12 frames
- **Slow action** - Every 16-24 frames

### Rough vs. Clean

At this stage:

- **Draw rough** - Focus on pose, not line quality
- **Use LINE layer** - Easy to clean up later
- **Check volume** - Keep character consistent
- **Use onion skin** - See previous/next keys

## Phase 3: Inbetweening

Fill in the frames between keys.

### What Are Inbetweens?

Frames that connect keyframes:

- **Slow in** - Gradual acceleration
- **Slow out** - Gradual deceleration
- **Even spacing** - Constant speed
- **Favors** - Closer to one key than other

### Inbetween Types

**Straight ahead:**
- Draw frame 1, 2, 3, 4, 5...
- Good for: continuous motion (water, fire)
- Hard to: hit specific timing

**Pose to pose:**
- Draw keys first, then fill in
- Good for: character animation
- Easier to: control timing

**Combination:**
- Pose to pose for structure
- Straight ahead for details
- Best of both worlds

### Spacing Charts

Plan inbetween placement:

```
Key 1 (frame 1)
  |
  | <- Half (frame 7)
  |   |
  |   | <- Quarter (frame 4)
  |   |
Key 2 (frame 13)
```

Celstomp shows spacing visually in onion skin.

### Inbetweening Technique

1. **Enable onion skin** - See both keys
2. **Position playhead** - Between keys
3. **Estimate middle** - Halfway between poses
4. **Draw inbetween** - Connect the motion
5. **Check volume** - Match keys
6. **Test playback** - See smooth motion

## Phase 4: Cleanup

Refine rough drawings into clean line art.

### Cleanup Process

1. **Lower opacity** of rough layer to 30%
2. **Create new LINE layer** above
3. **Trace with clean lines** - Confident strokes
4. **Maintain line weight** - Consistent thickness
5. **Add details** - Final refinements
6. **Delete rough** - When clean is done

### Line Quality

Good cleanup lines are:

- **Confident** - Single strokes, not sketchy
- **Consistent** - Similar lines look similar
- **Purposeful** - Every line has a reason
- **Fluid** - Natural curves, not rigid

### Tools for Cleanup

- **Brush** - 3-5px size
- **Eraser** - For corrections
- **Steady hand** - Or tablet
- **Zoom** - 200% for details

## Phase 5: Coloring

Add color to your clean line art.

### Base Colors

1. **Switch to COLOR layer**
2. **Use Fill Brush** for large areas
3. **Work flat** - No shading yet
4. **Stay in lines** - Clean edges
5. **Use palette** - Consistent colors

### Shadow Pass

1. **Switch to SHADE layer**
2. **Determine light source** - Where is light coming from?
3. **Add shadows** - Opposite light source
4. **Use multiply blend** - Natural shadows
5. **Build gradually** - Multiple light passes

### Highlight Pass

1. **Add COLOR layer** (or use existing)
2. **Lighten base colors** - Where light hits
3. **Keep subtle** - Don't overdo
4. **Consider material** - Different surfaces reflect differently

## Phase 6: Effects and Polish

Final touches:

### Motion Blur

For fast motion:

1. **Duplicate layer** - Of moving element
2. **Offset slightly** - In direction of motion
3. **Lower opacity** - 30-50%
4. **Merge** - When satisfied

### Impact Frames

Emphasize impacts:

1. **Add frame** - On contact
2. **Exaggerate pose** - Push it further
3. **Add effects** - Speed lines, impact stars
4. **Hold 1-2 frames** - Just for impact

### Camera Moves

Simulate camera:

- **Zoom** - Scale canvas gradually
- **Pan** - Shift canvas position
- **Rotate** - Rotate view slightly
- **Export** - Process handles motion

## Timing and Spacing

### Frame Rates

Common frame rates:

- **12 fps** - Classic animation (every 2nd frame at 24fps)
- **24 fps** - Film standard
- **30 fps** - Video standard
- **60 fps** - Smooth motion

In Celstomp: Set in timeline settings.

### Timing Principles

**Slow in and slow out:**
- Start slow, accelerate, end slow
- More natural than constant speed
- Achieved with spacing

**Overlapping action:**
- Different parts move at different times
- Hair moves after head stops
- Creates natural feel

**Follow-through:**
- Objects continue after force stops
- Momentum carries motion
- Settles into final pose

**Anticipation:**
- Move opposite direction first
- Prepares audience for action
- Makes action more readable

## Workflow Tips

### Organization

- **Save versions** - Filename_v01, v02, etc.
- **Use markers** - Label important frames
- **Work in passes** - Complete each phase
- **Test frequently** - Check playback often

### Efficiency

- **Reuse drawings** - Hold cels when possible
- **Cycle animations** - Loop repeating actions
- **Work rough first** - Details come later
- **Use shortcuts** - Speed up workflow

### Quality Control

- **Check arcs** - Motion should follow curves
- **Verify volume** - Keep character consistent
- **Test timing** - Does it feel right?
- **Get feedback** - Fresh eyes catch issues

## Common Mistakes

### Timing Issues

- **Too even** - All frames same spacing
- **Too few keys** - Motion unclear
- **Too many keys** - Over-complicated

**Fix:** Plan timing with animatic first.

### Spacing Issues

- **Linear motion** - Robot-like movement
- **Uneven volume** - Character shrinks/grows
- **Jitter** - Inconsistent spacing

**Fix:** Use onion skin, check arcs.

### Technical Issues

- **Wrong layer** - Drew on wrong layer
- **Forgot onion skin** - Can't see context
- **Lost work** - Didn't save

**Fix:** Check before drawing, save often.

## See Also

- [Timeline & Frames](../concepts/timeline.md) - Frame management
- [Onion Skinning](../concepts/onion-skinning.md) - See through time
- [Layers System](../concepts/layers.md) - Organizing artwork
