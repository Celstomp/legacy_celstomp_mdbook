# Troubleshooting

Solutions to common problems you might encounter.

## Installation Issues

### Can't Install Dependencies

**Problem:** `npm install` fails

**Solutions:**

1. **Check Node.js version:**
```bash
node --version  # Should be 18+
```

2. **Clear npm cache:**
```bash
npm cache clean --force
rm -rf node_modules package-lock.json
npm install
```

3. **Check internet connection:**
```bash
npm ping
```

4. **Use different registry:**
```bash
npm config set registry https://registry.npmjs.org/
```

### Python Server Won't Start

**Problem:** `run-dev.command` fails

**Solutions:**

1. **Check Python is installed:**
```bash
python3 --version
```

2. **Port already in use:**
```bash
# Try different port
cd celstomp
python3 -m http.server 8001
```

3. **Permission denied:**
```bash
chmod +x run-dev.command
./run-dev.command
```

## Performance Issues

### Slow Drawing

**Symptoms:** Brush lags, choppy strokes

**Solutions:**

1. **Close other tabs** - Frees up memory
2. **Reduce canvas size** - 1920x1080 is usually sufficient
3. **Disable anti-aliasing** - In brush settings
4. **Use Chrome/Firefox** - Better canvas performance
5. **Check browser zoom** - Reset with `Ctrl+0`

### Timeline Playback Choppy

**Symptoms:** Animation stutters

**Solutions:**

1. **Lower frame rate** - Try 12fps instead of 24fps
2. **Reduce canvas size** - Especially if 4K
3. **Limit layers** - Merge when possible
4. **Close other apps** - Free up system resources
5. **Enable hardware acceleration** - In browser settings

### High Memory Usage

**Symptoms:** Browser crashes, out of memory errors

**Solutions:**

1. **Export and clear** - Save project, start fresh
2. **Reduce undo steps** - Config: `maxUndoSteps: 50`
3. **Lower resolution** - Work smaller, scale up later
4. **Split projects** - Scene by scene
5. **Use image sequences** - Export frames, clear project

## Drawing Issues

### Brush Not Drawing

**Symptoms:** Nothing appears when drawing

**Checklist:**

1. **Layer selected?** - Check layers panel
2. **Layer visible?** - Eye icon should be open
3. **Layer locked?** - No lock icon
4. **Brush opacity?** - Should be > 0%
5. **Brush size?** - Should be > 0px
6. **Color selected?** - Not white on white
7. **Selection active?** - Press `Esc` to clear

### Lines Look Jagged

**Symptoms:** Pixelated or stepped lines

**Solutions:**

1. **Enable anti-aliasing** - In brush settings
2. **Increase brush size** - Very small brushes look jagged
3. **Zoom to 100%** - Check at actual size
4. **Use smoother strokes** - Draw faster, less hesitation
5. **Update browser** - Older browsers have worse anti-aliasing

### Pressure Not Working

**Symptoms:** Tablet pressure ignored

**Solutions:**

1. **Check tablet drivers** - Install latest from manufacturer
2. **Enable pressure** - In brush settings
3. **Test in other apps** - Verify tablet works
4. **Try different browser** - Some handle pressure differently
5. **Check Pointer Events API** - Browser must support

### Colors Wrong

**Symptoms:** Colors don't match what you picked

**Solutions:**

1. **Check blend mode** - Multiply darkens colors
2. **Layer opacity** - Less than 100% affects appearance
3. **Onion skin** - Can tint perception, toggle with `O`
4. **Monitor calibration** - Colors vary by display
5. **Color profile** - Check browser color management

## Timeline Issues

### Frames Not Advancing

**Symptoms:** Timeline stuck on one frame

**Solutions:**

1. **Check playback** - Press `Space` to stop
2. **Modal open?** - Close any dialogs
3. **Keyboard focus** - Click on timeline first
4. **Refresh page** - Reset state

### Missing Frames

**Symptoms:** Gaps in timeline

**Solutions:**

1. **Check cel exposure** - Did you delete frames?
2. **Layer visibility** - Is layer hidden?
3. **Undo** - `Ctrl+Z` to restore
4. **Check autosave** - Might have older version

### Can't Delete Frame

**Symptoms:** Delete key not working

**Solutions:**

1. **Select frame first** - Click on timeline
2. **Check for lock** - Is frame locked?
3. **Use menu** - Edit > Delete Frame
4. **Clear selection** - `Esc`, then try again

## Export Issues

### Export Fails

**Symptoms:** Error during export

**Solutions:**

1. **Check disk space** - Need room for output
2. **Reduce size** - Try smaller resolution
3. **Fewer frames** - Export in chunks
4. **Different format** - Try PNG instead of MP4
5. **Browser console** - Check for JavaScript errors

### Export Too Large

**Symptoms:** File size enormous

**Solutions:**

1. **Lower quality** - Reduce bitrate
2. **Smaller resolution** - 1080p instead of 4K
3. **Shorter duration** - Export selection only
4. **GIF optimization** - Fewer colors, dithering
5. **MP4 settings** - Lower quality preset

### Colors Wrong in Export

**Symptoms:** Export colors don't match canvas

**Solutions:**

1. **Check transparency** - GIF has limited transparency
2. **Color space** - Some formats convert colors
3. **Browser differences** - Test in different browsers
4. **Export as PNG** - For accurate colors

## File Issues

### Can't Save Project

**Symptoms:** Save fails or freezes

**Solutions:**

1. **Check storage** - localStorage might be full
2. **Clear old projects** - Remove unused data
3. **Export instead** - Use manual export
4. **Different browser** - Some handle storage differently
5. **Disable extensions** - Ad blockers might interfere

### Project Won't Load

**Symptoms:** JSON file doesn't open

**Solutions:**

1. **Check file format** - Must be valid JSON
2. **File corrupted?** - Try backup version
3. **Version mismatch** - Created in newer version?
4. **Validate JSON** - Use online JSON validator
5. **Browser console** - Check for errors

### Autosave Not Working

**Symptoms:** Lost work after crash

**Solutions:**

1. **Check if enabled** - Edit > Preferences
2. **Storage full?** - Clear browser data
3. **Private/incognito** - Doesn't save in private mode
4. **Export regularly** - Don't rely solely on autosave

## Display Issues

### UI Elements Missing

**Symptoms:** Panels or buttons not visible

**Solutions:**

1. **Check layout mode** - Dock vs Island
2. **Toggle UI** - Press `Tab`
3. **Reset layout** - View > Reset Layout
4. **Zoom level** - Browser zoom affects UI
5. **Screen resolution** - Minimum 1280x720 recommended

### Canvas Blank

**Symptoms:** Nothing visible on canvas

**Solutions:**

1. **Check zoom** - Reset with `Ctrl+0`
2. **Pan position** - Center view with `Home`
3. **Layer visibility** - At least one layer visible?
4. **Frame content** - Current frame has drawing?
5. **Clear color** - Background same as drawing?

### Text Blurry

**Symptoms:** UI text looks fuzzy

**Solutions:**

1. **Browser zoom** - Reset to 100%
2. **System scaling** - Check display settings
3. **Font loading** - Wait for fonts to load
4. **Different browser** - Font rendering varies

## Browser-Specific Issues

### Safari Issues

**Symptoms:** Various problems in Safari

**Solutions:**

1. **Enable Develop menu** - Preferences > Advanced
2. **Disable extensions** - Test without ad blockers
3. **Update Safari** - Use latest version
4. **Clear cache** - Cmd+Option+E
5. **Try Chrome/Firefox** - If issues persist

### Chrome Issues

**Symptoms:** Problems specific to Chrome

**Solutions:**

1. **Disable hardware acceleration** - chrome://settings/system
2. **Clear cache** - Ctrl+Shift+Delete
3. **Update Chrome** - Check for updates
4. **Incognito test** - Rule out extensions
5. **Reset settings** - If problems persist

### Firefox Issues

**Symptoms:** Problems specific to Firefox

**Solutions:**

1. **Update Firefox** - Check for updates
2. **Safe mode** - Test without extensions
3. **Clear cache** - Ctrl+Shift+Delete
4. **Reset prefs** - about:config (advanced)
5. **Try Chrome** - If issues persist

## Getting Help

If these solutions don't work:

1. **Check FAQ** - [Frequently Asked Questions](./faq.md)
2. **GitHub Issues** - Search existing issues
3. **Create issue** - Use bug report template
4. **Include details:**
   - Browser and version
   - Operating system
   - Steps to reproduce
   - Screenshots
   - Console errors

### Console Errors

Open developer console to check for errors:

- **Chrome/Edge:** `Ctrl+Shift+J` (Windows) or `Cmd+Option+J` (Mac)
- **Firefox:** `Ctrl+Shift+K` (Windows) or `Cmd+Option+K` (Mac)
- **Safari:** Enable Develop menu first, then `Cmd+Option+C`

Copy any red error messages when reporting issues.

## Preventing Issues

### Best Practices

1. **Export regularly** - Don't rely on autosave alone
2. **Version your files** - v01, v02, v03...
3. **Work in chunks** - Don't make one massive project
4. **Test exports early** - Verify workflow works
5. **Keep browser updated** - Latest versions have best support

### System Maintenance

1. **Update OS** - Latest security patches
2. **Update browser** - Best compatibility
3. **Update drivers** - Especially graphics and tablet
4. **Free up disk space** - At least 10% free
5. **Restart regularly** - Clear memory leaks

## See Also

- [FAQ](./faq.md) - Common questions
- [System Requirements](../requirements.md) - Compatibility info
- [Getting Help](../community/contributing.md) - How to report issues
