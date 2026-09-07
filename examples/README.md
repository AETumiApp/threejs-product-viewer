# threejs-product-viewer — Examples

An interactive, **production-grade** Three.js (r160) product viewer / configurator. No build step: open the `.html` file in a modern browser and it runs.

| Example | Description |
| --- | --- |
| [`product-viewer.html`](./product-viewer.html) | An orbit-controllable product viewer with occlusion-aware HTML hotspot markers projected onto 3D anchor points (they track the model each frame and hide when they rotate behind it) and an animated "exploded view" toggle. Mouse + touch friendly. |

### Expert / production features (every example)

- **Capability detection + graceful fallback** — probes WebGL2 → WebGL → none. With no WebGL context it paints a tasteful CSS gradient poster instead of a blank canvas; low-power devices start at reduced quality.
- **On-demand + adaptive performance** — DPR capped at 2; the loop renders only when something changes (orbit inertia, an exploded transition, resize) and **parks itself** when the scene is at rest, offscreen, or the tab is hidden — minimal battery. A rolling FPS average steps DPR down below 50 fps and back up above 58 fps with hysteresis.
- **Strict cleanup** — one `dispose()` releases `OrbitControls`, all geometries/materials, hotspot DOM, listeners and the renderer, on `pagehide`.
- **Accessibility** — the canvas is `role="img"` with an `aria-label`; the toolbar and hotspots are native `<button>`s (keyboard-reachable, focus rings), and hotspot labels reveal on focus as well as hover; `prefers-reduced-motion` disables the idle spin and renders on interaction only.
- **Premium look** — ACES Filmic tone mapping, hemisphere + directional key lighting, glowing translucent shell rings.

Three.js r160 + `OrbitControls` are loaded as ES modules through an importmap on **jsDelivr only** (`three` + `three/addons/`).

Explore more on the hub: **https://aetumi.app** · product viewers → https://aetumi.app/aesport
