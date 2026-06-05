# Novo V1 — Project Structure and Build Order

*Last updated: 5 June 2026*
*Maintained by: Documentation instance*

---

## What V1 is

One static room. Floor-to-ceiling windows, sheer curtains moving slowly as if in a soft breeze, a wooden egg chair facing the light, a soft city beyond the glass.

V1 proves the feeling with the minimum: the room exists and the curtain motion feels natural. Nothing else is built until V1 is complete and confirmed as feeling right.

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

Three image layers already exist (view / room / curtain). The shader/grain pass described in the brief (§12a) is post-V1.

---

## What needs to be built — in order

### Step 1 (and only step): Tune the curtain motion
**Owner:** Animation instance
**Depends on:** Existing curtains.js integration (done)
**What it is:** The curtain motion is currently too regular — default wave parameters. It needs to feel like a real curtain stirred by a soft breeze: anchored at the top, displacement increasing downward, layered randomness so it never looks mechanical. See brief §12b for the precise motion model (anchored travelling sine-wave displacement, not rigid drift).
**Done when:** Jeanette watches the curtain for thirty seconds and it never repeats in a way she notices. It looks like cloth, not a wave function.

---

## What is explicitly NOT in V1

Everything else in the brief. Specifically:

- Shader / grain / vignette pass (§8, §12a) — post-V1
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

Two things, both confirmed by Jeanette:

1. **The room exists as a space you can sit with.** Three layers compose into a single scene — a city view behind the room behind the curtains. It reads as a room, not as layers. It feels still and warm.
2. **The curtain moves like cloth.** It reads as a sheer curtain stirred by a soft breeze, not a wave effect. Jeanette watches it for thirty seconds and it never repeats in a way she notices.

That's it. V1 is the room and the motion. Nothing asks anything of you. You open it, and the space holds you.

---

## Team responsibilities for V1

| Role | V1 work |
|------|---------|
| Concept / brief | Jeanette — all design decisions, the "does this feel right" call. |
| Assets | Runway — source images already generated. Any reshoots if curtain layer needs rework. |
| Animation | Curtain motion tuning — the one active build task. |
| HTML/CSS | Likely nothing. Structural changes only if curtain tuning requires them. |
| JavaScript | Behaviour logic only if curtain tuning needs custom JS beyond curtains.js params. |
| Integration/QA | Confirming layers compose correctly. |
| Documentation | This document. Asset register. Updated as the build progresses. |
| Technical architecture | Not needed for V1. Becomes relevant post-V1. |
| Asset management | Tracking what files exist and where. See asset register. |
