# NotePalace

A browser-based **3D memory palace** for spatial note-taking and mind-mapping, built with [Three.js](https://threejs.org/).

## What It Does

NotePalace lets you organize notes spatially in a 3D world. It's based on the [method of loci](https://en.wikipedia.org/wiki/Method_of_loci) — a mnemonic technique where you associate information with physical locations.

- **Boxes** — Each note lives inside a colored 3D box placed on a circle.  
- **Sub-circles** — Click the glowing path between any two boxes to create a nested circle, drilling deeper into related ideas.  
- **Breadcrumb navigation** — A trail at the top lets you jump back to any parent level.  
- **Persistence** — Everything saves automatically to your browser's `localStorage`.

## How to Run

No installation, no build tools, no server required. Just open `index.html` in a modern browser:

```bash
# Option 1: Open directly
open index.html

# Option 2: Serve with a static server (Python 3)
python3 -m http.server 8080
# Then visit http://localhost:8080
```

An internet connection is needed the first time to load Three.js from CDN.

## How to Use

### Adding Notes

1. Click any numbered box to open the note panel.  
2. Type your note in the textarea.  
3. Click **Save** (or press `Ctrl+Enter` / `Cmd+Enter`).  
4. Press `Escape` to close the panel.

### Creating Sub-circles

1. Click the glowing curved path between two adjacent boxes.  
2. A new, smaller circle appears with its own set of boxes.  
3. This creates a hierarchical relationship — the sub-circle is "between" those two parent boxes.

### Navigation

- **Orbit** — Click and drag to rotate the camera.  
- **Zoom** — Scroll or pinch.  
- **Pan** — Right-click and drag.  
- **Breadcrumbs** — Click any ancestor label at the top to jump back up the hierarchy.

### Deleting

Open a box's note panel and click **Delete**. The box and all its sub-circles are removed.

## Resetting Data

All data is stored in `localStorage` under the key `memoryPalace`. To wipe everything, open your browser's DevTools and run:

```js
localStorage.removeItem('memoryPalace');
```

Then refresh the page.

## Tech Stack

- **Three.js 0.160** — 3D rendering
- **OrbitControls** — Camera controls
- **CSS2DRenderer** — HTML labels in 3D space
- **localStorage** — Data persistence
- No frameworks, no bundlers, no build step.

## Project Structure

```
NotePalace/
└── index.html    # The entire application (~650 lines)
```

Everything — HTML, CSS, and JavaScript — is in a single file.
