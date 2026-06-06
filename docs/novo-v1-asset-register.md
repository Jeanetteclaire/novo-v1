# Novo V1 — Asset Register

*Last updated: 6 June 2026*
*Maintained by: Documentation instance*

---

## Project directory structure

```
novo-v1/
├── index.html
├── images/
│   ├── chair-removebg-preview.png
│   ├── curtain.png
│   ├── empty-room-window.png
│   └── room.png
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

Layer stack, back to front: room → curtain (animated) → chair → shader/grain (not yet built).

| # | Filename | Location | What it is | Source | Status |
|---|----------|----------|-----------|--------|--------|
| 1 | index.html | /novo-v1/ | Single file: HTML structure, CSS layout, GLSL shaders (vertex + fragment), curtains.js v8.1.6 initialisation. | Hand-written | In use |
| 2 | empty-room-window.png | /novo-v1/images/ | Back layer — empty loft with tall windows, wooden floor. View baked in (not yet separated). Pencil-drawn style. | Runway, anchored to Blender render | In use |
| 3 | curtain.png | /novo-v1/images/ | Middle layer — three sheer curtain panels on transparent background. Animated by curtains.js via WebGL plane with sine-wave vertex displacement. | Runway + background removal | In use |
| 4 | chair-removebg-preview.png | /novo-v1/images/ | Front layer — egg chair, background removed. | Runway + remove.bg | In use |
| 5 | room.png | /novo-v1/images/ | Room variant. | Runway | In directory — may be earlier version. Status TBC. |

Style across all layers: pencil linework, warm muted palette (cream, pale grey, dusty rose), watercolour wash, visible hatching, paper grain quality.

Note: Image filenames in index.html may not match current asset filenames (ISSUE-12). Check and update references when replacing assets.

---

## Pipeline assets (outside the web directory)

These exist as part of the Blender→Runway→Meshy pipeline but are not served to the browser.

| # | What | Format | Source | Status |
|---|------|--------|--------|--------|
| 6 | Blender test room | .blend | Jeanette / Blender Claude | Exists — tall windows with grid framing, floor, walls, ceiling |
| 7 | Egg chair 3D model | .glb | Meshy.ai (from Runway PNG) | Exists — imported into Blender, clean geometry |
| 8 | Small table | In Blender scene | Blender | Present in scene |
| 9 | Three test renders | .png | Blender renders | Produced — different perspectives, primary angle front-on |
| 10 | Runway prompt log | Text | novo-runway-prompt-log.md | Tested and working — method, style constants, every prompt with results/learnings, pipeline reference |

---

## Documentation files

| # | Filename | Location | What it is | Status |
|---|----------|----------|-----------|--------|
| 11 | Novo Brief v13.md | /novo-v1/docs/ | Design brief. Living document. Authoritative source for what Novo IS. | Current |
| 12 | Novo v1 — How It All Interacts.png | /novo-v1/docs/ | V1 interaction diagram. Note: shows four layers (view / room / curtain / shader); proven build uses three image layers (room / curtain / chair) plus future shader. Also includes seasonal view swap and sound, both post-V1. | Current |
| 13 | Novo_Scoping_Worksheet.md | /novo-v1/docs/ | Scoping worksheet. | Unknown — Jeanette to confirm |
| 14 | novo-runway-prompt-log.md | /novo-v1/docs/ | Runway prompt log. Method, style constants, every prompt with results/learnings, pipeline reference, future considerations. Supersedes Novo_v1_Runway_Prompts.md. | Current |
| 15 | novo-v1-build-order.md | /novo-v1/docs/ | Project structure and build order. | Current |
| 16 | novo-v1-asset-register.md | /novo-v1/docs/ | This file. | Current |
| 17 | novo-v1-known-issues.md | /novo-v1/docs/ | Known issues, risks, and deferred items. | Current |
| 18 | novo-backlog.md | /novo-v1/docs/ | Backlog — active tasks and post-V1 ideas. | Current |

---

## Files not yet created (expected for V1)

| What | Phase/Step | Notes |
|------|-----------|-------|
| Refined layer images | Phase 0b.1 | Tighter Blender-anchored layers if current set needs better alignment. Will supersede current images/. |
| CSS file (if separated from index.html) | Phase 1 | May stay inline. TBD. |
| JS file (if separated from index.html) | Phase 1 | May stay inline. TBD. |
| Shader/grain code (if separate file) | Phase 1.3 | The top layer. CSS filters and/or WebGL shader pass. May be inline. TBD. |

---

## Tools in the pipeline

| Tool | Role | Notes |
|------|------|-------|
| Blender | Canonical geometry — perspective, proportions, spatial relationships. Composition authority. | Test room exists. |
| Runway | Pencil-drawn illustration style. Takes Blender render as image input + text prompts. Aesthetic authority. | Subscription active. Most prone to drift. |
| Meshy.ai | 2D image → 3D .glb model. Bridges the modelling gap for complex objects. | Tested with egg chair — accurate, clean import. |
| remove.bg | Background removal for layer separation. | Used for chair and curtain. |
| curtains.js v8.1.6 | WebGL plane animation. Drives curtain motion via vertex displacement shader. | Loaded from CDN. |

---

## Register rules

- Every file that is part of the project gets a row. No exceptions.
- **Source** = where the file came from (Runway, remove.bg, Blender, Meshy.ai, hand-written, library, etc.)
- **Status** = one of: **in use**, **archived**, **superseded by [filename]**, **draft**.
- When a file is replaced, the old file stays in the register marked superseded. Nothing disappears silently.
- Version numbers go in filenames when a file has been through more than one iteration. The register tracks which version is current.
