# Novo V1 — Known Issues

*Last updated: 5 June 2026*
*Maintained by: Documentation instance*

---

## Active issues (blocking or affecting the current build step)

**ISSUE-01: Curtain motion too regular**
Severity: Active — this IS Phase 1, step 1.2.
The curtain animates but uses default wave parameters. The motion reads as a wave function, not as cloth. Needs layered randomness, anchored displacement increasing from the top, and enough variation that it never visibly repeats. See brief §12b.
Owner: Animation instance.

**ISSUE-09: Runway style consistency across angles (live risk)**
Severity: Active — this is what Phase 0 exists to solve.
Runway generates beautiful individual images, but cannot guarantee consistency across multiple renders of the same room. If the room needs to be seen from more than one angle (now or post-V1), each Runway generation may produce a subtly different room — different proportions, different light, different chair. This breaks the feeling of one coherent space. The Blender→Runway pipeline (Phase 0) is the proposed solution: Blender holds the canonical geometry, Runway applies the style. Phase 0.2 specifically tests whether Runway style transfer holds consistency across angles of the same Blender scene.
Owner: Assets instance.
Risk level: If Phase 0.2 fails (style transfer doesn't hold), the pipeline doesn't work and alternative approaches are needed. This is the single biggest technical risk in V1.

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

**ISSUE-05: No version control**
No Git repository or any other version control set up for the project. Not blocking V1, but risk increases with every change made to working code. Worth setting up before post-V1 work begins.

---

## Housekeeping

**ISSUE-06: Brief filename inconsistency** — CLOSED
Previous brief versions (v1–v12) with mixed naming conventions have been deleted. Only v13 remains. No longer an issue.

**ISSUE-07: Scoping worksheet status unknown**
docs/Novo_Scoping_Worksheet.md exists. Unclear whether it's still active or was a one-off exercise. Jeanette to confirm — can then be marked active or archived in the asset register.

**ISSUE-08: Interaction diagram shows broader scope than current V1 build**
The diagram ("Novo v1 — How It All Interacts.png", now in docs/) includes JS Job B (seasonal view swap) and sound, both of which are post-V1. The diagram is still the correct architectural reference, but instances reading it should know the current V1 build is a subset of what it shows.
