# Novo V1 — Project Structure and Build Order

*Last updated: 5 June 2026*
*Maintained by: Documentation instance*

---

## What V1 is

One static room. Floor-to-ceiling windows, sheer curtains moving slowly as if in a soft breeze, a wooden egg chair facing the light, a soft city beyond the glass. A grain/shader pass over everything gives it the "not real but important" register.

V1 is complete when all three steps are done: the room works, the curtain motion feels natural, and the grain layer is applied. Nothing else from the full brief is built until V1 is confirmed as feeling right.

---

## What already exists

| What | File | Status | Notes |
|------|------|--------|-------|
| Room layer (back) | images/room.png | In use | Runway-generated. Will be replaced by Blender-anchored version. |
| Curtain layer (middle, animated) | images/curtain.png | In use | Runway + remove.bg. Animated via curtains.js. Will be replaced. |
| Chair layer (front) | images/chair-removebg-preview.png | In use | Runway + remove.bg. Will be replaced. |
| Empty room variant | images/empty-room-window.png | In directory | Status TBC. |
| Main HTML file | index.html | In use | Updated — loads three image layers with z-ordering, runs curtain animation. |
| curtains.js integration | (in index.html) | Working | Animates the middle curtain layer. |
| Design brief | docs/Novo Brief v13.md | Current | Living document, maintained by Jeanette. |
| Runway prompts | docs/Novo_v1_Runway_Prompts.md | In use | Prompts for generating scene images. |
| Interaction diagram | docs/Novo v1 — How It All Interacts.png | Current | Reference architecture. |

Three-layer architecture proven: room behind, curtain animated in the middle, chair in front. Current images prove the concept but don't share exact perspective — they were generated separately in Runway. The Blender-anchored pipeline (Phase 0b) will produce replacements that share one composition.

---

## What needs to be built — in order

### Phase 0a — Architecture proof ✓ PASSED

**What was tested:** Can multiple Runway-generated image layers stack and composite in the browser, with curtains.js animating a middle layer while other layers sit above and below?

**Result:** Yes. Three-layer architecture proven — room behind, curtain animated in the middle, chair in front. index.html updated to support three layers with z-ordering.

**What this confirms:**
- The stacked-layers approach from the interaction diagram is sound
- curtains.js can animate a middle layer while other layers sit above and below
- Runway-generated assets in the pencil-drawn style can composite together
- The z-ordering code works

**What it exposed (logged in known issues):**
- Curtain may be tiling/repeating across the canvas rather than hanging as distinct panels matching window widths (ISSUE-10)
- Layers don't share exact perspective — generated separately in Runway, not from one anchored composition (ISSUE-11). This is precisely what the Blender pipeline is meant to solve
- Curtain motion tuning still ahead — wait for final art (ISSUE-01)

---

### Phase 0b — Blender-anchored asset pipeline (current phase)

The architecture works. The next phase is making the art right — getting layers that truly belong together because they're anchored to the same Blender composition. Current images prove the concept but will be replaced.

**0b.1: Write Blender-anchored prompts**
**Owner:** Assets instance (Runway Claude) — brief is ready
**What it is:** Get the prompts written that will drive the Blender room build and the Runway style transfer. These need to describe the canonical room precisely enough that Blender can build it and Runway can style it consistently.
**Done when:** Prompts are written and reviewed.

**0b.2: Test prompts in Runway — iterate until layers share one composition**
**Owner:** Jeanette (in Runway)
**Depends on:** 0b.1 complete.
**What it is:** Generate layers from the Blender-anchored composition. Iterate until the room, curtain, and chair share exact perspective because they come from the same 3D scene. This is where the Runway consistency problem (ISSUE-09) gets solved.
**Done when:** A set of layers exists where every element belongs to the same room — same perspective, same light, same scale.

**0b.3: Confirm asset set is consistent and complete**
**Owner:** Jeanette
**Depends on:** 0b.2 complete.
**What it is:** Stack the new layers, confirm they compose cleanly into one coherent room. Current images in images/ will be superseded.
**Done when:** Jeanette confirms these are the layers to build with. Asset register updated.

---

### Phase 1 — Build (uses confirmed assets from Phase 0b)

**1.1: Room and layers working ✓ (architecture proven — will re-integrate with final art)**
**Owner:** Code instance
**Status:** Architecture proven with current assets. Will need re-integration when Phase 0b produces aligned layers — drop the new images into the working HTML.
**What done looked like:** Open localhost:8000 and see a room with curtains moving and the chair in front. Three layers composing into a single scene.

**1.2: Curtain motion tuned to natural**
**Owner:** Animation instance
**Depends on:** Step 1.1 re-confirmed with final Blender-anchored assets.
**What it is:** The curtain motion is currently too regular — default wave parameters. It needs to feel like a real curtain stirred by a soft breeze: anchored at the top, displacement increasing downward, layered randomness so it never looks mechanical. See brief §12b for the precise motion model (anchored travelling sine-wave displacement, not rigid drift).
**Done when:** Jeanette watches the curtain for thirty seconds and it never repeats in a way she notices. It looks like cloth, not a wave function.

**1.3: Grain layer added — V1 complete**
**Owner:** Animation instance (shader code) + Jeanette (tuning by eye)
**Depends on:** Step 1.2 complete (motion settled before adding visual treatment on top).
**What it is:** A post-processing layer applied over the whole scene — grain, soft focus, vignette, hatching. The top layer in the stack (see interaction diagram). Sits over everything and gives the scene its painterly, illustrated register. See brief §8 (organic on technical) and §12a (painterly shader pass).
**Done when:** The room reads as illustrated, not photographic. There is a visible texture across the whole scene. It feels like "paper or painting — not real, but important." V1 is complete.

---

## What is explicitly NOT in V1

Everything else in the brief. Specifically:

- Sound / ambient audio (§10) — post-V1
- The board (§5)
- Claudette (§5a)
- The gratitude layer (§5c)
- The book wall (§3a)
- The entrance sequence / compression-and-release corridor (§4)
- The departure ritual (§7a)
- The puzzle / activity object (§6)
- Seasonal view rotation (§11a) — V1 has one view, not a pool
- Overview / first-person camera toggle (§7)
- Any navigable 3D
- Any additional room elements (plants, art, furniture beyond the chair)
- Version control (noted as not set up; important but not a build step for V1 itself)

---

## How Jeanette knows V1 is finished

Phase 0a (architecture proof) is passed. Phase 0b is done when Blender-anchored layers exist that share one composition. Phase 1 is done when three things are confirmed in order:

1. **The layers compose into one room.** Blender-anchored layers drop into the working HTML and read as a single coherent space — same perspective, same light, same scale. *(Phase 1, step 1.1 — re-integration with final art.)*
2. **The curtain moves like cloth.** It reads as a sheer curtain stirred by a soft breeze, not a wave effect. Jeanette watches it for thirty seconds and it never repeats in a way she notices. *(Phase 1, step 1.2.)*
3. **The scene reads as illustrated, not digital.** The grain/shader layer gives the whole image a texture — paper, pencil, painting. It feels like "not real, but important." *(Phase 1, step 1.3.)*

When all three are confirmed, V1 is complete. You open it, the space holds you, and nothing asks anything of you.

---

## Team responsibilities for V1

| Role | V1 work |
|------|---------|
| Concept / brief | Jeanette — all design decisions, the "does this feel right" call at each step. |
| Assets | Blender/Claude MVP — Phase 0 room build and renders. Runway — style transfer passes. |
| Animation | Curtain motion tuning (1.2). Shader/grain pass code (1.3). |
| HTML/CSS | Structural changes if needed to support the grain layer. Likely minimal. |
| JavaScript | Behaviour logic if curtain tuning needs custom JS beyond curtains.js params. |
| Integration/QA | Phase 0.6 (confirm asset set). Phase 1 layer composition and grain pass testing. |
| Documentation | This document. Asset register. Known issues. Backlog. Updated as the build progresses. |
| Technical architecture | Not needed for V1. Becomes relevant post-V1. |
| Asset management | Tracking what files exist and where. Critical during Phase 0 as new assets are created. See asset register. |
