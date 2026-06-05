# Novo V1 — Asset Register

*Last updated: 5 June 2026*
*Maintained by: Documentation instance*

---

## Project directory structure

```
novo-v1/
├── index.html
├── images/
│   ├── view.png
│   ├── room.png
│   └── curtain.png
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

These are the files that make V1 run.

| # | Filename | Location | What it is | Source | Status |
|---|----------|----------|-----------|--------|--------|
| 1 | index.html | /novo-v1/ | Main page. Loads the three image layers, runs curtain animation. | Hand-written | In use |
| 2 | view.png | /novo-v1/images/ | City view layer — the soft city beyond the glass. Sits behind the room. | Runway | In use — may be superseded by Phase 0 pipeline |
| 3 | room.png | /novo-v1/images/ | Room interior layer — windows, egg chair, walls. The main scene. | Runway | In use — may be superseded by Phase 0 pipeline |
| 4 | curtain.png | /novo-v1/images/ | Transparent curtain layer — sheer curtains, no background. Animates over the room. | Runway + remove.bg | In use — may be superseded by Phase 0 pipeline |

Note: The brief describes V1 as four stacked layers — view / room / curtain / shader-grade (§12a). Three of those four are images and exist. The fourth (shader/grain) is code, not a file — it will be applied as a post-processing pass over the other three. Current images were generated directly in Runway; Phase 0 tests a Blender→Runway pipeline that may produce replacements.

---

## Documentation files

| # | Filename | Location | What it is | Status |
|---|----------|----------|-----------|--------|
| 5 | Novo Brief v13.md | /novo-v1/docs/ | Current design brief. Living document. | Current |
| 6 | Novo v1 — How It All Interacts.png | /novo-v1/docs/ | V1 interaction diagram. Shows the full V1 architecture: one HTML page, three code files (HTML/CSS/JS), two JS jobs, four stacked layers, external view image pool, optional sound. The reference architecture for every instance working on V1. Note: diagram shows broader scope than current V1 build (includes seasonal view swap and sound, both post-V1). | Current |
| 7 | Novo_Scoping_Worksheet.md | /novo-v1/docs/ | Scoping worksheet. | Unknown — Jeanette to confirm if still active |
| 8 | Novo_v1_Runway_Prompts.md | /novo-v1/docs/ | Runway prompts for generating V1 scene images. | In use |
| 9 | novo-v1-build-order.md | /novo-v1/docs/ | Project structure and build order (Phase 0 + Phase 1). | Current |
| 10 | novo-v1-asset-register.md | /novo-v1/docs/ | This file. | Current |
| 11 | novo-v1-known-issues.md | /novo-v1/docs/ | Known issues, risks, and deferred items. | Current |
| 12 | novo-backlog.md | /novo-v1/docs/ | Backlog — active tasks and post-V1 ideas. | Current |

Previous brief versions (v1–v12) have been deleted. Only v13 is retained.

---

## Files not yet created (expected for V1)

| What | Phase/Step | Notes |
|------|-----------|-------|
| Blender room file (.blend) | Phase 0.3 | The canonical 3D room geometry. Created if pipeline test succeeds. |
| Blender layer renders | Phase 0.4 | Rendered layers from confirmed angles. |
| Runway-styled layer images | Phase 0.5 | Style-transferred versions of the Blender renders. May replace current images/ contents. |
| CSS file (if separated from index.html) | Phase 1 | May stay inline. TBD by HTML/CSS instance. |
| JS file (if separated from index.html) | Phase 1 | Curtain animation logic may be extracted. TBD by Animation instance. |
| Shader/grain code (if separate file) | Phase 1.3 | The fourth layer. May be inline JS/CSS or a separate file. TBD by Animation instance. |

---

## Register rules

- Every file that is part of the project gets a row. No exceptions.
- **Source** = where the file came from (Runway, remove.bg, Blender, hand-written, library, etc.)
- **Status** = one of: **in use**, **archived**, **superseded by [filename]**, **draft**.
- When a file is replaced, the old file stays in the register marked superseded. Nothing disappears silently.
- Version numbers go in filenames when a file has been through more than one iteration. The register tracks which version is current.
