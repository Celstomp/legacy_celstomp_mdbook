# Frequently Asked Questions

Common questions about Celstomp answered.

## General Questions

### What is Celstomp?

Celstomp is a free, browser-based 2D animation tool. It lets you create frame-by-frame animations without installing software.

### Is Celstomp really free?

Yes. Celstomp is open source under the GPL v3 license. Use it, modify it, share it - all free.

### Do I need to create an account?

No. Celstomp works without accounts or logins. Your work saves locally to your browser.

### Does it work offline?

Yes, after the first load. Celstomp is a Progressive Web App (PWA) that works offline.

### What browsers are supported?

Chrome, Firefox, Safari, and Edge - all modern versions. Chrome and Firefox work best.

## Getting Started

### How do I start?

1. Go to https://ginyo.space/celstomp/
2. The built-in tutorial will guide you
3. Or read the [Quick Start Guide](../guides/quickstart.md)

### Is there a tutorial?

Yes. Press `?` in the app to see the built-in tutorial. You can also read the [Tutorial Guide](../guides/tutorial.md).

### Can I use Celstomp on mobile?

Yes, but it's optimized for desktop. Tablets work better than phones. Use a stylus for best results.

### Do I need a drawing tablet?

No, but it helps. You can draw with a mouse, but a tablet with pressure sensitivity gives better results.

## Technical Questions

### Where is my work saved?

Work saves to your browser's localStorage and can be exported as JSON files. We recommend exporting regularly as backup.

### How much storage do I have?

Typically 5-10 MB per browser. For larger projects, export to JSON files regularly.

### Can I recover deleted work?

If you haven't closed the browser, try `Ctrl+Z` to undo. Otherwise, use your exported backup files.

### Why is it running slowly?

Try:
- Closing other browser tabs
- Reducing canvas size
- Lowering frame count
- Using Chrome or Firefox
- Disabling onion skin temporarily

### Does Celstomp collect my data?

No. Celstomp is client-side only. Nothing uploads to servers. See our [Security Policy](../community/security.md).

## Features

### What export formats are available?

- **MP4** - Video for social media
- **GIF** - For web and messaging
- **Image Sequence** - PNGs for advanced editing
- **JSON** - Project files

See [Export Formats](../guides/export-formats.md) for details.

### Can I import images?

Yes. Import PNG, JPG, and GIF files as backgrounds or reference.

### Is there audio support?

Not currently. You can add audio in post-production using video editors.

### Can I collaborate with others?

Not in real-time, but you can share project JSON files with collaborators.

### Are there keyboard shortcuts?

Yes. Press `?` in the app to see them all. See [Keyboard Shortcuts](../guides/shortcuts.md).

## Workflow Questions

### What's the best way to learn animation?

Start with the bouncing ball exercise:
1. Draw circle at top
2. Draw at bottom
3. Add inbetweens
4. Test playback

Then try the [Animation Workflow](../guides/animation-workflow.md) guide.

### How many frames per second should I use?

- **12 fps** - Classic animation, smaller files
- **24 fps** - Standard film rate
- **30 fps** - Video standard
- **60 fps** - Smooth motion

### What's the difference between layers?

- **LINE** - Outlines and sketches
- **SHADE** - Shadows and depth
- **COLOR** - Flat colors
- **FILL** - Fill tool output
- **PAPER** - Background

See [Layers System](../concepts/layers.md).

### How do I copy and paste?

- **Selection:** Use Lasso or Rectangle tool
- **Copy:** `Ctrl+C`
- **Paste:** `Ctrl+V`
- **Duplicate:** `Ctrl+D`

### Can I hold a drawing for multiple frames?

Yes. In the timeline, drag the right edge of a cel to extend its exposure.

## Troubleshooting

### I can't see my drawing

Check:
- Are you on the right layer?
- Is the layer visible (eye icon)?
- Is layer opacity above 0%?
- Is onion skin hiding it?
- Did you draw outside canvas bounds?

### The brush isn't working

Check:
- Is a selection active? (Press `Esc` to clear)
- Is the layer locked?
- Is brush size set to 0?
- Is brush opacity at 0%?

### Export fails

Try:
- Smaller canvas size
- Fewer frames
- Lower quality setting
- Different browser
- More disk space

### Timeline won't play

Check:
- Is loop enabled? (`L` key)
- Are there frames to play?
- Is another dialog open?
- Try refreshing the page

### Colors look wrong

Check:
- Layer blend mode (Multiply darkens)
- Layer opacity
- Onion skin tint
- Browser color profile

## File Questions

### How do I save my work?

Press `Ctrl+S` or go to File > Save Project. This exports a JSON file you can reload later.

### Can I open projects in other software?

Not directly. Celstomp uses its own format. Export as image sequence to use in other apps.

### Are project files backward compatible?

Generally yes, but always back up before updating.

### How do I backup my work?

1. Export project JSON regularly
2. Store in cloud storage (Google Drive, Dropbox)
3. Version your files (v01, v02, etc.)

## Comparison Questions

### How is Celstomp different from [other software]?

**vs. Krita:**
- Celstomp: Web-based, simpler, focused on animation
- Krita: Desktop, more features, painting + animation

**vs. OpenToonz:**
- Celstomp: Web-based, easier to learn, modern UI
- OpenToonz: Desktop, professional features, complex

**vs. Procreate:**
- Celstomp: Free, web-based, frame-by-frame
- Procreate: iPad only, paid, raster painting

**vs. FlipaClip:**
- Celstomp: Desktop focused, more export options
- FlipaClip: Mobile focused, simpler

### Is Celstomp for beginners?

Yes! The built-in tutorial and simple interface make it great for learning. But it has features for experienced animators too.

## Contribution Questions

### How can I contribute?

- Report bugs
- Suggest features
- Improve documentation
- Submit code

See [Contributing](../development/contributing.md).

### Can I donate?

The project doesn't accept donations currently. Contributing your time is the best support.

### How do I report a bug?

1. Check if it's already reported
2. Use the bug report template
3. Include steps to reproduce
4. Add screenshots if helpful

See [Security](../community/security.md) for security issues.

## Future Questions

### What's planned for future versions?

Check GitHub issues and discussions for:
- Planned features
- Roadmap
- Community suggestions

### Will Celstomp always be free?

Yes. It's open source under GPL v3, which ensures it remains free.

### Can I use Celstomp commercially?

Yes. The GPL v3 license allows commercial use. Your animations are yours.

## Still Have Questions?

- Read the [full documentation](../introduction.md)
- Check [Troubleshooting](./troubleshooting.md)
- Open an issue on GitHub
- Try the built-in tutorial (press `?`)

## Quick Reference

| Question | Answer |
|----------|--------|
| Price? | Free |
| Offline? | Yes |
| Account? | No |
| Mobile? | Yes (but desktop recommended) |
| Tablet support? | Yes |
| File size? | 5-20 MB typical |
| Export formats? | MP4, GIF, PNG, JSON |
| License? | GPL v3 |
