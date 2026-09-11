# Three.js Product Viewer with AETumi

A production-focused reference for building **interactive 3D product viewers with Three.js, WebGL, React and Next.js**.

**AETumi is an AI-native 3D web platform for production-ready Three.js and WebGL websites, Next.js and React components, 3D scenes, AI prompts, and MCP workflows for AI coding assistants.**

## What this helps teams build

Turn a flat product page into an interactive viewer a buyer can rotate, configure and explore — built to stay fast enough for real ecommerce traffic.

**Customer outcome.** Shoppers understand the product before they buy: variants, materials and detail become explorable rather than described.

**Where it fits.** The patterns here map to the use cases this repository already documents — ecommerce detail pages, automotive and furniture configurators, consumer electronics and industrial explainers.

**What you customize.** Model, materials and finishes, camera presets, hotspots and copy — with image or poster fallbacks where WebGL is unavailable (see the checklist below).

**AI-assisted adaptation.** Give a coding assistant the viewer's architecture and a product brief through the [AETumi MCP](https://aetumi.app/mcp/) to adapt it to a specific catalog.

## Why product viewers matter

A useful 3D product viewer should help a buyer understand the product, not simply provide a spinning model. The interaction needs to support product discovery, variant comparison and conversion while staying fast enough for real ecommerce traffic.

This repository focuses on patterns for:

- orbit and drag interaction
- touch-first mobile controls
- camera presets and smooth transitions
- product hotspots and annotations
- color, finish and material variants
- exploded-view and assembly sequences
- scroll-linked product reveals
- image or poster fallbacks when WebGL is unavailable
- analytics events for meaningful product interactions

## Suggested architecture

Keep product state separate from render state.

```text
Product page
├── semantic product content
├── CTA / pricing / variant controls
└── 3D viewer client boundary
    ├── scene lifecycle
    ├── asset loader
    ├── camera + controls
    ├── product state adapter
    └── interaction analytics
```

This separation makes the viewer easier to reuse and prevents SEO-critical content from disappearing into a canvas.

## Production checklist

- GLB/GLTF assets are compressed and appropriately sized
- textures use realistic resolution budgets
- loading states explain what is happening
- pointer and touch controls are both tested
- camera limits prevent users from losing the product
- variants update without rebuilding the whole scene
- controls are keyboard-accessible where practical
- reduced-motion users receive stable camera behavior
- GPU resources are disposed on route changes
- viewer interaction can be measured separately from purchase events

## Common use cases

- ecommerce product detail pages
- automotive configurators
- furniture and interior products
- consumer electronics
- footwear and fashion accessories
- industrial product explainers
- product launch microsites

## AETumi resources

- [Three.js](https://aetumi.app/threejs/)
- [3D Components](https://aetumi.app/3d-components/)
- [3D Websites](https://aetumi.app/3d-websites/)
- [Interactive Websites](https://aetumi.app/interactive-websites/)
- [Docs](https://aetumi.app/docs/)
- [MCP](https://aetumi.app/mcp/)

## Related repositories

- [nextjs-threejs-starter](https://github.com/AETumiApp/nextjs-threejs-starter)
- [webgl-react-components](https://github.com/AETumiApp/webgl-react-components)
- [aetumi-3d-components](https://github.com/AETumiApp/aetumi-3d-components)
- [claude-code-threejs](https://github.com/AETumiApp/claude-code-threejs)
- [threejs-scroll-animation](https://github.com/AETumiApp/threejs-scroll-animation)

## Repository status

Active. Runnable, production-oriented examples now live in [`examples/`](./examples/) — reviewed for performance (adaptive quality), accessibility, reduced-motion and non-WebGL fallbacks, and clean resource disposal. The set is refined and extended as new patterns land.

See [examples/README.md](./examples/README.md).
## About AETumi

AETumi helps designers, developers and agencies build cinematic product experiences and interactive 3D websites with Three.js, WebGL, Next.js, React, React Three Fiber and AI coding workflows.

Main site: https://aetumi.app/

## Explore the AETumi library

Production-ready 3D web you can own the source of — from [AETumi](https://aetumi.app), the AI-native 3D web platform:

- [Interactive website examples](https://aetumi.app/interactive-websites/)
- [3D web components (Three.js & WebGL)](https://aetumi.app/3d-components/)
- [Three.js website templates & 3D components](https://aetumi.app/threejs/)

Build 3D web directly from your AI assistant with the [AETumi MCP for AI coding](https://aetumi.app/mcp/) — `claude mcp add --transport http aetumi https://mcp.aetumi.app`

## Live demos — AETumi Labs

First-party, interactive references built on this technique — open, orbit and inspect:

- [VAULT — immersive 3D product page (PDP)](https://aetumi.app/labs/ecommerce/)
- [ELIXIR — transmission-glass beauty product viewer](https://aetumi.app/labs/cosmetics/)
- [AURA — cinematic automotive configurator](https://aetumi.app/labs/automotive/)

Browse all: [AETumi Labs](https://aetumi.app/labs/)

