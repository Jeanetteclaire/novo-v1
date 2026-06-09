# Novo V1 — Known Issues

*Last updated: 9 June 2026*
*Maintained by: Documentation instance*
*Status: V1 wrapped up. Project paused.*

---

## Active issues (blocking or affecting the current build step)

**ISSUE-09: Runway drift between generations (risk downgraded — pipeline validated but weakness remains)**
Severity: Managed risk — no longer the single biggest V1 risk, but still present.
The Blender→Runway pipeline is validated: Runway holds composition when anchored to a Blender render, and style consistency across separately-generated layers is confirmed. The pipeline WORKS. However, Runway can still shift details between generations even with a Blender anchor — multiple passes may be needed for tight alignment. Layer generation isn't one-shot. This is manageable, not blocking.
Owner: Jeanette (in Runway, iterating).

**ISSUE-10: Curtain may be tiling/repeating across canvas**
Severity: Observed — not blocking, log for now.
The curtain looks like it might be tiling or repeating across the canvas rather than hanging as distinct panels matching window widths. Needs checking once final art is in place — may resolve itself with Blender-anchored curtain layer.
Owner: Code Claude (JS) when final art arrives.

**ISSUE-11: Layer alignment requires manual CSS positioning**
Severity: Observed — manageable for V1.
Layers generated separately don't pixel-align automatically. CSS positioning may need manual adjustment per layer. The Blender anchor constrains perspective and proportions (validated), but fine positioning in-browser is still manual work. Acceptable for V1's single viewpoint; becomes harder if multiple viewpoints are needed post-V1.
Owner: Code Claude (HTML/CSS).

**ISSUE-01: Curtain motion too regular (waiting for final art)**
Severity: Deferred — Phase 1, step 1.2. Wait for final assets before tuning.
The curtain animates but uses default wave parameters via a GLSL vertex displacement shader (sine-wave, anchored at top, slow horizontal sway). The motion reads as a wave function, not as cloth. Needs layered randomness, anchored displacement increasing from the top, and enough variation that it never visibly repeats. See brief §12b. No point tuning motion on placeholder art — tune once the final curtain layer is in place.
Owner: Code Claude (JS).

---

## Known but not yet relevant (will matter at a later step)

**ISSUE-02: Grain/shader pass — IN PROGRESS (four features implemented, tuning ahead)**
Four painterly overlay features are now live in index.html: vignette (CSS radial gradient), static paper grain (JS-generated noise tile at 0.04 opacity), colour grade (CSS filter: brightness/contrast/saturate/sepia on the scene wrapper), and animated grain/boil (SVG feTurbulence/feDisplacementMap, seed cycling ~every 900ms). Each is independently toggleable. Parameters are first-pass values — tuning by eye is still ahead. See brief §8, §12a.
Owner: Code Claude (JS) + Jeanette.

---

## Consciously deferred from V1

**ISSUE-03: Sound deferred despite being "core" in the brief** — CLOSED
Sound is now implemented. Ambient audio plays on loop, starts on first click/tap (browser autoplay restriction). Volume 0.3.

**ISSUE-04: View layer not yet separated** — CLOSED
View is now a separate video layer (view.mp4) behind a room layer with transparent windows. The view shows through the windows. Seasonal rotation is still post-V1 but the architectural separation is done.

**ISSUE-05: No version control** — CLOSED
Git repository set up and pushing to GitHub.

---

## Housekeeping

**ISSUE-06: Brief filename inconsistency** — CLOSED
Previous brief versions (v1–v12) with mixed naming conventions have been deleted. Only v13 remains. No longer an issue.

**ISSUE-07: Scoping worksheet status unknown**
docs/Novo_Scoping_Worksheet.md exists. Unclear whether it's still active or was a one-off exercise. Jeanette to confirm — can then be marked active or archived in the asset register.

**ISSUE-08: Interaction diagram shows broader scope than current V1 build**
The diagram ("Novo v1 — How It All Interacts.png", now in docs/) includes JS Job B (seasonal view swap) and sound, both of which are post-V1. The diagram is still the correct architectural reference, but instances reading it should know the current V1 build is a subset of what it shows.

**ISSUE-12: Image filenames in repo may not match current asset filenames** — CLOSED
Asset filenames updated. Current index.html references match the current files in images/ (room.png, curtains.png, plant.png, chair.png, view.mp4).
