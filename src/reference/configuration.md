# Configuration

Celstomp can be configured through settings, configuration files, and URL parameters.

## In-App Settings

### Accessing Settings

**Menu:** Edit > Preferences

Or press `Ctrl + ,` (comma)

### Canvas Settings

**Default Size:**
- Width: 1920 pixels
- Height: 1080 pixels
- Aspect ratio: 16:9

**Change default:**
```javascript
// In console or custom script
window.celstompConfig.set('defaultCanvasWidth', 1280);
window.celstompConfig.set('defaultCanvasHeight', 720);
```

### Timeline Settings

**Default Frame Rate:**
- Default: 24 fps
- Options: 12, 24, 30, 60 fps

**Default Duration:**
- Default: 24 frames (1 second @ 24fps)
- Can be extended as needed

### Tool Settings

**Brush:**
- Default size: 10px
- Default opacity: 100%
- Pressure enabled: true (if tablet detected)
- Anti-aliasing: true

**Eraser:**
- Default size: 10px
- Soft mode: true

### Onion Skin Settings

**Defaults:**
- Enabled: true
- Previous frames: 1
- Next frames: 1
- Previous color: Green (#00FF00)
- Next color: Red (#FF0000)
- Opacity: 30%

### Interface Settings

**Theme:**
- Options: Dark (default), Light
- Applies to UI chrome only

**Font:**
- Default: Inconstant (custom)
- Alternative: System fonts

**Panel Layout:**
- Dock mode: Fixed (default)
- Island mode: Floating panels

## Configuration File

### Location

Configuration stored in browser localStorage:

```javascript
// Access via console
JSON.parse(localStorage.getItem('celstomp-config'));
```

### Structure

```json
{
  "canvas": {
    "defaultWidth": 1920,
    "defaultHeight": 1080
  },
  "timeline": {
    "defaultFps": 24,
    "defaultFrameCount": 24
  },
  "tools": {
    "brush": {
      "defaultSize": 10,
      "pressureEnabled": true
    }
  },
  "ui": {
    "theme": "dark",
    "layout": "dock"
  },
  "shortcuts": {
    "custom": {}
  }
}
```

### Resetting Configuration

Reset to defaults:

```javascript
// In browser console
localStorage.removeItem('celstomp-config');
location.reload();
```

## URL Parameters

Pass configuration via URL:

```
https://ginyo.space/celstomp/?fps=30&theme=light
```

### Available Parameters

| Parameter | Values | Description |
|-----------|--------|-------------|
| fps | 12, 24, 30, 60 | Default frame rate |
| theme | dark, light | UI theme |
| width | number | Canvas width |
| height | number | Canvas height |
| layout | dock, island | Panel layout |
| onion | true, false | Enable onion skin |
| tutorial | true, false | Show tutorial |

### Example URLs

**Animation at 30fps:**
```
?fps=30
```

**Light theme with custom size:**
```
?theme=light&width=1280&height=720
```

**Skip tutorial:**
```
?tutorial=false
```

## Environment Variables

For local development:

### .env.development

```bash
# Development server
VITE_DEV_PORT=5173

# Hot reload
VITE_HMR=true

# Source maps
VITE_SOURCE_MAPS=true
```

### .env.production

```bash
# Build optimization
VITE_MINIFY=true
VITE_COMPRESSION=true

# Analytics (if added)
VITE_ANALYTICS_ID=
```

## Advanced Configuration

### Custom Shortcuts

Modify keyboard shortcuts:

```javascript
// Add custom shortcut
window.shortcutManager.register('ctrl+shift+s', () => {
  exportHelper.exportMp4({ quality: 'high' });
});
```

### Custom Tools

Register custom tools:

```javascript
window.toolManager.register('smudge', {
  name: 'Smudge',
  shortcut: '8',
  cursor: 'crosshair',
  onPointerDown: (e) => { /* ... */ },
  onPointerMove: (e) => { /* ... */ },
  onPointerUp: (e) => { /* ... */ }
});
```

### Custom Export Presets

Add export configurations:

```javascript
window.exportPresets.add('social', {
  format: 'mp4',
  width: 1080,
  height: 1080,
  fps: 30,
  quality: 'high'
});
```

## Performance Configuration

### Memory Limits

Adjust based on available RAM:

```javascript
// In console
window.celstompConfig.set('maxUndoSteps', 50);  // Default: 100
window.celstompConfig.set('cacheSize', 100);     // MB, default: 200
```

### Rendering

```javascript
// Disable anti-aliasing for pixel art
window.celstompConfig.set('antiAliasing', false);

// Reduce onion skin quality for performance
window.celstompConfig.set('onionQuality', 'low');
```

## Storage Configuration

### Autosave

```javascript
// Enable/disable
window.celstompConfig.set('autosave', true);

// Interval (milliseconds)
window.celstompConfig.set('autosaveInterval', 30000);  // 30 seconds

// Maximum backups
window.celstompConfig.set('maxAutosaves', 10);
```

### Export Location

```javascript
// Default download folder (browser dependent)
window.celstompConfig.set('defaultExportPath', 'celstomp-exports');
```

## Troubleshooting

### Settings Not Saving

**Problem:** Changes don't persist

**Solutions:**
1. Check browser localStorage is enabled
2. Clear browser data and try again
3. Check for errors in console
4. Try different browser

### URL Parameters Not Working

**Problem:** Parameters ignored

**Solutions:**
1. Check parameter spelling
2. Verify values are valid
3. Clear browser cache
4. Check for JavaScript errors

### Configuration Corrupted

**Problem:** Strange behavior

**Solution:** Reset configuration:
```javascript
localStorage.removeItem('celstomp-config');
location.reload();
```

## Best Practices

### Project-Specific Settings

Save project-specific settings in the project file, not global config.

### Version Control

Don't commit local configuration:

```gitignore
# .gitignore
.env.local
.env.*.local
```

### Sharing Configurations

Export/import settings:

```javascript
// Export
const config = localStorage.getItem('celstomp-config');
// Save to file

// Import
// Load from file
localStorage.setItem('celstomp-config', config);
```

## Configuration Reference

### Complete Option List

```javascript
const defaultConfig = {
  // Canvas
  defaultCanvasWidth: 1920,
  defaultCanvasHeight: 1080,
  defaultAspectRatio: '16:9',
  
  // Timeline
  defaultFps: 24,
  defaultFrameCount: 24,
  
  // Tools
  brush: {
    defaultSize: 10,
    defaultOpacity: 1,
    pressureEnabled: true,
    antiAliasing: true
  },
  eraser: {
    defaultSize: 10,
    soft: true
  },
  
  // Onion skin
  onionSkin: {
    enabled: true,
    prevFrames: 1,
    nextFrames: 1,
    prevColor: '#00FF00',
    nextColor: '#FF0000',
    opacity: 0.3
  },
  
  // UI
  theme: 'dark',
  layout: 'dock',
  font: 'Inconstant',
  
  // Performance
  maxUndoSteps: 100,
  cacheSize: 200,
  renderQuality: 'high',
  
  // Storage
  autosave: true,
  autosaveInterval: 30000,
  maxAutosaves: 10,
  
  // Export
  defaultExportFormat: 'mp4',
  defaultExportQuality: 'high'
};
```

## See Also

- [Building from Source](../development/building.md) - Development config
- [File Formats](./file-formats.md) - Project file structure
- [FAQ](./faq.md) - Common questions
