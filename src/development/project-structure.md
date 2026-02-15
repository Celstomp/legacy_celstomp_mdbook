# Project Structure

Understanding the file organization helps you navigate the codebase and contribute effectively.

## Root Directory

```
celstomp_v1/
├── celstomp/              # Main application
├── .github/               # GitHub templates
├── node_modules/          # Dependencies (if using npm)
├── .git/                  # Git repository
├── .gitignore             # Git ignore rules
├── LICENSE                # GPL v3 license
├── README.md              # Project documentation
├── CONTRIBUTING.md        # Contribution guidelines
├── SECURITY.md            # Security policy
├── CODE_OF_CONDUCT.md     # Community standards
├── package.json           # npm configuration
├── package-lock.json      # Locked dependencies
├── vite.config.mjs        # Vite build config
├── run-dev.bat            # Windows dev script
└── run-dev.command        # Mac/Linux dev script
```

## Main Application Directory

The `celstomp/` folder contains all application code:

```
celstomp/
├── index.html             # App entry point
├── manifest.webmanifest   # PWA manifest
├── service-worker.js      # Offline support
├── robots.txt             # SEO crawler hints
├── sitemap.xml            # SEO sitemap
├── celstomp-app.js        # Main application logic
├── celstomp-autosave.js   # Autosave functionality
├── celstomp-imgseq.js     # Image sequence export
├── css/                   # Stylesheets
├── js/                    # JavaScript modules
├── parts/                 # HTML partials
├── icons/                 # Icons and images
├── fonts/                 # Local fonts
└── dist/                  # Build output (generated)
```

## CSS Directory

Styles organized by component:

```
css/
├── base.css               # Base styles, resets
├── layout.css             # Layout utilities
├── main.css               # Main entry point
├── variables.css          # CSS custom properties
└── components/            # Component-specific
    ├── brushes.css        # Brush tool styles
    ├── header.css         # Header/menu styles
    ├── island.css         # Floating island UI
    ├── layers.css         # Layer panel styles
    ├── legacy.css         # Legacy compatibility
    ├── overlays.css       # Modal/overlay styles
    ├── timeline.css       # Timeline styles
    └── tools.css          # Tool panel styles
```

### CSS Architecture

**Variables (`variables.css`):**
```css
:root {
  --color-primary: #007bff;
  --color-bg: #1a1a1a;
  --spacing-sm: 8px;
  --spacing-md: 16px;
  --font-main: 'Inconstant', sans-serif;
}
```

**Base (`base.css`):**
- CSS reset
- Typography
- Global defaults

**Components:**
- BEM naming convention
- Scoped to component
- Modular and reusable

## JavaScript Directory

Modular code organized by function:

```
js/
├── html-loader.js         # Module loader
├── init.js                # Initialization
├── omggif.js              # GIF encoder (vendor)
├── core/                  # Core utilities
├── editor/                # Editing features
├── input/                 # Input handling
├── tools/                 # Drawing tools
└── ui/                    # UI components
```

### Core Module (`js/core/`)

Shared primitives and utilities:

```
core/
├── color-manager.js       # Color utilities
├── runtime-utils.js       # Runtime helpers
├── time-helper.js         # Time functions
├── zoom-helper.js         # Zoom handling
└── index.js               # Barrel exports
```

**Responsibilities:**
- Color space conversions
- Utility functions
- Helper classes
- Shared constants

### Editor Module (`js/editor/`)

Animation editing functionality:

```
editor/
├── canvas-helper.js       # Canvas operations
├── export-helper.js       # Export functions
├── history-helper.js      # Undo/redo system
├── layer-manager.js       # Layer management
├── timeline-helper.js     # Timeline control
└── index.js               # Barrel exports
```

**Responsibilities:**
- Drawing operations
- Layer management
- Timeline control
- Export processing
- History tracking

### Input Module (`js/input/`)

User input handling:

```
input/
├── pointer-events.js      # Pointer event handling
├── pointer-wire.js        # Event routing
└── index.js               # Barrel exports
```

**Responsibilities:**
- Mouse events
- Touch events
- Pen/tablet input
- Keyboard shortcuts
- Gesture recognition

### Tools Module (`js/tools/`)

Drawing and selection tools:

```
tools/
├── brush-helper.js        # Brush implementation
├── eraser-manager.js      # Eraser tool
├── lasso-helper.js        # Lasso selection
└── index.js               # Barrel exports
```

**Responsibilities:**
- Tool logic
- Drawing algorithms
- Selection operations
- Tool state management

### UI Module (`js/ui/`)

User interface components:

```
ui/
├── color-wheel.js         # Color picker
├── dock-helper.js         # Dock layout
├── interaction-shortcuts.js # Keyboard handling
├── island-helper.js       # Island UI
├── menu-wires.js          # Menu connections
├── mobile-native-zoom-guard.js # Mobile support
├── mount-island-dock.js   # Component mounting
├── swatch-handler.js      # Color swatches
├── ui-components.js       # Reusable components
└── index.js               # Barrel exports
```

**Responsibilities:**
- Component rendering
- Layout management
- Event binding
- State synchronization

## HTML Partials (`parts/`)

Dynamic HTML templates:

```
parts/
├── header.js              # Top menu bar
├── modals.js              # Modal dialogs
├── sidepanel.js           # Side panels
├── stage.js               # Canvas stage
└── timeline.js            # Timeline UI
```

**Pattern:**
```javascript
// parts/header.js
window.__celstompParts = window.__celstompParts || {};
window.__celstompParts.header = `
  <header class="app-header">
    <nav>...</nav>
  </header>
`;
```

Injected at runtime by `html-loader.js`.

## Assets

### Icons (`icons/`)

```
icons/
├── favicon.ico            # Browser favicon
├── favicon.svg            # Vector favicon
├── screenshot-wide.png    # PWA wide screenshot
└── screenshot-narrow.png  # PWA narrow screenshot
```

### Fonts (`fonts/`)

```
fonts/
└── Inconstant-Regular.woff2  # Primary font
```

## Configuration Files

### Vite Configuration

`vite.config.mjs`:
- Build settings
- Plugin configuration
- Asset copying
- Dev server options

### Package Configuration

`package.json`:
- Project metadata
- Dependencies
- Scripts (dev, build, preview)

### PWA Manifest

`manifest.webmanifest`:
- App name and description
- Icons and screenshots
- Display mode
- Categories

## Build Output

`dist/` directory (generated):

```
dist/
├── index.html             # Built HTML
├── assets/                # Bundled assets
│   ├── index-*.js         # Main JS bundle
│   └── index-*.css        # Main CSS bundle
├── js/                    # Copied modules
├── css/                   # Copied styles
├── parts/                 # Copied partials
├── icons/                 # Copied icons
├── manifest.webmanifest   # Copied manifest
├── service-worker.js      # Copied SW
├── robots.txt             # Copied SEO file
└── sitemap.xml            # Copied SEO file
```

Generated by `npm run build`.

## Development Files

### Local Development

`run-dev.bat` (Windows):
```batch
@echo off
cd celstomp
python -m http.server 8000
```

`run-dev.command` (Mac/Linux):
```bash
#!/bin/bash
cd "$(dirname "$0")/celstomp"
python3 -m http.server 8000
```

### Git Configuration

`.gitignore`:
```
node_modules/
dist/
*.log
.DS_Store
```

## File Naming Conventions

### JavaScript

- **kebab-case** - `file-name.js`
- **descriptive** - `layer-manager.js` not `lm.js`
- **suffixes** - `-helper.js`, `-manager.js`, `-utils.js`

### CSS

- **kebab-case** - `file-name.css`
- **component-based** - `component-name.css`
- **BEM classes** - `.block__element--modifier`

### Assets

- **lowercase** - `file-name.png`
- **descriptive** - `screenshot-wide.png`
- **no spaces** - Use hyphens

## Import Patterns

### Module Imports

```javascript
// From barrel
import { layerManager } from './js/editor/index.js';

// Direct import
import { utils } from './js/core/runtime-utils.js';
```

### CSS Imports

```css
/* From main.css */
@import './variables.css';
@import './components/header.css';
```

## Best Practices

### Adding New Files

1. **Place in correct directory** - Match existing structure
2. **Follow naming conventions** - Consistent with project
3. **Export from barrel** - Add to index.js
4. **Update documentation** - Document in comments

### Modifying Files

1. **Check dependencies** - What relies on this file?
2. **Test thoroughly** - Multiple browsers
3. **Update barrels** - If adding exports
4. **Document changes** - In commit message

### Removing Files

1. **Check references** - Find all imports
2. **Update barrels** - Remove from index.js
3. **Update documentation** - Remove references
4. **Clean build** - Remove from dist

## See Also

- [Architecture](./architecture.md) - System design
- [Code Organization](./code-organization.md) - Module patterns
- [Contributing](./contributing.md) - Contribution guidelines
