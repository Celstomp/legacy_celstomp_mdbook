# Building from Source

Build Celstomp locally to customize, contribute, or run offline.

## Prerequisites

### Required Software

- **Git** - Version control
- **Node.js** 18+ - JavaScript runtime
- **npm** 8+ - Package manager (comes with Node)

Verify installation:

```bash
git --version
node --version
npm --version
```

### Optional Software

- **Python 3.x** - Alternative dev server
- **Code editor** - VS Code recommended

## Getting the Code

### Clone Repository

```bash
git clone https://github.com/ginyoa/celstomp_v1.git
cd celstomp_v1
```

### Install Dependencies

```bash
npm install
```

This installs:
- Vite (build tool)
- Development dependencies

## Development Build

### Start Dev Server

```bash
npm run dev
```

Opens at `http://localhost:5173`

Features:
- **Hot reloading** - Auto-refresh on changes
- **Source maps** - Debug original code
- **Fast builds** - Optimized for development

### Alternative: Python Server

If you don't have Node.js:

**Mac/Linux:**
```bash
./run-dev.command
```

**Windows:**
```cmd
run-dev.bat
```

Or manually:

```bash
cd celstomp
python3 -m http.server 8000
```

Visit `http://localhost:8000`

## Production Build

### Create Build

```bash
npm run build
```

Output goes to `celstomp/dist/` directory.

### Preview Build

```bash
npm run preview
```

Opens at `http://localhost:4173`

Test the production build before deploying.

### Build Output

```
celstomp/dist/
├── index.html           # Entry point
├── assets/              # Bundled JS/CSS
├── js/                  # Module files
├── css/                 # Stylesheets
├── parts/               # HTML partials
├── icons/               # Icons
├── manifest.webmanifest # PWA manifest
└── service-worker.js    # Offline support
```

## Build Configuration

### Vite Config

Edit `vite.config.mjs`:

```javascript
export default defineConfig({
  root: 'celstomp',
  base: './',
  build: {
    outDir: 'dist',
    emptyOutDir: true,
  },
  // Customizations here
});
```

### Custom Build Steps

Add to Vite config:

```javascript
function customPlugin() {
  return {
    name: 'custom-plugin',
    apply: 'build',
    closeBundle() {
      // Custom build logic
      console.log('Build complete!');
    }
  };
}

export default defineConfig({
  plugins: [customPlugin()]
});
```

## Customization

### Changing Default Settings

Edit `js/core/runtime-utils.js`:

```javascript
const DEFAULTS = {
  canvasWidth: 1920,
  canvasHeight: 1080,
  fps: 24,
  brushSize: 10
};
```

### Adding Features

1. **Create module** in appropriate folder
2. **Export from barrel** (index.js)
3. **Wire into app** (celstomp-app.js)
4. **Test thoroughly**

### Styling Changes

Edit CSS in `css/` directory:

```css
/* css/components/custom.css */
.custom-element {
  background: var(--color-primary);
}
```

Import in `css/main.css`:

```css
@import './components/custom.css';
```

## Troubleshooting Builds

### Build Fails

**Error:** `Cannot find module`

```bash
# Clear cache
rm -rf node_modules
rm package-lock.json
npm install
```

**Error:** `Out of memory`

```bash
# Increase Node memory
export NODE_OPTIONS="--max-old-space-size=4096"
npm run build
```

### Dev Server Issues

**Port already in use:**

```bash
# Use different port
npm run dev -- --port 3000
```

**Changes not showing:**

```bash
# Hard refresh browser
Ctrl + Shift + R

# Or restart dev server
Ctrl + C
npm run dev
```

### Build Output Issues

**Missing files:**

Check `vite.config.mjs` copy plugin. Ensure files are listed:

```javascript
copyFile('service-worker.js', 'service-worker.js');
```

**Assets 404:**

Check base path in config:

```javascript
base: './',  // Relative paths
// or
base: '/celstomp/',  // Absolute path
```

## Deployment

### Static Hosting

Upload `dist/` folder to:

- **GitHub Pages**
- **Netlify**
- **Vercel**
- **Any static host**

### GitHub Pages

1. Build: `npm run build`
2. Copy `dist/` to `docs/` folder (or `gh-pages` branch)
3. Push to GitHub
4. Enable Pages in repository settings

### Netlify

1. Connect GitHub repository
2. Build command: `npm run build`
3. Publish directory: `celstomp/dist`
4. Deploy

## Development Workflow

### Making Changes

1. **Start dev server:** `npm run dev`
2. **Make changes** in source files
3. **Test in browser** (auto-refreshes)
4. **Build for production:** `npm run build`
5. **Test production build:** `npm run preview`

### Adding Dependencies

```bash
npm install package-name
```

For development only:

```bash
npm install --save-dev package-name
```

### Updating Dependencies

```bash
npm update
```

Or specific package:

```bash
npm update package-name
```

## Performance Optimization

### Bundle Analysis

```bash
npm install --save-dev rollup-plugin-visualizer
```

Add to `vite.config.mjs`:

```javascript
import { visualizer } from 'rollup-plugin-visualizer';

export default defineConfig({
  plugins: [
    // ... other plugins
    visualizer()
  ]
});
```

### Code Splitting

Vite automatically splits code. Control with:

```javascript
// Dynamic imports
const module = await import('./heavy-module.js');
```

### Asset Optimization

- **Images** - Compress before adding
- **Fonts** - Use WOFF2 format
- **CSS** - Minified automatically

## Advanced Building

### Custom Environments

Create `.env` files:

```bash
# .env.development
VITE_API_URL=http://localhost:3000

# .env.production
VITE_API_URL=https://api.example.com
```

Access in code:

```javascript
const apiUrl = import.meta.env.VITE_API_URL;
```

### Conditional Building

```javascript
// vite.config.mjs
export default defineConfig(({ mode }) => {
  return {
    build: {
      minify: mode === 'production',
      sourcemap: mode === 'development'
    }
  };
});
```

## Next Steps

After building:

- [Contributing](./contributing.md) - Submit your changes
- [Testing](./testing.md) - Ensure quality
- [Deployment](./deployment.md) - Go live

## See Also

- [Project Structure](./project-structure.md) - File organization
- [Code Organization](./code-organization.md) - Coding patterns
- [Architecture](./architecture.md) - System design
