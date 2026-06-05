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
    ├── Novo Brief v11.md
    ├── Novo Brief v12.md
    ├── Novo Brief v13.md
    ├── Novo_Brief_v1.md
    ├── Novo_Brief_v2.md
    ├── Novo_Brief_v3.md
    ├── Novo_Brief_v4.md
    ├── Novo_Brief_v5.md
    ├── Novo_Brief_v6.md
    ├── Novo_Brief_v7.md
    ├── Novo_Brief_v8.md
    ├── Novo_Brief_v9.md
    ├── Novo_Brief_v10.md
    ├── Novo_Scoping_Worksheet.md
    └── Novo_v1_Runway_Prompts.md
```

---

## Active build files

These are the files that make V1 run.

| # | Filename | Location | What it is | Source | Status |
|---|----------|----------|-----------|--------|--------|
| 1 | index.html | /novo-v1/ | Main page. Loads the three image layers, runs curtain animation. | Hand-written | In use |
| 2 | view.png | /novo-v1/images/ | City view layer — the soft city beyond the glass. Sits behind the room. | Runway | In use |
| 3 | room.png | /novo-v1/images/ | Room interior layer — windows, egg chair, walls. The main scene. | Runway | In use |
| 4 | curtain.png | /novo-v1/images/ | Transparent curtain layer — sheer curtains, no background. Animates over the room. | Runway + remove.bg | In use |

Note: The brief describes V1 as four stacked layers — view / room / curtain / shader-grade (§12a companion artefacts). Three of those four are images and exist. The fourth (shader/grain) is code, not a file — it will be applied as a post-processing pass over the other three.

---

## Documentation files

| # | Filename | Location | What it is | Status |
|---|----------|----------|-----------|--------|
| 5 | Novo Brief v13.md | /novo-v1/docs/ | Current design brief. Living document. | Current |
| 6 | Novo Brief v12.md | /novo-v1/docs/ | Previous brief version. | Superseded by v13 |
| 7 | Novo Brief v11.md | /novo-v1/docs/ | Previous brief version. | Superseded by v13 |
| 8 | Novo_Brief_v1.md through v10 | /novo-v1/docs/ | Brief history, v1–v10. | Superseded by v13 |
| 9 | Novo_Scoping_Worksheet.md | /novo-v1/docs/ | Scoping worksheet. | Unknown — confirm if still active |
| 10 | Novo_v1_Runway_Prompts.md | /novo-v1/docs/ | Runway prompts for generating V1 scene images. | In use — referenced in brief §12a companion artefacts |

---

## Files not yet created (expected for V1)

| What | Step | Notes |
|------|------|-------|
| CSS file (if separated from index.html) | Any | May stay inline. TBD by HTML/CSS instance. |
| JS file (if separated from index.html) | 2 | Curtain animation logic may be extracted. TBD by Animation instance. |
| Shader/grain code (if separate file) | 3 | The fourth layer. May be inline JS/CSS or a separate file. TBD by Animation instance. |

---

## Companion artefacts (exist outside the project directory)

| What | Filename | Where | Source | Notes |
|------|----------|-------|--------|-------|
| V1 interaction diagram | Novo_v1___How_It_All_Interacts_2x.png | Whimsical (exported as PNG) | Jeanette | Shows the full V1 architecture: one HTML page containing three code files (HTML/CSS/JS), two JS jobs (animate curtain / swap view), four stacked layers (view / room / curtain / shader-grade), external view image pool, and optional sound. The reference architecture for every instance working on V1. |

---

## Register rules

- Every file that is part of the project gets a row. No exceptions.
- **Source** = where the file came from (Runway, remove.bg, hand-written, library, etc.)
- **Status** = one of: **in use**, **archived**, **superseded by [filename]**, **draft**.
- When a file is replaced, the old file stays in the register marked superseded. Nothing disappears silently.
- Version numbers go in filenames when a file has been through more than one iteration. The register tracks which version is current.
