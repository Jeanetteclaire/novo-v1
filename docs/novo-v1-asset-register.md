# Novo V1 — Asset Register

*Last updated: 5 June 2026*
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
    ├── Novo_v1_Runway_Prompts.md
    ├── novo-backlog.md
    ├── novo-v1-asset-register.md
    ├── novo-v1-build-order.md
    └── novo-v1-known-issues.md
```

---

## Active build files

These are the files that make V1 run. The proven layer architecture is: room behind, curtain animated in the middle, chair in front.

| # | Filename | Location | What it is | Source | Status |
|---|----------|----------|-----------|--------|--------|
| 1 | index.html | /novo-v1/ | Main page. Loads three image layers with z-ordering, runs curtain animation via curtains.js. Updated to support three-layer architecture. | Hand-written | In use |
| 2 | room.png | /novo-v1/images/ | Room interior — back layer. | Runway | In use — will be replaced by Blender-anchored version |
| 3 | curtain.png | /novo-v1/images/ | Transparent curtain — middle layer, animated. | Runway + remove.bg | In use — will be replaced by Blender-anchored version |
| 4 | chair-removebg-preview.png | /novo-v1/images/ | Chair — front layer. Background removed. | Runway + remove.bg | In use — will be replaced by Blender-anchored version |
| 5 | empty-room-window.png | /novo-v1/images/ | Empty room/window variant. | Runway | In directory — status TBC |

Note: These images were generated separately in Runway and do not share exact perspective. They prove the architecture works but will be replaced by layers rendered from the same Blender composition (Phase 0, Blender pipeline). Previous file view.png has been removed.

---

## Documentation files

| # | Filename | Location | What it is | Status |
|---|----------|----------|-----------|--------|
| 6 | Novo Brief v13.md | /novo-v1/docs/ | Current design brief. Living document. | Current |
| 7 | Novo v1 — How It All Interacts.png | /novo-v1/docs/ | V1 interaction diagram. Reference architecture. Note: diagram shows four layers (view / room / curtain / shader-grade); the proven build uses three image layers (room / curtain / chair) plus a future shader layer. | Current |
| 8 | Novo_Scoping_Worksheet.md | /novo-v1/docs/ | Scoping worksheet. | Unknown — Jeanette to confirm if still active |
| 9 | Novo_v1_Runway_Prompts.md | /novo-v1/docs/ | Runway prompts for generating V1 scene images. | In use |
| 10 | novo-v1-build-order.md | /novo-v1/docs/ | Project structure and build order. | Current |
| 11 | novo-v1-asset-register.md | /novo-v1/docs/ | This file. | Current |
| 12 | novo-v1-known-issues.md | /novo-v1/docs/ | Known issues, risks, and deferred items. | Current |
| 13 | novo-backlog.md | /novo-v1/docs/ | Backlog — active tasks and post-V1 ideas. | Current |

---

## Files not yet created (expected for V1)

| What | Phase/Step | Notes |
|------|-----------|-------|
| Blender room file (.blend) | Phase 0 | The canonical 3D room geometry. All layers rendered from this. |
| Blender-anchored layer renders | Phase 0 | Room, curtain, chair rendered from the same composition — shared perspective. |
| Runway-styled layer images | Phase 0 | Style-transferred versions of the Blender renders. Will replace current images/ contents. |
| CSS file (if separated from index.html) | Phase 1 | May stay inline. TBD. |
| JS file (if separated from index.html) | Phase 1 | May stay inline. TBD. |
| Shader/grain code (if separate file) | Phase 1.3 | The top layer. May be inline. TBD. |

---

## Register rules

- Every file that is part of the project gets a row. No exceptions.
- **Source** = where the file came from (Runway, remove.bg, Blender, hand-written, library, etc.)
- **Status** = one of: **in use**, **archived**, **superseded by [filename]**, **draft**.
- When a file is replaced, the old file stays in the register marked superseded. Nothing disappears silently.
- Version numbers go in filenames when a file has been through more than one iteration. The register tracks which version is current.
