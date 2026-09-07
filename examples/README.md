# threejs-product-viewer — Examples

An interactive Three.js (r160) product viewer / configurator. No build step: open the `.html` file in a modern browser and it runs.

| Example | Description |
| --- | --- |
| [`product-viewer.html`](./product-viewer.html) | An orbit-controllable product viewer with HTML hotspot markers projected onto 3D anchor points (they track the model each frame) and an animated "exploded view" toggle that offsets each sub-part. Mouse + touch friendly. |

Loads Three.js + `OrbitControls` as ES modules through an importmap (`three` from cdnjs, addons from jsdelivr). Respects `prefers-reduced-motion` (renders on interaction only) and handles resize.

Explore more on the hub: **https://aetumi.app** · product viewers → https://aetumi.app/aesport

---

## Example backlog / roadmap

# Three.js Product Viewer Example Backlog

## Planned examples

### Minimal orbit viewer

A small GLTF viewer with constrained orbit controls, responsive sizing, loading state and cleanup.

### Product variant switcher

Swap materials or product finishes without reloading the full scene. Keep UI state outside the Three.js render loop.

### Hotspot annotations

Project selected 3D positions into screen space and connect them to accessible HTML labels.

### Exploded-view sequence

Animate product parts between assembled and exploded states while preserving predictable camera framing.

### Ecommerce analytics hooks

Document interaction events such as `viewer_open`, `viewer_rotate`, `variant_change`, `hotspot_open` and `exploded_view` without coupling analytics logic to rendering.

## Quality bar

Every example should document:

- asset size and loading behavior
- mobile controls
- cleanup strategy
- reduced-motion fallback
- semantic HTML boundary
- performance considerations

## AETumi links

- https://aetumi.app/threejs/
- https://aetumi.app/3d-components/
- https://aetumi.app/interactive-websites/
