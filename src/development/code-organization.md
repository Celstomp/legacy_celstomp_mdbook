# Code Organization

Celstomp uses modern JavaScript patterns to keep code maintainable and modular.

## Module Pattern

### Barrel Exports

Each module folder has an `index.js` that defines what to load:

```javascript
// js/editor/index.js
(function () {
  'use strict';

  const barrels = window.__celstompBarrels || (window.__celstompBarrels = {});

  barrels.editor = [
    './js/editor/layer-manager.js',
    './js/editor/timeline-helper.js',
    './js/editor/history-helper.js',
    './js/editor/canvas-helper.js',
    './js/editor/export-helper.js'
  ];
})();
```

Benefits:
- **Dependency declaration** - Clear what each module needs
- **Lazy loading** - Load only when needed
- **Organization** - Logical grouping

### IIFE Pattern

Modules use Immediately Invoked Function Expressions:

```javascript
// js/core/color-manager.js
(function () {
  'use strict';

  // Private variables
  const defaultColor = '#000000';
  
  // Private functions
  function hexToRgb(hex) {
    // Implementation
  }

  // Public API
  window.colorManager = {
    convert: hexToRgb,
    // ...
  };
})();
```

Benefits:
- **Encapsulation** - Private variables
- **Namespace** - Avoid global pollution
- **Strict mode** - Catches errors

## Naming Conventions

### Variables

```javascript
// Constants (uppercase snake_case)
const MAX_BRUSH_SIZE = 200;
const DEFAULT_FPS = 24;

// Variables (camelCase)
let currentFrame = 1;
let brushSize = 10;

// Booleans (is/has prefix)
let isPlaying = false;
let hasSelection = true;

// Arrays (plural)
const layers = [];
const frames = [];

// Objects (descriptive)
const layerConfig = { opacity: 1 };
const timelineState = { current: 1 };
```

### Functions

```javascript
// Actions (verb + noun)
function drawLine() { }
function updateTimeline() { }
function handleClick() { }

// Getters (get + noun)
function getBrushSize() { }
function getCurrentLayer() { }

// Setters (set + noun)
function setBrushSize(size) { }
function setActiveLayer(layer) { }

// Checkers (is/has + noun)
function isLayerVisible(layer) { }
function hasUnsavedChanges() { }

// Event handlers (on + event)
function onMouseDown(e) { }
function onFrameChange() { }
```

### Classes (if used)

```javascript
// PascalCase
class LayerManager {
  constructor() {
    this.layers = [];
  }
  
  addLayer(config) {
    // Implementation
  }
}
```

## Code Structure

### File Template

```javascript
// js/module/feature-helper.js

(function () {
  'use strict';

  // ==========================================
  // Configuration
  // ==========================================
  const CONFIG = {
    maxRetries: 3,
    defaultTimeout: 5000
  };

  // ==========================================
  // Private State
  // ==========================================
  let privateVariable = null;
  const privateCache = new Map();

  // ==========================================
  // Private Functions
  // ==========================================
  function privateHelper() {
    // Implementation
  }

  // ==========================================
  // Public API
  // ==========================================
  window.featureHelper = {
    /**
     * Does something important
     * @param {string} param - Description
     * @returns {boolean} Result
     */
    publicMethod(param) {
      return privateHelper(param);
    }
  };
})();
```

### Function Organization

Within a module, organize by:

1. **Configuration** - Constants, defaults
2. **State** - Variables, caches
3. **Private functions** - Internal helpers
4. **Public API** - Exported functions
5. **Event handlers** - If applicable

## State Management

### Module-Level State

Each module manages its own state:

```javascript
// js/editor/timeline-helper.js
(function () {
  'use strict';

  // Module state
  let currentFrame = 1;
  let totalFrames = 24;
  let isPlaying = false;
  const frameCache = new Map();

  window.timelineHelper = {
    get currentFrame() { return currentFrame; },
    get totalFrames() { return totalFrames; },
    
    goToFrame(frame) {
      if (frame < 1 || frame > totalFrames) return;
      currentFrame = frame;
      this.emit('framechange', frame);
    }
  };
})();
```

### Event Communication

Modules communicate via events:

```javascript
// Publishing
window.dispatchEvent(new CustomEvent('layerchange', {
  detail: { layer: 'LINE' }
}));

// Subscribing
window.addEventListener('layerchange', (e) => {
  console.log('New layer:', e.detail.layer);
});
```

Benefits:
- **Loose coupling** - Modules don't depend directly
- **Reactive** - Auto-update on changes
- **Debuggable** - Events visible in DevTools

## Error Handling

### Try-Catch Pattern

```javascript
function riskyOperation() {
  try {
    // Potentially throwing code
    const result = calculateSomething();
    return result;
  } catch (error) {
    console.error('Operation failed:', error);
    // Fallback behavior
    return defaultValue;
  }
}
```

### Validation

```javascript
function setBrushSize(size) {
  // Validate input
  if (typeof size !== 'number') {
    console.warn('Brush size must be a number');
    return;
  }
  
  if (size < 1 || size > MAX_BRUSH_SIZE) {
    console.warn(`Brush size must be between 1 and ${MAX_BRUSH_SIZE}`);
    return;
  }
  
  brushSize = size;
}
```

### User Feedback

```javascript
function exportProject() {
  try {
    doExport();
    showNotification('Export complete!', 'success');
  } catch (error) {
    showNotification('Export failed: ' + error.message, 'error');
    console.error(error);
  }
}
```

## Comments

### When to Comment

**Do comment:**
- Complex algorithms
- Non-obvious behavior
- Public API documentation
- Workarounds or hacks

**Don't comment:**
- Obvious code
- What code does (show with code)
- Outdated comments

### Comment Style

```javascript
// Good: Explains why
// Using binary search because array is sorted
const index = binarySearch(arr, target);

// Bad: States the obvious
// Increment counter
 counter++;

// Good: Documents function
/**
 * Calculates the distance between two points
 * @param {number} x1 - First point X
 * @param {number} y1 - First point Y
 * @param {number} x2 - Second point X
 * @param {number} y2 - Second point Y
 * @returns {number} Distance in pixels
 */
function getDistance(x1, y1, x2, y2) {
  return Math.sqrt((x2 - x1) ** 2 + (y2 - y1) ** 2);
}
```

## Code Quality

### Consistency

- **Follow existing patterns** - Match the codebase
- **Use consistent formatting** - 2 spaces for indentation
- **Maintain naming conventions** - Throughout project

### Simplicity

```javascript
// Complex
function toggleVisibility(element) {
  if (element.style.display === 'none') {
    element.style.display = 'block';
  } else {
    element.style.display = 'none';
  }
}

// Simple
function toggleVisibility(element) {
  element.style.display = element.style.display === 'none' ? 'block' : 'none';
}
```

### Readability

```javascript
// Good
function calculateAverage(frames) {
  const total = frames.reduce((sum, frame) => sum + frame.duration, 0);
  return total / frames.length;
}

// Avoid
const calcAvg=f=>f.reduce((s,f)=>s+f.d,0)/f.length;
```

## Performance

### Efficient DOM Access

```javascript
// Cache references
const canvas = document.getElementById('canvas');
const ctx = canvas.getContext('2d');

// Reuse instead of querying repeatedly
for (let i = 0; i < 100; i++) {
  ctx.fillRect(i * 10, 0, 10, 10); // Good
  // document.getElementById('canvas').getContext('2d').fillRect(...) // Bad
}
```

### Debouncing

```javascript
function debounce(func, wait) {
  let timeout;
  return function executedFunction(...args) {
    const later = () => {
      clearTimeout(timeout);
      func(...args);
    };
    clearTimeout(timeout);
    timeout = setTimeout(later, wait);
  };
}

// Usage
const debouncedResize = debounce(() => {
  resizeCanvas();
}, 250);

window.addEventListener('resize', debouncedResize);
```

## Testing Approach

### Manual Testing

Test changes in:
- Chrome (primary)
- Firefox
- Safari (if available)
- Edge

### Test Checklist

- [ ] Feature works in all browsers
- [ ] No console errors
- [ ] Keyboard shortcuts work
- [ ] Touch input works (mobile)
- [ ] Export works
- [ ] Save/load works

## See Also

- [Architecture](./architecture.md) - System design
- [Project Structure](./project-structure.md) - File organization
- [Contributing](./contributing.md) - Contribution guidelines
