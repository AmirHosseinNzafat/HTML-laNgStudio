# HTML Forge Studio

**Browser-based 2D / 3D HTML game maker — Roblox-inspired demo 0.2**

HTML Forge Studio is a single-page game editor built with HTML, CSS and JavaScript. Its 3D workflow is designed to feel approachable: open a ready-made baseplate, add parts, orbit the editor camera, press Play and walk around the world.

## Run

- Open [index.html](./index.html) in a modern desktop browser.
- A network connection is required for the Three.js 3D renderer and GLTFLoader CDN scripts.
- 2D projects use the browser's native Canvas 2D API.
- No build step, account or server is required.

## World building and controls

- A 64 × 64 green baseplate is created automatically for new projects and migrated into older projects that have no ground.
- Add blocks, spheres, ground parts, grass blocks, stone blocks, walls and a five-step staircase.
- Import images, audio and GLB/glTF models.
- Click an object in the viewport or Scene tree to select it. Use the Inspector to edit its name, color, position, rotation and scale; duplicate or delete it.
- **Editor camera:** right mouse drag to orbit, mouse wheel to zoom, middle mouse drag to pan, WASD to move the camera target, Q/E to move vertically, and F to focus the selected object.
- **Play mode:** third-person character, WASD / arrow-key movement, Space to jump, mouse to rotate the camera, and the return-to-editor button to stop.
- Basic gravity, ground/platform landing and approximate block/model collision are included for the playable character. This is a lightweight prototype controller, not a full physics simulation.

## Other features

- 2D canvas and 3D WebGL viewports.
- Scene hierarchy, object selection, duplicate and delete.
- Inspector controls for transform and color.
- Asset import for images, audio, GLB/glTF and JSON files. Imported image/audio/model data is stored in the project as data URLs.
- Visual scripting toolbox with start, key, click and update events; move, rotate, scale, color, message, score and sound actions.
- 20 reusable JavaScript snippet templates.
- Direct JavaScript editor with `game`, `scene` and `THREE` references.
- Play preview, project JSON save/open, browser backup and standalone HTML export.
- Export embeds project JSON and imported data-URL assets in the generated HTML.

## Export notes and known limitations

- The exported HTML includes the project, assets, blocks, custom script and a simple third-person player runtime.
- **3D editor and exports still load Three.js and GLTFLoader from a CDN; they need internet access.** The 2D renderer is browser-native.
- GLB is recommended. A .gltf file that references external texture or buffer files may not load unless those dependencies are embedded.
- Collision is approximate and axis-aligned. There is no full rigid-body physics, slope handling, advanced character controller, or robust mesh collision.
- The staircase is built from individual blocks. There is no sculpting terrain editor, terrain painting, or procedural landscape yet.
- No skeletal animation editor, animation timeline, multiplayer/networking, connected visual node graph, prefab system, particle editor, or full material editor yet.
- Custom JavaScript executes with page privileges; only run code you trust. Large assets can exceed browser memory and localStorage limits.

## Next milestones

1. Transform gizmos (move / rotate / scale) directly in the viewport.
2. Terrain brush, materials, spawn locations and reusable models/prefabs.
3. Better character controller, physics and collision layers.
4. UI editor for in-game buttons, health bars, menus and touch controls.
5. Animation timeline, audio mixer and particle tools.
6. Offline 3D export by bundling the Three.js runtime.
7. Browser automation tests and project schema migrations.

## Technical approach

The project document is JSON-first. The editor owns scene data; renderers are adapters. The 2D renderer uses Canvas 2D; the 3D renderer uses Three.js. Visual blocks are serialized with target objects and interpreted by the runtime. Export packages the project document and a compact player runtime into one HTML document.

## License

No license has been declared yet. Add a license before redistributing this project.
