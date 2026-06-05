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
| City view layer | images/view.png | Exists | The soft city beyond the glass. Sits behind the room layer. |
| Room interior layer | images/room.png | Exists | The main scene — windows, egg chair, walls. |
| Curtain layer | images/curtain.png | Exists | Transparent sheer curtains. Generated in Runway, background removed via remove.bg. |
| Main HTML file | index.html | Exists | Loads the three image layers, runs curtain animation. Served at localhost:8000. |
| curtains.js integration | (in index.html) | Working | Curtain layer animates over the static room. |
| Design brief | docs/Novo Brief v13.md | Current | Living document, maintained by Jeanette. |
| Runway prompts | docs/Novo_v1_Runway_Prompts.md | Exists | Prompts used to generate the scene images. |

Three image layers already exist (view / room / curtain). The fourth layer — shader/grain — is code applied on top (step 3).

---

## What needs to be built — in order

### Phase 0 — R&D and asset pipeline (before any building)

The current room images were generated directly in Runway. Phase 0 tests a better pipeline: build a canonical 3D room in Blender, render layers from confirmed angles, then run Runway style transfer to get the pencil-drawn aesthetic. This solves the consistency problem — Runway alone can't guarantee the same room from different angles, but a Blender model can.

**0.1: Test Claude/Blender pipeline**
**Owner:** Assets instance (Blender/Claude MVP)
**What it is:** Can Claude build a simple room from a description in Blender? Test with a basic scene — walls, window, chair. Not the final room; just proving the pipeline works.
**Done when:** A recognisable room exists as a Blender file, built by Claude from a text description.

**0.2: Test Runway style transfer consistency**
**Owner:** Assets instance (Runway)
**What it is:** Take a Blender render and run Runway style transfer on it. Does the pencil-drawn / illustrated look hold across multiple angles of the same scene? Test with at least two different camera angles of the same room.
**Done when:** Two or more angles of the same Blender room, style-transferred in Runway, look like the same room in the same style.

**0.3: Build the canonical Blender room**
**Owner:** Assets instance (Blender/Claude MVP) + Jeanette (design approval)
**Depends on:** 0.1 and 0.2 both successful.
**What it is:** Build the actual Novo room in Blender — the loft, floor-to-ceiling windows, egg chair, the space. This becomes the canonical geometry that all renders come from.
**Done when:** Jeanette approves the room as the right space.

**0.4: Render all required layers**
**Owner:** Assets instance (Blender)
**Depends on:** 0.3 complete.
**What it is:** Render the separate layers the build needs — room, view, curtain — from the confirmed camera angle(s). Each moving element is its own layer (per brief §12b).
**Done when:** Clean, separate layer renders exist for each required element.

**0.5: Run Runway style pass on each render**
**Owner:** Assets instance (Runway) + Jeanette (tuning by eye)
**Depends on:** 0.4 complete.
**What it is:** Apply the Runway style transfer to each rendered layer. The pencil-drawn, painterly, illustrated look. Prompts should include "painterly / illustration / soft edges / not photorealistic / muted / calm" as the defence against the clunky-realistic look (per brief §12a companion artefacts).
**Done when:** Each layer looks right individually and together they compose into a coherent scene.

**0.6: Confirm asset set is consistent and complete**
**Owner:** Integration/QA + Jeanette
**Depends on:** 0.5 complete.
**What it is:** Stack the layers, check they compose cleanly, confirm the set is ready for Phase 1 build. The current Runway-only images (room.png, view.png, curtain.png) may be superseded by the new pipeline output.
**Done when:** Jeanette confirms the asset set is the room she wants to build with. Asset register updated with new files.

---

### Phase 1 — Build (uses confirmed assets from Phase 0)

**1.1: Room and curtains working ✓**
**Owner:** Animation instance + HTML/CSS instance
**Status:** Complete with current assets. May need re-integration if Phase 0 produces new layer images.
**What done looked like:** Open localhost:8000 and see a room with a city view, curtains moving over it. Layers compose into a single scene.

**1.2: Curtain motion tuned to natural**
**Owner:** Animation instance
**Depends on:** Step 1.1 confirmed with final assets.
**What it is:** The curtain motion is currently too regular — default wave parameters. It needs to feel like a real curtain stirred by a soft breeze: anchored at the top, displacement increasing downward, layered randomness so it never looks mechanical. See brief §12b for the precise motion model (anchored travelling sine-wave displacement, not rigid drift).
**Done when:** Jeanette watches the curtain for thirty seconds and it never repeats in a way she notices. It looks like cloth, not a wave function.

**1.3: Grain layer added — V1 complete**
**Owner:** Animation instance (shader code) + Jeanette (tuning by eye)
**Depends on:** Step 1.2 complete (motion settled before adding visual treatment on top).
**What it is:** A post-processing layer applied over the whole scene — grain, soft focus, vignette, hatching. This is the fourth layer in the stack (see interaction diagram). It sits on top of everything and gives the scene its painterly, illustrated register. See brief §8 (organic on technical) and §12a (painterly shader pass).
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

Phase 0 is done when the asset pipeline is proven and a consistent set of styled layers exists. Phase 1 is done when three things are confirmed in order:

1. **The room exists as a space you can sit with.** Layers compose into a single scene — a city view behind the room behind the curtains. It reads as a room, not as layers. *(Phase 1, step 1.1 — done with current assets, may need re-confirmation with Phase 0 assets.)*
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
