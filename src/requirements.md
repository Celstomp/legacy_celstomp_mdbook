# System Requirements

Celstomp runs in your web browser. Here's what you need for the best experience.

## Browser Support

Celstomp works on all modern browsers:

| Browser | Minimum Version | Notes |
|---------|----------------|-------|
| Chrome | 90+ | Fully supported |
| Firefox | 88+ | Fully supported |
| Safari | 14+ | Fully supported |
| Edge | 90+ | Fully supported |

**Recommendation:** Use Chrome or Firefox for the best performance with large projects.

## Operating System

Celstomp is OS-agnostic. It runs on:

- Windows 10/11
- macOS 10.15+
- Linux (any modern distro)
- ChromeOS

## Hardware Requirements

### Minimum Specs

- **RAM:** 4 GB
- **Storage:** 100 MB for the app (projects saved locally)
- **Display:** 1280x720 resolution
- **Input:** Mouse or trackpad

### Recommended Specs

- **RAM:** 8 GB or more (for complex projects)
- **Storage:** 500 MB free space
- **Display:** 1920x1080 or higher
- **Input:** Drawing tablet with pressure sensitivity

## For Local Development

If you want to run Celstomp locally:

### Using Vite (Recommended)

- **Node.js:** 18.0.0 or newer
- **npm:** 8.0.0 or newer (comes with Node)

Check your versions:

```bash
node --version
npm --version
```

### Using Python

- **Python:** 3.7 or newer

Check your version:

```bash
python3 --version
```

## Drawing Tablet Support

Celstomp supports pressure-sensitive drawing tablets:

- Wacom tablets (Intuos, Cintiq)
- Huion tablets
- XP-Pen tablets
- Apple Pencil (on iPad with compatible browser)
- Microsoft Surface Pen

**Note:** Pressure sensitivity requires a browser that supports the Pointer Events API (all modern browsers do).

## Mobile Devices

Celstomp works on tablets and phones, though the interface is optimized for desktop:

- **iPad:** Safari on iPadOS 14+
- **Android tablets:** Chrome on Android 10+
- **Phones:** Possible but not recommended for serious work

For mobile use, connect a stylus for better drawing precision.

## Network Requirements

**For live version:**
- Internet connection required
- Works offline after first load (PWA support)
- No data usage while drawing (only on initial load)

**For local version:**
- No internet required
- Runs entirely on your machine

## Performance Tips

If Celstomp feels slow:

1. **Close other browser tabs** - frees up RAM
2. **Reduce canvas size** - smaller dimensions = better performance
3. **Limit layers** - merge layers when possible
4. **Lower frame count** - work in chunks for long animations
5. **Use Chrome or Firefox** - typically faster for canvas operations

## Checking Browser Compatibility

To verify your browser supports all Celstomp features:

1. Open the browser console (F12)
2. Look for any red error messages
3. Check that these APIs are supported:
   - Canvas 2D context
   - Pointer Events
   - localStorage
   - File API

## Getting Help

If you're having trouble:

- Check the [FAQ](./reference/faq.md)
- See [Troubleshooting](./reference/troubleshooting.md)
- Open an issue on GitHub
