# API Overview

This reference covers the public APIs exposed by Celstomp modules.

## Core Module

### colorManager

Color manipulation utilities.

```javascript
// Convert hex to RGB
const rgb = colorManager.hexToRgb('#FF0000');
// Returns: { r: 255, g: 0, b: 0 }

// Convert RGB to hex
const hex = colorManager.rgbToHex(255, 0, 0);
// Returns: '#FF0000'

// Blend colors
const blended = colorManager.blend('#FF0000', '#0000FF', 0.5);
// Returns mixed color
```

### runtimeUtils

General utility functions.

```javascript
// Clamp value
const clamped = runtimeUtils.clamp(value, min, max);

// Debounce function
const debounced = runtimeUtils.debounce(func, delay);

// Throttle function
const throttled = runtimeUtils.throttle(func, limit);

// Generate ID
const id = runtimeUtils.generateId();
```

### timeHelper

Time-related utilities.

```javascript
// Format time
const formatted = timeHelper.formatTime(seconds);
// Returns: "0:00:00"

// Frame to time
const time = timeHelper.frameToTime(frame, fps);

// Time to frame
const frame = timeHelper.timeToFrame(time, fps);
```

### zoomHelper

Zoom and pan utilities.

```javascript
// Set zoom level
zoomHelper.setZoom(level);

// Get current zoom
const zoom = zoomHelper.getZoom();

// Reset zoom
zoomHelper.resetZoom();

// Pan to position
zoomHelper.panTo(x, y);
```

## Editor Module

### layerManager

Layer management API.

```javascript
// Get all layers
const layers = layerManager.getLayers();

// Get active layer
const active = layerManager.getActiveLayer();

// Set active layer
layerManager.setActiveLayer('LINE');

// Toggle layer visibility
layerManager.toggleLayer('LINE');

// Set layer opacity
layerManager.setOpacity('LINE', 0.5);

// Get layer opacity
const opacity = layerManager.getOpacity('LINE');
```

### timelineHelper

Timeline control API.

```javascript
// Get current frame
const frame = timelineHelper.currentFrame;

// Get total frames
const total = timelineHelper.totalFrames;

// Go to frame
timelineHelper.goToFrame(10);

// Go to next frame
timelineHelper.nextFrame();

// Go to previous frame
timelineHelper.prevFrame();

// Add frame
timelineHelper.addFrame();

// Delete frame
timelineHelper.deleteFrame(frameNumber);

// Play animation
timelineHelper.play();

// Stop animation
timelineHelper.stop();

// Toggle loop
timelineHelper.toggleLoop();

// Set frame rate
timelineHelper.setFps(24);
```

### historyHelper

Undo/redo system.

```javascript
// Record action
historyHelper.record({
  type: 'draw',
  layer: 'LINE',
  frame: 1,
  data: drawingData
});

// Undo
historyHelper.undo();

// Redo
historyHelper.redo();

// Check if can undo
const canUndo = historyHelper.canUndo();

// Check if can redo
const canRedo = historyHelper.canRedo();

// Clear history
historyHelper.clear();
```

### canvasHelper

Canvas operations.

```javascript
// Get canvas context
const ctx = canvasHelper.getContext();

// Clear canvas
canvasHelper.clear();

// Draw image
canvasHelper.drawImage(image, x, y);

// Get canvas data
const data = canvasHelper.getImageData();

// Put canvas data
canvasHelper.putImageData(data);

// Resize canvas
canvasHelper.resize(width, height);
```

### exportHelper

Export functionality.

```javascript
// Export as MP4
exportHelper.exportMp4({
  format: 'mp4',
  quality: 'high',
  fps: 24,
  startFrame: 1,
  endFrame: 24
});

// Export as GIF
exportHelper.exportGif({
  format: 'gif',
  colors: 256,
  fps: 15
});

// Export as image sequence
exportHelper.exportImageSequence({
  format: 'png',
  prefix: 'frame_'
});
```

## Input Module

### pointerEvents

Pointer event handling.

```javascript
// Register handler
pointerEvents.on('pointerdown', (e) => {
  console.log('Pointer down at:', e.x, e.y);
});

// Available events:
// - pointerdown
// - pointermove
// - pointerup
// - pointercancel
```

## Tools Module

### brushHelper

Brush tool API.

```javascript
// Set brush size
brushHelper.setSize(10);

// Get brush size
const size = brushHelper.getSize();

// Set brush color
brushHelper.setColor('#000000');

// Get brush color
const color = brushHelper.getColor();

// Enable pressure
brushHelper.setPressureEnabled(true);

// Set brush shape
brushHelper.setShape('round'); // 'round' or 'square'
```

### eraserManager

Eraser tool API.

```javascript
// Set eraser size
eraserManager.setSize(10);

// Set eraser opacity
eraserManager.setOpacity(1);

// Set soft/hard eraser
eraserManager.setSoft(true);
```

## UI Module

### uiComponents

UI component management.

```javascript
// Show modal
uiComponents.showModal('export', options);

// Hide modal
uiComponents.hideModal();

// Show notification
uiComponents.showNotification('Saved!', 'success');

// Update status bar
uiComponents.updateStatus('Frame 12 of 24');
```

### swatchHandler

Color swatch management.

```javascript
// Add swatch
swatchHandler.addSwatch('#FF0000');

// Remove swatch
swatchHandler.removeSwatch(index);

// Get all swatches
const swatches = swatchHandler.getSwatches();

// Load palette
swatchHandler.loadPalette(paletteData);

// Export palette
const palette = swatchHandler.exportPalette();
```

## Events

Celstomp emits custom events you can listen to:

```javascript
// Frame change
window.addEventListener('framechange', (e) => {
  console.log('Frame:', e.detail.frame);
});

// Layer change
window.addEventListener('layerchange', (e) => {
  console.log('Layer:', e.detail.layer);
});

// Playback state
window.addEventListener('playback', (e) => {
  console.log('Playing:', e.detail.isPlaying);
});

// Export complete
window.addEventListener('exportcomplete', (e) => {
  console.log('Export done:', e.detail.format);
});
```

### Event Reference

| Event | Detail | Description |
|-------|--------|-------------|
| framechange | `{ frame: number }` | Frame changed |
| layerchange | `{ layer: string }` | Active layer changed |
| playback | `{ isPlaying: boolean }` | Playback state changed |
| exportstart | `{ format: string }` | Export started |
| exportprogress | `{ progress: number }` | Export progress (0-100) |
| exportcomplete | `{ format: string }` | Export finished |
| layervisibility | `{ layer: string, visible: boolean }` | Layer toggled |
| undo | `{ action: object }` | Undo performed |
| redo | `{ action: object }` | Redo performed |

## Configuration

### Global Settings

Access via `window.celstompConfig`:

```javascript
// Read setting
const fps = window.celstompConfig.get('fps');

// Set setting
window.celstompConfig.set('fps', 24);

// Available settings:
// - fps: number (frame rate)
// - onionSkinEnabled: boolean
// - brushSize: number
// - autoSave: boolean
// - theme: string ('dark' | 'light')
```

## Examples

### Custom Brush Tool

```javascript
// Create custom brush behavior
(function () {
  'use strict';
  
  const myBrush = {
    draw(x, y, pressure) {
      const size = brushHelper.getSize() * pressure;
      const ctx = canvasHelper.getContext();
      
      ctx.beginPath();
      ctx.arc(x, y, size, 0, Math.PI * 2);
      ctx.fill();
    }
  };
  
  // Register with input system
  pointerEvents.on('pointerdown', (e) => {
    if (brushHelper.isActive()) {
      myBrush.draw(e.x, e.y, e.pressure);
    }
  });
})();
```

### Custom Export Format

```javascript
// Add custom export
(function () {
  'use strict';
  
  exportHelper.registerFormat('custom', {
    async export(options) {
      const frames = [];
      
      for (let i = options.startFrame; i <= options.endFrame; i++) {
        timelineHelper.goToFrame(i);
        const data = canvasHelper.getImageData();
        frames.push(data);
      }
      
      // Process frames...
      return processedData;
    }
  });
})();
```

## TypeScript Support

While Celstomp is vanilla JavaScript, you can add type definitions:

```typescript
// celstomp.d.ts
declare namespace Celstomp {
  interface Layer {
    id: string;
    opacity: number;
    visible: boolean;
  }
  
  interface TimelineHelper {
    currentFrame: number;
    totalFrames: number;
    goToFrame(frame: number): void;
    // ...
  }
}

declare const layerManager: {
  getLayers(): Celstomp.Layer[];
  getActiveLayer(): string;
  setActiveLayer(layer: string): void;
};

declare const timelineHelper: Celstomp.TimelineHelper;
```

## Notes

- APIs may change between versions
- Check `window` object to see available APIs
- Most modules expose their API on `window`
- Use events for loose coupling between modules
- APIs are not officially stable - use at your own risk

## See Also

- [Architecture](./architecture.md) - System design
- [Code Organization](./code-organization.md) - Module patterns
- [File Formats](./file-formats.md) - Data structures
