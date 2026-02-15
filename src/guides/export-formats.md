# Export Formats

Celstomp offers multiple export options depending on your needs.

## Export Overview

Choose the right format for your destination:

| Format | Best For | Quality | File Size |
|--------|----------|---------|-----------|
| MP4 | Social media, video | High | Medium |
| GIF | Web, messaging | Medium | Small |
| Image Sequence | Editing, archiving | Lossless | Large |
| JSON | Backup, editing | Exact | Small |

## MP4 Export

Video format for sharing and playback.

### When to Use MP4

- Uploading to YouTube, TikTok, Instagram
- Embedding in presentations
- Playing on devices
- Archiving final work

### MP4 Settings

**Resolution:**
- Match canvas size (recommended)
- Or choose preset: 1080p, 720p, 480p
- Higher = better quality, larger file

**Frame Rate:**
- Match timeline (recommended)
- Common: 24fps, 30fps, 60fps
- Higher = smoother, larger file

**Quality:**
- Low - Smaller file, visible compression
- Medium - Balance of size/quality
- High - Best quality, larger file
- Custom - Adjust bitrate manually

### Export Process

1. **File > Export > MP4**
2. **Choose settings:**
   - Resolution
   - Frame rate
   - Quality
3. **Select range:**
   - All frames
   - In/Out points
   - Custom range
4. **Click Export**
5. **Wait for processing**
6. **Download file**

### Tips for MP4

- Match frame rate to destination (24fps for film, 30fps for video)
- Test different quality settings
- Use higher quality for final exports
- Background color fills transparent areas

## GIF Export

Perfect for web and simple animations.

### When to Use GIF

- Discord, Slack reactions
- Website graphics
- Simple loops
- Small file size needed

### GIF Settings

**Colors:**
- 8-256 colors
- Fewer colors = smaller file
- Dithering options for smooth gradients

**Frame Rate:**
- Usually 10-15fps for GIFs
- Higher = smoother but larger
- Can skip frames to reduce size

**Loop:**
- Forever - Repeats continuously
- Once - Plays one time
- Custom - Specific number

**Size:**
- Original size
- Or resize (50%, 75%, custom)
- Smaller = faster loading

### Export Process

1. **File > Export > GIF**
2. **Configure:**
   - Color palette
   - Frame rate
   - Loop setting
   - Size
3. **Preview** - See how it looks
4. **Adjust settings** - Optimize size
5. **Export**
6. **Download**

### Optimizing GIFs

Reduce file size:

- **Fewer colors** - 32 or 64 is often enough
- **Smaller dimensions** - Resize if possible
- **Lower frame rate** - 10fps is often fine
- **Reduce frames** - Shorter animations
- **Limited palette** - Fewer colors used

### GIF Limitations

- **256 colors max** - Limited palette
- **No transparency gradations** - All or nothing
- **Large file sizes** - For long/hi-res animations
- **No audio** - Silent only

## Image Sequence Export

Individual frames for advanced editing.

### When to Use Image Sequence

- Importing to After Effects, Premiere
- Post-processing in Photoshop
- Archiving at highest quality
- Frame-by-frame editing

### Sequence Settings

**Format:**
- **PNG** - Lossless, transparency, larger
- **JPEG** - Smaller, lossy, no transparency
- **WebP** - Modern, good compression

**Naming:**
- `frame_001.png`, `frame_002.png`, etc.
- Custom prefix
- Leading zeros (001 vs 1)
- Start number

**Range:**
- All frames
- In/Out points
- Every Nth frame (for tests)

### Export Process

1. **File > Export > Image Sequence**
2. **Choose format** - PNG recommended
3. **Set naming** - Prefix and numbering
4. **Select range**
5. **Choose folder** - Where to save
6. **Export**
7. **Files save** - One per frame

### Working with Sequences

**Import to video editor:**
1. Import first frame
2. Enable "image sequence" option
3. Software treats as video clip

**Batch process:**
- Use Photoshop actions
- ImageMagick commands
- Python scripts
- Automation tools

## JSON Project Export

Save your work for editing later.

### When to Use JSON

- Backing up projects
- Transferring between computers
- Collaborative work
- Long-term storage

### What's Included

JSON files contain:

- All layer data
- Frame information
- Color palettes
- Project settings
- Canvas configuration

### Export Process

1. **File > Save Project** or `Ctrl+S`
2. **Choose location**
3. **Name file** (e.g., `my_animation.json`)
4. **Save**

### Import Process

1. **File > Load Project**
2. **Choose JSON file**
3. **Project loads** with all data intact

### JSON Structure

```json
{
  "version": "1.0",
  "canvas": {
    "width": 1920,
    "height": 1080
  },
  "layers": [...],
  "frames": [...],
  "palette": [...]
}
```

## Export Best Practices

### Before Exporting

1. **Review animation** - Play it back
2. **Check frame range** - In/Out points set?
3. **Verify layers** - All visible that should be
4. **Test settings** - Do a short test first
5. **Save project** - Before exporting

### Quality vs. Size

Balance considerations:

- **Draft/Preview** - Low quality, fast export
- **Review** - Medium quality, reasonable size
- **Final** - High quality, best settings
- **Archive** - Lossless, maximum quality

### Destinations

**YouTube:**
- MP4, 1080p or 4K
- 24fps or 30fps
- High quality

**Instagram/TikTok:**
- MP4, 1080x1920 (vertical)
- 30fps
- High quality

**Discord:**
- GIF for small loops (<8MB)
- MP4 for longer videos
- Optimize for size

**Portfolio:**
- High quality MP4
- Multiple sizes (1080p, 4K)
- Lossless backup

## Troubleshooting

**Export fails:**
- Check browser permissions
- Try smaller resolution
- Close other browser tabs
- Check available disk space

**File too large:**
- Lower resolution
- Reduce frame rate
- Lower quality settings
- Shorter duration

**Quality looks bad:**
- Increase quality setting
- Use higher resolution
- Check source quality
- Try different format

**Colors look wrong:**
- Check color profile
- GIFs limited to 256 colors
- Try PNG for accuracy
- Verify layer visibility

**Missing frames:**
- Check In/Out points
- Verify all layers visible
- Check frame range selection
- Ensure cels are exposed

## See Also

- [Saving Your Work](./quickstart.md) - Project files
- [Animation Workflow](./animation-workflow.md) - Preparing for export
- [System Requirements](./requirements.md) - Performance considerations
