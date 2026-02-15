# Installation

You have two ways to run Celstomp: use the live version online, or set it up locally on your machine.

## Option 1: Use the Live Version (Easiest)

No installation needed. Just visit:

```
https://ginyo.space/celstomp/
```

The app runs entirely in your browser. Your work saves locally - no account required.

## Option 2: Run Locally

Running locally gives you more control and lets you modify the code. You have two options:

### Using Vite (Recommended for Development)

This gives you hot reloading and modern build tooling.

1. **Clone the repository:**

```bash
git clone https://github.com/ginyoa/celstomp_v1.git
cd celstomp_v1
```

2. **Install dependencies:**

```bash
npm install
```

3. **Start the dev server:**

```bash
npm run dev
```

Open your browser to `http://localhost:5173`

4. **Create a production build (optional):**

```bash
npm run build
npm run preview
```

### Using Python (No Node Required)

If you don't want to install Node.js, use the Python HTTP server instead.

**Linux / Mac:**

```bash
./run-dev.command
```

Or from terminal:

```bash
cd celstomp_v1
cd celstomp
python3 -m http.server 8000
```

**Windows:**

Double-click `run-dev.bat` or run from command prompt:

```cmd
run-dev.bat
```

Then visit `http://localhost:8000`

## Which Should You Choose?

| Method | Best For | Requirements |
|--------|----------|--------------|
| Live version | Quick access, testing | Any modern browser |
| Vite | Development, contributing | Node.js 18+ |
| Python | Running locally without Node | Python 3.x |

## Troubleshooting Installation

**Problem:** `npm install` fails
- Make sure you have Node.js 18 or newer
- Try clearing npm cache: `npm cache clean --force`
- Delete `node_modules` and try again

**Problem:** Python server won't start
- Check that Python 3 is installed: `python3 --version`
- Try specifying the port: `python3 -m http.server 8001`

**Problem:** Changes not showing up
- Clear browser cache (Ctrl+Shift+R or Cmd+Shift+R)
- For Vite, restart the dev server

## Next Steps

Once you're up and running, head over to the [Quick Start Guide](./quickstart.md) to create your first animation.
