# Novo V1 — Asset Register

*Last updated: 9 June 2026*
*Maintained by: Documentation instance*
*Status: V1 wrapped up. Project paused.*

---

## Project directory structure

```
novo-v1/
├── index.html
├── audio/
│   └── ambient.mp3
├── images/
│   ├── chair.png
│   ├── curtains.png
│   ├── plant.png
│   ├── room.png
│   └── view.mp4
└── docs/
    ├── Novo Brief v13.md
    ├── Novo v1 — How It All Interacts.png
    ├── Novo_Scoping_Worksheet.md
    ├── novo-runway-prompt-log.md
    ├── novo-backlog.md
    ├── novo-v1-asset-register.md
    ├── novo-v1-build-order.md
    └── novo-v1-known-issues.md
```

---

## Active build files

Layer stack, back to front: view (video) → room (transparent windows) → curtains (animated) → plant → chair → painterly overlays.

| # | Filename | Location | What it is | Source | Status |
|---|----------|----------|-----------|--------|--------|
| 1 | index.html | /novo-v1/ | Single file: HTML structure, CSS layout, GLSL shaders (vertex + fragment), curtains.js v8.1.6 init, four painterly overlay features (vignette, paper grain, colour grade, animated boil), ambient sound, parallax. Each feature independently toggleable by commenting out its CSS/JS block. | Hand-written | In use |
| 2 | view.mp4 | /novo-v1/images/ | View layer — looping video visible through transparent windows in room layer. Autoplay, muted, looping. | Runway (video) | In use |
| 3 | room.png | /novo-v1/images/ | Room layer — walls, windows (transparent), floor, ceiling. View shows through the transparent windows. | Runway, anchored to Blender render | In use |
| 4 | curtains.png | /novo-v1/images/ | Curtain layer — sheer curtain panels on transparent background. Animated by curtains.js via WebGL plane. | Runway + background removal | In use |
| 5 | plant.png | /novo-v1/images/ | Plant layer — sits in front of curtains. Transparent background. | Runway + background removal | In use |
| 6 | chair.png | /novo-v1/images/ | Chair layer — egg chair, foreground. Transparent background. | Runway + background removal | In use |
| 7 | ambient.mp3 | /novo-v1/audio/ | Ambient soundscape. Loops continuously. Starts on first click/tap (browser autoplay restriction). | TBC | In use |

Style across all image layers: pencil linework, warm muted palette (cream, pale grey, dusty rose), watercolour wash, visible hatching, paper grain quality.

Note: Previous asset filenames (empty-room-window.png, curtain.png, chair-removebg-preview.png) have been superseded by the current set.

---

## Pipeline assets (outside the web directory)

These exist as part of the Blender→Runway→Meshy pipeline but are not served to the browser.

| # | What | Format | Source | Status |
|---|------|--------|--------|--------|
| 8 | Blender test room | .blend | Jeanette / Blender Claude | Exists — tall windows with grid framing, floor, walls, ceiling |
| 9 | Egg chair 3D model | .glb | Meshy.ai (from Runway PNG) | Exists — imported into Blender, clean geometry |
| 10 | Small table | In Blender scene | Blender | Present in scene |
| 11 | Three test renders | .png | Blender renders | Produced — different perspectives, primary angle front-on |
| 12 | Runway prompt log | Text | novo-runway-prompt-log.md | Tested and working — method, style constants, every prompt with results/learnings, pipeline reference |

---

## Documentation files

| # | Filename | Location | What it is | Status |
|---|----------|----------|-----------|--------|
| 13 | Novo Brief v13.md | /novo-v1/docs/ | Design brief. Living document. Authoritative source for what Novo IS. | Current |
| 14 | Novo v1 — How It All Interacts.png | /novo-v1/docs/ | V1 interaction diagram. Note: shows four layers (view / room / curtain / shader); proven build uses five image/video layers (view / room / curtain / plant / chair) plus shader overlays. Also includes seasonal view swap, which is post-V1. | Current |
| 15 | Novo_Scoping_Worksheet.md | /novo-v1/docs/ | Scoping worksheet. | Unknown — Jeanette to confirm |
| 16 | novo-runway-prompt-log.md | /novo-v1/docs/ | Runway prompt log. Method, style constants, every prompt with results/learnings, pipeline reference, future considerations. Supersedes Novo_v1_Runway_Prompts.md. | Current |
| 17 | novo-v1-build-order.md | /novo-v1/docs/ | Project structure and build order. | Current |
| 18 | novo-v1-asset-register.md | /novo-v1/docs/ | This file. | Current |
| 19 | novo-v1-known-issues.md | /novo-v1/docs/ | Known issues, risks, and deferred items. | Current |
| 20 | novo-backlog.md | /novo-v1/docs/ | Backlog — active tasks and post-V1 ideas. | Current |

---

## Tools in the pipeline

| Tool | Role | Notes |
|------|------|-------|
| Blender | Canonical geometry — perspective, proportions, spatial relationships. Composition authority. | Test room exists. |
| Runway | Pencil-drawn illustration style. Takes Blender render as image input + text prompts. Aesthetic authority. | Subscription active. Most prone to drift. |
| Meshy.ai | 2D image → 3D .glb model. Bridges the modelling gap for complex objects. | Tested with egg chair — accurate, clean import. |
| remove.bg | Background removal for layer separation. | Used for chair, curtain, plant. |
| curtains.js v8.1.6 | WebGL plane animation. Drives curtain motion via vertex displacement shader. | Loaded from CDN. |

---

## Register rules

- Every file that is part of the project gets a row. No exceptions.
- **Source** = where the file came from (Runway, remove.bg, Blender, Meshy.ai, hand-written, library, etc.)
- **Status** = one of: **in use**, **archived**, **superseded by [filename]**, **draft**.
- When a file is replaced, the old file stays in the register marked superseded. Nothing disappears silently.
- Version numbers go in filenames when a file has been through more than one iteration. The register tracks which version is current.
