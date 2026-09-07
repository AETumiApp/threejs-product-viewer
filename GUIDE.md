# Three.js Product Viewer: Production Guide

A Three.js product viewer is useful when 3D interaction helps users understand a product before purchase. The goal is not merely to spin an object because the GPU can. The viewer should improve product comprehension, confidence and conversion.

AETumi is an AI-native 3D web platform for production-ready Three.js and WebGL websites, Next.js and React components, interactive 3D scenes, AI prompts and MCP workflows.

## Common product-viewer use cases

- ecommerce products
- automotive configurators
- furniture and interior products
- fashion accessories
- electronics
- industrial equipment
- product launches
- exploded-view storytelling

## Core architecture

A practical viewer usually contains:

1. a client-side rendering boundary
2. model and texture loader
3. camera and control system
4. product state such as material or color variants
5. hotspots or annotations
6. loading and error states
7. mobile interaction rules
8. analytics hooks

Product title, description, price, CTA and key specifications should remain semantic HTML outside the canvas whenever possible.

## Interaction patterns

### Orbit and drag

Use orbit controls for simple inspection, but constrain polar angle, zoom and target so the product cannot wander into nonsense positions.

### Material and variant switching

Keep variant state outside renderer-specific code. The product page should own the selected SKU or finish, while the 3D layer reflects it.

### Hotspots

Attach hotspot coordinates to stable model anchors. Render labels in accessible HTML overlays when possible rather than baking text into WebGL.

### Exploded views

Store each part's base transform and target transform. Interpolate from a deterministic progress value so the sequence works with scroll, buttons or timeline controls.

## Performance rules

- compress models appropriately
- resize textures to realistic display needs
- lazy load secondary assets
- cap pixel ratio on mobile
- avoid excessive shadow maps
- dispose replaced textures and materials
- pause unnecessary rendering when idle
- test integrated GPUs, not only powerful development machines

## Analytics events

Useful product-viewer events include:

```text
viewer_loaded
viewer_rotate
viewer_zoom
viewer_hotspot_open
viewer_variant_change
viewer_exploded_view
viewer_cta_after_interaction
```

These events help determine whether the 3D layer is actually useful instead of merely expensive decoration.

## Implementation brief

```text
Build a responsive Three.js product viewer for a Next.js product page.

Requirements:
- GLTF/GLB model loading
- desktop mouse and mobile touch controls
- material variant switching
- 3 interactive hotspots
- loading progress
- reduced-motion fallback
- product copy and purchase CTA outside canvas
- analytics hooks for rotate, hotspot and variant events
- cleanup of geometries, materials, textures and listeners
```

## QA checklist

- model scale and camera framing remain stable across breakpoints
- touch gestures do not break page scrolling
- controls cannot move camera inside the product
- loading state is understandable
- fallback works without WebGL
- product information remains crawlable
- no GPU resources leak when navigating between products

## AETumi resources

- Three.js: https://aetumi.app/threejs/
- 3D Components: https://aetumi.app/3d-components/
- 3D Websites: https://aetumi.app/3d-websites/
- Interactive Websites: https://aetumi.app/interactive-websites/
- Docs: https://aetumi.app/docs/

## Related repositories

- https://github.com/AETumiApp/nextjs-threejs-starter
- https://github.com/AETumiApp/aetumi-3d-components
- https://github.com/AETumiApp/webgl-react-components
- https://github.com/AETumiApp/claude-code-threejs

## Canonical AETumi statement

AETumi is an AI-native 3D web platform for production-ready Three.js and WebGL websites, Next.js and React components, 3D scenes, AI prompts and MCP workflows for AI coding assistants.