# Novo V1 — Project Structure and Build Order

*Last updated: 5 June 2026*
*Maintained by: Documentation instance*

---

## What V1 is

One static room. Floor-to-ceiling windows, sheer curtains moving slowly as if in a soft breeze, a wooden egg chair facing the light, a soft city beyond the glass. A grain/shader pass over everything gives it the "not real but important" register.

V1 is complete when all three steps are done: the room works, the curtain motion feels natural, and the grain layer is applied. Nothing else from the full brief is built until V1 is confirmed as feeling right.

---

## What already exists

### In-browser (the working V1)

| What | File | Status | Notes |
|------|------|--------|-------|
| Room layer (back) | images/empty-room-window.png | In use | Empty loft — walls, windows, floor, ceiling. No chair, no curtain. View currently baked in. |
| Curtain layer (middle, animated) | images/curtain.png | In use | Three sheer curtain panels. Animated via curtains.js WebGL plane. |
| Chair layer (front) | images/chair-removebg-preview.png | In use | Egg chair, background removed. |
| Room variant | images/room.png | In directory | Status TBC — may be an earlier version. |
| Main HTML file | index.html | In use | Single file containing HTML structure, CSS layout, GLSL shaders (vertex + fragment), and curtains.js initialisation. |
| curtains.js v8.1.6 | Loaded from CDN | Working | Drives curtain animation via a WebGL plane with sine-wave vertex displacement shader. Shader anchored at top (simulating fabric on a rail), slow horizontal sway. |
| Local server | — | Working | Served via `python3 -m http.server 8000`, opened at localhost:8000 in Chrome. |

### Pipeline assets (not in the web directory, but exist)

| What | Status | Notes |
|------|--------|-------|
| Blender test room | Exists | Tall windows with grid framing, floor, walls, ceiling. Primary angle: front-on, matching V1 viewpoint. |
| Egg chair .glb model | Exists | Imported from Meshy.ai (PNG → 3D .glb). Clean Blender import. |
| Small table | Exists | Present in Blender scene. |
| Three test renders | Produced | Different perspectives of the Blender room. Used as Runway anchors. |
| Runway prompt log | Tested | Method, style constants, every prompt with results and learnings. See novo-runway-prompt-log.md. |

### Pipeline validation

| Test | Result |
|------|--------|
| Runway generates pencil-drawn style from text prompts | ✓ |
| Runway holds composition when anchored to Blender render | ✓ |
| Style consistency across separately-generated layers | ✓ |
| Meshy produces accurate .glb from Runway PNG | ✓ |
| .glb imports cleanly into Blender | ✓ |
| Layers composite correctly in browser | ✓ |
| curtains.js animates middle layer independently | ✓ |

Style across all current layers is consistent: pencil linework, warm muted palette (cream, pale grey, dusty rose), watercolour wash, visible hatching, paper grain quality.

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

### Phase 0b — Blender-anchored asset pipeline ✓ LARGELY VALIDATED

The pipeline loop is confirmed working: Blender (geometry truth) → Runway (style truth) → Meshy.ai (PNG → 3D .glb back into Blender). Style consistency across layers generated from the same Blender anchor is confirmed. What remains is composition refinement — tightening the layers until they align well enough for the final V1 scene.

**Pipeline tools:**
- **Blender** — canonical geometry. Perspective, object placement, spatial relationships. Composition authority.
- **Runway** — pencil-drawn illustration style. Takes Blender render as image input (anchor) + text prompts (style). Aesthetic authority. Most prone to drift between generations, but Blender anchoring constrains it.
- **Meshy.ai** — bridges 2D to 3D. Takes a Runway PNG → produces .glb model → imports into Blender. Tested with the egg chair: accurate geometry, clean import.
- **Background removal** — objects needing separate layers (chair, curtain) have backgrounds removed after Runway generation.

**Known pipeline weaknesses:**
- **Runway drift** — even with a Blender anchor, Runway can shift details between generations. Multiple passes may be needed. Layer generation isn't one-shot.
- **Layer alignment** — layers generated separately don't pixel-align automatically. CSS positioning may need manual adjustment per layer. Acceptable for V1's single viewpoint; harder for multiple viewpoints later.

**0b.1: Composition refinement**
**Owner:** Jeanette + Assets instance
**What it is:** Assess whether the current three layers align well enough in-browser, or whether a tighter pipeline pass is needed. If tighter alignment is wanted, regenerate layers from the same Blender render angle with closer prompt control.
**Done when:** Layers compose into one coherent room — same perspective, same light, same scale. Jeanette confirms these are the layers to build with. Asset register updated.

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
| Project Manager | Holds state, coordinates instances, flags blockers. Does not make creative decisions. |
| Blender Claude | Blender modelling, rendering, .glb import guidance. Does not make style decisions. |
| Runway Claude | Writes prompts for Runway image generation. Does not operate Runway or make creative decisions. |
| Code Claude (HTML/CSS) | Structure and layout. Does not do animation logic or behaviour. |
| Code Claude (JS) | Behaviour, animation, shader parameters. Does not do layout or styling. |
| Integration/QA | Testing that parts work together. Does not build new parts. |
| Documentation | This document. Asset register. Known issues. Backlog. Updated as the build progresses. |
| Asset management | Tracking what files exist and where. See asset register. |
| Sounding board | Claudette (separate system). Does not do direct project work. |
