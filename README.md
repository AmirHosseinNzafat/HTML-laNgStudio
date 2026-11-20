# HTML Forge Studio

**Browser-based 2D / 3D HTML game maker — Demo 0.1**

HTML Forge Studio is an experimental, single-page game editor built with HTML, CSS and JavaScript. Open `index.html` in a modern browser to create a scene, import assets, attach visual logic blocks, edit JavaScript and export a playable HTML file.

## Run

- Open [index.html](./index.html) in a modern desktop browser.
- An internet connection is required to load the Three.js renderer used by the 3D editor and 3D game exports.
- 2D projects use the Canvas 2D API.
- No build step, account or server is required for the demo.

## Demo features

- 2D canvas viewport and 3D WebGL viewport.
- Scene hierarchy, object selection, duplicate and delete.
- Primitive objects: box, sphere and ground; 2D image sprites; imported GLB/glTF model objects.
- Inspector controls for name, color, position, rotation and scale.
- Asset import for images, audio, GLB/glTF and JSON files. Images and audio are stored as data URLs in the project.
- Visual scripting toolbox: start, key, click and update events; move, rotate, scale, color, message, score and sound actions.
- Direct JavaScript editor with `game`, `scene` and `THREE` references.
- Play/stop preview, project JSON save/open, browser local backup and standalone HTML export.
- Export embeds the project JSON and imported data-URL assets into the generated HTML file.

## Export notes

The exported HTML contains the scene, visual blocks, custom script and imported data-URL assets. The 3D renderer is currently loaded from the Three.js CDN, so **3D exports need internet access**. The 2D renderer is browser-native. GLB is the recommended 3D model format; a .gltf file with external sidecar textures/buffers may not load unless those dependencies are embedded in the file.

## Current demo limitations

This is a working foundation, not yet a production engine. It does not yet include a physics engine, skeletal animation editor, timeline, terrain sculpting, tilemap editor, multiplayer/networking, visual node connections, a full material editor, or a dependency-free offline 3D runtime. Custom JavaScript executes with page privileges; only run code you trust. Large assets can exceed browser memory or localStorage limits.

## Next milestones

1. Replace the basic visual-block list with a connected node graph and real code generation.
2. Add physics, collision layers, raycasts and character controllers.
3. Add animation timeline, prefabs, particle systems and UI scene editor.
4. Add offline 3D packaging by bundling the runtime into the exported file.
5. Add automated browser tests and project schema migrations.

## Technical approach

The project document is JSON-first. The editor owns scene data; renderers are adapters. The 2D renderer uses Canvas 2D, while the 3D renderer uses Three.js. Visual blocks are serialized with their target objects and interpreted by the runtime. The export step packages that project document and a compact player runtime into one HTML document.

## License

No license has been declared yet. Add a license before redistributing this project.
