# File Formats

Celstomp uses several file formats for projects, exports, and configuration.

## Project File (.json)

The native Celstomp format for saving work.

### Structure

```json
{
  "version": "1.0",
  "metadata": {
    "created": "2024-01-15T10:30:00Z",
    "modified": "2024-01-16T14:22:00Z",
    "title": "My Animation"
  },
  "canvas": {
    "width": 1920,
    "height": 1080,
    "backgroundColor": "#ffffff"
  },
  "timeline": {
    "frameCount": 120,
    "fps": 24,
    "loop": true
  },
  "layers": [
    {
      "id": "LINE",
      "name": "Line Art",
      "type": "raster",
      "opacity": 1.0,
      "blendMode": "normal",
      "visible": true,
      "cels": {
        "1": {
          "data": "data:image/png;base64,...",
          "exposure": [1, 2, 3]
        }
      }
    }
  ],
  "palette": [
    {
      "color": "#FF0000",
      "name": "Red"
    }
  ],
  "settings": {
    "onionSkinEnabled": true,
    "onionSkinFrames": 1,
    "brushSize": 10
  }
}
```

### Field Reference

**Metadata:**
| Field | Type | Description |
|-------|------|-------------|
| version | string | File format version |
| created | string | ISO 8601 timestamp |
| modified | string | ISO 8601 timestamp |
| title | string | Project name |

**Canvas:**
| Field | Type | Description |
|-------|------|-------------|
| width | number | Canvas width in pixels |
| height | number | Canvas height in pixels |
| backgroundColor | string | Hex color code |

**Timeline:**
| Field | Type | Description |
|-------|------|-------------|
| frameCount | number | Total frames |
| fps | number | Frame rate |
| loop | boolean | Loop playback |

**Layer:**
| Field | Type | Description |
|-------|------|-------------|
| id | string | Layer identifier |
| name | string | Display name |
| type | string | "raster" or "vector" |
| opacity | number | 0.0 to 1.0 |
| blendMode | string | Blend mode name |
| visible | boolean | Layer visibility |
| cels | object | Frame data |

**Cel:**
| Field | Type | Description |
|-------|------|-------------|
| data | string | Base64 PNG data |
| exposure | array | Frame numbers where visible |

### Version History

- **1.0** - Current format
- Future versions will maintain backward compatibility

## Palette File (.json)

Color palette export/import.

### Structure

```json
{
  "version": "1.0",
  "name": "My Palette",
  "colors": [
    {
      "hex": "#FF0000",
      "rgb": [255, 0, 0],
      "name": "Pure Red"
    },
    {
      "hex": "#00FF00",
      "rgb": [0, 255, 0],
      "name": "Pure Green"
    }
  ]
}
```

### Compatibility

Palette files are compatible with:
- Celstomp (native)
- GIMP (via .gpl export)
- Adobe apps (via .ase export)

## Image Sequence

### PNG Format

Lossless export with transparency:

- **Extension:** .png
- **Compression:** Lossless
- **Alpha channel:** Yes
- **Color depth:** 24-bit or 32-bit

**Naming convention:**
```
frame_001.png
frame_002.png
frame_003.png
...
frame_120.png
```

### JPEG Format

Compressed export, smaller files:

- **Extension:** .jpg
- **Compression:** Lossy
- **Alpha channel:** No
- **Quality:** Adjustable (0-100)

### WebP Format

Modern format with good compression:

- **Extension:** .webp
- **Compression:** Lossy or lossless
- **Alpha channel:** Yes
- **Browser support:** Modern browsers

## GIF Export

Animated GIF format:

### Specifications

- **Extension:** .gif
- **Colors:** 2-256 (user selectable)
- **Frame rate:** 1-60 fps
- **Loop:** Forever, once, or N times
- **Transparency:** 1-bit (on/off)

### Limitations

- Maximum 256 colors per frame
- No partial transparency
- Limited to 8-bit color depth
- Dithering for smooth gradients

## MP4 Export

Video format using H.264 codec:

### Specifications

- **Extension:** .mp4
- **Code:c:** H.264 (AVC)
- **Audio:** None
- **Resolution:** User selectable
- **Frame rate:** User selectable

### Quality Settings

| Setting | Bitrate | Use Case |
|---------|---------|----------|
| Low | 2 Mbps | Quick previews |
| Medium | 5 Mbps | General use |
| High | 10 Mbps | Final output |

## ASE Palette (Adobe)

Adobe Swatch Exchange format:

### Compatibility

- Adobe Photoshop
- Adobe Illustrator
- Adobe After Effects
- GIMP (with plugin)

### Structure

Binary format containing:
- Color swatches
- Color names
- Color spaces (RGB, CMYK, LAB)

## GPL Palette (GIMP)

GIMP palette format:

### Structure

```
GIMP Palette
Name: My Palette
Columns: 16
#
255   0   0	Pure Red
  0 255   0	Pure Green
  0   0 255	Pure Blue
```

### Compatibility

- GIMP
- Inkscape
- Krita
- Celstomp (import only)

## Configuration Files

### vite.config.mjs

Vite build configuration:

```javascript
export default defineConfig({
  root: 'celstomp',
  base: './',
  build: {
    outDir: 'dist',
    emptyOutDir: true
  }
});
```

### manifest.webmanifest

PWA manifest:

```json
{
  "name": "Celstomp",
  "short_name": "Celstomp",
  "start_url": "./",
  "display": "standalone",
  "background_color": "#000000",
  "icons": [...]
}
```

### package.json

npm configuration:

```json
{
  "name": "celstomp-v1",
  "version": "1.0.0",
  "scripts": {
    "dev": "vite",
    "build": "vite build"
  },
  "dependencies": {}
}
```

## Import/Export Compatibility

### Importing

| Format | Can Import | Notes |
|--------|------------|-------|
| JSON (project) | Yes | Native format |
| JSON (palette) | Yes | Native format |
| ASE | Yes | Adobe palettes |
| GPL | Yes | GIMP palettes |
| PNG | Yes | As background or frame |
| JPG | Yes | As background only |
| GIF | No | Not supported |

### Exporting

| Format | Can Export | Use Case |
|--------|------------|----------|
| JSON (project) | Yes | Save work |
| JSON (palette) | Yes | Share colors |
| ASE | Yes | Adobe apps |
| GPL | Yes | GIMP |
| PNG | Yes | Frames, sequences |
| JPG | Yes | Compressed frames |
| GIF | Yes | Web, messaging |
| MP4 | Yes | Video, social |
| WebP | Yes | Modern web |

## Working with Files

### Manual Editing

**Warning:** Edit JSON files at your own risk.

Always:
1. Make backups
2. Validate JSON syntax
3. Test in Celstomp
4. Keep original

### Programmatic Access

Read project files with JavaScript:

```javascript
// Load and parse project
fetch('project.json')
  .then(r => r.json())
  .then(project => {
    console.log('Frame count:', project.timeline.frameCount);
    console.log('Layers:', project.layers.length);
  });
```

### Batch Processing

Process exports with tools:

**ImageMagick:**
```bash
# Convert sequence to video
convert frame_*.png output.mp4

# Resize all frames
mogrify -resize 50% frame_*.png
```

**FFmpeg:**
```bash
# Create video from sequence
ffmpeg -i frame_%03d.png -c:v libx264 output.mp4
```

## File Size Considerations

### Project Files

| Canvas Size | Approximate Size |
|-------------|------------------|
| 1920x1080 | 5-20 MB |
| 3840x2160 | 20-80 MB |
| 1280x720 | 2-8 MB |

**Factors affecting size:**
- Canvas resolution
- Number of frames
- Drawing complexity
- Compression

### Export Files

| Format | Size (1 second @ 24fps) |
|--------|-------------------------|
| PNG sequence | 10-50 MB |
| GIF | 500 KB - 5 MB |
| MP4 (high) | 1-3 MB |
| MP4 (low) | 200-500 KB |

## See Also

- [Export Formats](../guides/export-formats.md) - Export options
- [Saving Your Work](../guides/quickstart.md) - Save projects
- [API Overview](./api-overview.md) - Programmatic access
