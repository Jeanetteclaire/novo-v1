# Novo V1 — Known Issues

*Last updated: 5 June 2026*
*Maintained by: Documentation instance*

---

## Active issues (blocking or affecting the current build step)

**ISSUE-09: Layers don't share exact perspective (confirmed — Blender pipeline will solve)**
Severity: Active — this is what Phase 0b exists to solve.
The current layers were generated separately in Runway and do not share exact perspective — different proportions, different light angles, different scale. The architecture proof (Phase 0a) confirmed the stacking works, but also confirmed the art needs to come from one anchored composition. The Blender→Runway pipeline (Phase 0b) is the solution: Blender holds the canonical geometry so all layers share one viewpoint, Runway applies the style.
Owner: Assets instance.
Risk level: If Runway style transfer doesn't hold consistency across layers from the same Blender scene, the pipeline doesn't work and alternative approaches are needed. This remains the single biggest technical risk in V1.

**ISSUE-10: Curtain may be tiling/repeating across canvas**
Severity: Observed — not blocking, log for now.
The curtain looks like it might be tiling or repeating across the canvas rather than hanging as distinct panels matching the window widths. Needs checking once final art is in place — may resolve itself with Blender-anchored curtain layer.
Owner: Animation instance (when final art arrives).

**ISSUE-11: Perspective mismatch between current layers**
Severity: Observed — expected to be resolved by Phase 0b.
The room, curtain, and chair were generated separately in Runway, so they don't share exact perspective. This is precisely what the Blender-anchored pipeline is meant to solve. Not a problem with the architecture (which is proven) — a problem with the current placeholder art.
Owner: Assets instance.

**ISSUE-01: Curtain motion too regular (waiting for final art)**
Severity: Deferred — Phase 1, step 1.2. Wait for Blender-anchored assets before tuning.
The curtain animates but uses default wave parameters. The motion reads as a wave function, not as cloth. Needs layered randomness, anchored displacement increasing from the top, and enough variation that it never visibly repeats. See brief §12b. No point tuning motion on placeholder art — tune once the final curtain layer is in place.
Owner: Animation instance.

---

## Known but not yet relevant (will matter at a later step)

**ISSUE-02: No grain/shader pass**
Severity: Deferred — Phase 1, step 1.3, depends on step 1.2 completion.
The fourth layer (grain, soft focus, vignette, hatching) does not exist yet. Without it the scene reads as a clean digital image rather than an illustration. See brief §8, §12a.
Owner: Animation instance.

---

## Consciously deferred from V1

**ISSUE-03: Sound deferred despite being "core" in the brief**
The brief elevates sound to a core immersion mechanism (§10) and calls headphones the highest-leverage sensory channel. Sound is nonetheless out of V1 scope by Jeanette's decision. This is noted here so the weight the brief gives it isn't lost when sound is picked up post-V1.

**ISSUE-04: Seasonal view swap not implemented**
V1 uses one static view (view.png). The brief describes a system where JS checks the real-world date, picks a season, and randomly selects a view from an external pool of seasonal images (§11a). The interaction diagram includes this as "JS Job B." Deferred — V1 has one view only.

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
