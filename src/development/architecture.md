# Architecture

Understanding Celstomp's architecture helps developers contribute effectively and users appreciate how the application works.

## System Overview

Celstomp is a client-side web application with no server requirements. Everything runs in the browser.

### Architecture Diagram

```
┌─────────────────────────────────────────────┐
│              User Interface                  │
│  ┌─────────┐  ┌─────────┐  ┌──────────┐    │
│  │ Header  │  │ Stage   │  │ Panels   │    │
│  └─────────┘  └─────────┘  └──────────┘    │
└─────────────────────────────────────────────┘
                      │
┌─────────────────────────────────────────────┐
│           Application Logic                  │
│  ┌──────────┐  ┌──────────┐  ┌──────────┐   │
│  │   Core   │  │  Editor  │  │   UI     │   │
│  │  Utils   │  │  Canvas  │  │ Events   │   │
│  └──────────┘  └──────────┘  └──────────┘   │
└─────────────────────────────────────────────┘
                      │
┌─────────────────────────────────────────────┐
│              Data Layer                      │
│  ┌──────────┐  ┌──────────┐  ┌──────────┐   │
│  │  Layers  │  │  Frames  │  │ History  │   │
│  └──────────┘  └──────────┘  └──────────┘   │
└─────────────────────────────────────────────┘
                      │
┌─────────────────────────────────────────────┐
│           Storage & Export                   │
│  ┌──────────┐  ┌──────────┐  ┌──────────┐   │
│  │localStorage│ │   JSON   │  │  Media   │   │
│  └──────────┘  └──────────┘  └──────────┘   │
└─────────────────────────────────────────────┘
```

## Core Components

### UI Layer

Handles user interaction:

**Responsibilities:**
- Render interface elements
- Handle user input
- Update display
- Manage layout

**Key files:**
- `ui-components.js` - Reusable UI elements
- `menu-wires.js` - Menu connections
- `island-helper.js` - Floating UI elements

### Application Logic

The heart of the application:

**Core Module:**
- Shared utilities
- Color management
- Time helpers
- Zoom helpers

**Editor Module:**
- Canvas operations
- Timeline management
- Layer system
- History/undo
- Export functions

**Input Module:**
- Pointer event handling
- Touch support
- Keyboard shortcuts

**Tools Module:**
- Brush implementation
- Eraser logic
- Selection tools
- Fill algorithms

### Data Layer

Manages application state:

**State Management:**
- Current frame
- Active layer
- Tool settings
- View state

**Data Structures:**
- Layer objects
- Frame arrays
- Cel references
- History stack

## Module System

### Barrel Pattern

Celstomp uses a barrel loading pattern:

```javascript
// index.js defines barrel
barrels.editor = [
  './js/editor/layer-manager.js',
  './js/editor/timeline-helper.js',
  './js/editor/history-helper.js',
  './js/editor/canvas-helper.js',
  './js/editor/export-helper.js'
];

// html-loader.js loads barrels dynamically
```

Benefits:
- **Modular loading** - Load only needed modules
- **Dependency management** - Clear relationships
- **Code organization** - Logical grouping

### Module Categories

**Core (`js/core/`):**
Shared primitives and utilities

**Editor (`js/editor/`):**
Animation editing functionality

**Input (`js/input/`):**
Event handling and user input

**Tools (`js/tools/`):**
Drawing and manipulation tools

**UI (`js/ui/`):**
Interface components and layout

## Data Flow

### User Action Flow

1. **User input** - Click, key press, gesture
2. **Input handler** - Processes raw input
3. **Tool logic** - Determines action
4. **State update** - Modify application state
5. **Canvas render** - Update display
6. **History record** - Save for undo

### Example: Brush Stroke

```
User drags mouse
    ↓
Pointer event fired
    ↓
Input module captures
    ↓
Brush tool calculates path
    ↓
Canvas helper applies pixels
    ↓
Layer data updated
    ↓
Display refreshed
    ↓
History records action
```

## Canvas System

### HTML5 Canvas API

Celstomp uses the HTML5 Canvas 2D context:

- **Main canvas** - Display and interaction
- **Layer canvases** - Individual layer data
- **Offscreen canvases** - Processing and export

### Rendering Pipeline

1. **Clear main canvas**
2. **Render layers** (bottom to top):
   - Apply blend modes
   - Apply opacity
   - Composite to main
3. **Apply onion skin** (if enabled)
4. **Apply UI overlays**
5. **Present to screen**

### Performance Considerations

- **Dirty rectangles** - Only redraw changed areas
- **Layer caching** - Cache layer renders
- **RequestAnimationFrame** - Sync with display
- **Image smoothing** - Disable for pixel art

## Storage Architecture

### In-Memory State

Active while app runs:

```javascript
// Conceptual state structure
const state = {
  currentFrame: 1,
  currentLayer: 'LINE',
  layers: {
    LINE: { cels: {...}, opacity: 1 },
    SHADE: { cels: {...}, opacity: 0.5 },
    // ...
  },
  timeline: {
    frames: [...],
    fps: 24
  },
  history: {
    stack: [...],
    position: 0
  }
};
```

### Persistent Storage

Saves between sessions:

**localStorage:**
- Autosave data
- User preferences
- Palette storage
- Tutorial progress

**IndexedDB (optional):**
- Large project files
- Cache data
- Offline support

### Project File Format

JSON structure:

```json
{
  "version": "1.0",
  "metadata": {
    "created": "2024-01-15",
    "modified": "2024-01-16"
  },
  "canvas": {
    "width": 1920,
    "height": 1080,
    "backgroundColor": "#ffffff"
  },
  "timeline": {
    "frameCount": 120,
    "fps": 24
  },
  "layers": [
    {
      "id": "LINE",
      "type": "vector",
      "opacity": 1,
      "blendMode": "normal",
      "cels": {...}
    }
  ],
  "palette": [...]
}
```

## Export System

### Client-Side Processing

All export happens in browser:

- **MP4** - Canvas recording + ffmpeg.js
- **GIF** - Frame extraction + omggif.js
- **Images** - Canvas toDataURL()
- **JSON** - JSON.stringify()

### Export Pipeline

1. **Validate range** - Check frame selection
2. **Render frames** - Draw each frame
3. **Process media** - Encode to format
4. **Generate blob** - Create file
5. **Trigger download** - User saves file

### Memory Management

Large exports handled carefully:

- **Batch processing** - Process in chunks
- **Garbage collection** - Clean up between frames
- **Progress indicators** - Show export status
- **Cancellation** - Allow stopping export

## Service Worker

### PWA Support

Service worker enables:

- **Offline usage** - App works without internet
- **Background sync** - Queue actions offline
- **Cache management** - Store assets locally
- **Install prompt** - Add to home screen

### Cache Strategy

**Cache-first:**
- Check cache first
- Serve cached version
- Update in background

Benefits:
- Fast loading
- Works offline
- Reduced bandwidth

## Browser APIs Used

### Core APIs

- **Canvas 2D Context** - Drawing and rendering
- **Pointer Events** - Unified mouse/touch input
- **localStorage** - Persistent storage
- **File API** - File import/export
- **Blob API** - Binary data handling

### Media APIs

- **MediaRecorder** - Canvas recording
- **HTMLCanvasElement.captureStream()** - Video stream
- **Canvas.toBlob()** - Image export

### PWA APIs

- **Service Worker** - Background processing
- **Cache API** - Asset caching
- **Web App Manifest** - Install support
- **BeforeInstallPrompt** - Install UI

## Security Considerations

### Client-Side Only

Celstomp never sends data to servers:

- All processing in browser
- No user accounts
- No data collection
- No tracking

### File Safety

Safe file handling:

- JSON parsed (not executed)
- Images validated
- No external scripts loaded
- Content Security Policy

### Browser Storage

Data stays in browser:

- localStorage is sandboxed
- Cleared when browser data cleared
- Not shared across domains
- User controls via browser settings

## Performance Architecture

### Optimization Strategies

**Rendering:**
- Dirty rectangle updates
- Layer compositing
- Hardware acceleration

**Memory:**
- Object pooling
- Canvas reuse
- Garbage collection

**Responsiveness:**
- Async operations
- Web Workers (optional)
- Debounced updates

### Profiling Points

Monitor performance:

- Frame render time
- Memory usage
- Input latency
- Export speed

## Future Architecture

### Potential Improvements

**WebGL Rendering:**
- GPU acceleration
- Better performance
- Shader effects

**Web Workers:**
- Background export
- Non-blocking UI
- Parallel processing

**IndexedDB:**
- Larger storage
- Structured data
- Better querying

## See Also

- [Project Structure](./project-structure.md) - File organization
- [Code Organization](./code-organization.md) - Module patterns
- [Building from Source](./building.md) - Build process
