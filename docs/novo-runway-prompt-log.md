# Novo V1 — Runway Prompt Log

*Date: 5–6 June 2026*
*Model: Nano Banana 2*
*Purpose: Generating layered illustration assets for the Novo room, anchored to Blender geometry*

---

## The Method

Novo V1 is built as stacked image layers: room, curtains, and chair composited together in the browser. The layers must align perfectly when overlaid. Previous attempts using text-only prompts produced beautiful results but with inconsistent composition — every generation invented its own perspective, chair position, and window proportions.

The solution: use a Blender render as the image reference in Runway. The Blender render locks the geometry (perspective, positions, proportions). The prompt controls the aesthetic (pencil-drawn illustration with watercolour wash). The two authorities are kept separate — Blender owns WHERE things are, the prompt owns WHAT they look like.

---

## Style Constants

Used across all prompts to maintain aesthetic consistency:

> Pencil-drawn illustration with visible pencil lines, crosshatching, and soft watercolour washes. Warm muted palette of cream, pale grey, and dusty rose. Subtle paper grain texture. Soft edges, no harsh lines. Storybook illustration quality.

These are non-negotiable. Every prompt includes some version of this language. The key defence against Runway drifting toward photorealism or stylised 3D.

---

## Prompt 1 — Room Layer (Test 1: Geometry Anchoring)

**Reference image:** Blender render (novo_test_final.png)

**Prompt:**

> Pencil-drawn illustration of this interior scene. Maintain the exact perspective, camera angle, window positions, and room proportions from the reference image. Transform the rendering style into a hand-drawn illustration with visible pencil lines, crosshatching, and soft watercolour washes. Warm muted palette of cream, pale grey, and dusty rose. The egg-shaped form becomes a high-backed wooden egg chair with textured linen upholstery, same position and scale. Bare warm wooden floorboards with subtle grain. Tall floor-to-ceiling windows with clean glass, no curtains, no drapes — windows completely clear showing soft diffused white light beyond. The small table remains as a simple wooden side table. Subtle paper grain texture across the entire image. Soft edges, no harsh lines. Storybook illustration quality. No people, no text, no additional furniture or decorations.

**Result:** Success. All four outputs held the Blender composition — window mullion positions, floor line, chair placement, ceiling height were consistent. The style transformation worked well. The chair rendered as a recognisable egg chair despite the Blender input being a literal egg shape. Some outputs kept the side table, some dropped it.

**What worked:**
- The Blender render reliably anchored the composition
- Naming "high-backed wooden egg chair" steered Runway away from rendering a literal egg
- The style language landed consistently across all four outputs
- "No curtains, no drapes — windows completely clear" was respected

**What to note:**
- The side table appeared inconsistently — Runway sometimes dropped it. If the table matters, it may need its own layer or stronger prompt emphasis
- The chair's wood/leather tones and base style varied between outputs, but position held

---

## Prompt 2 — Room Layer Consistency Check (Test 3)

**Reference image:** Blender render (novo_test_final.png)

**Prompt:**

> Hand-drawn pencil illustration of this interior space. Preserve the exact camera angle, perspective, room geometry, and object placement from the reference. Render as a storybook illustration with visible pencil strokes, hatching, and delicate watercolour washes in warm cream, pale grey, and dusty rose tones. The egg-shaped object is a high-backed egg chair in warm wood with soft linen cushioning, same position and size. Simple wooden side table in its current position. Warm wooden floor with hand-drawn wood grain. Tall windows with clear glass, no curtains or drapes — open and bright with soft white light beyond. Subtle paper texture throughout. Soft edges, atmospheric and serene. No people, no text, no clutter, no additional objects.

**Why the wording changed:** Deliberately used different phrasing for the same instructions to test whether the Blender anchor held the composition regardless of prompt variation. If the geometry is truly anchored by the reference image, different words describing the same intent should produce the same layout.

**Result:** Success. Comparing Test 1 and Test 3 side by side, the composition held — window positions, floor line, chair placement, ceiling height were consistent across both batches. The Blender anchor is reliable.

**Key finding:** The geometry anchoring is driven by the reference image, not the prompt text. This means prompt wording can focus on style and mood without risking composition drift.

---

## Prompt 3 — Curtain Layer (First Attempt) — SUPERSEDED by Prompt 6

**Reference image:** Favourite room output from Test 1 (illustrated room, not the Blender render)

**Prompt:**

> Sheer white muslin curtains hanging from the top of the window frames shown in this reference image. The curtains are the ONLY element — remove the room, floor, chair, table, and all walls entirely. Flat pale cream background replacing everything except the curtains. Full-length translucent fabric with natural vertical folds and gentle draping, hanging from the exact window positions in the reference. Same pencil-drawn illustration style as the reference — visible pencil lines, crosshatching on the fabric folds, soft watercolour wash. The fabric is semi-transparent with soft light passing through. No shadows cast on the background. No floor, no walls, no furniture. Only curtains on a clean flat background.

**Why the reference changed:** The curtain layer needs to match the illustrated room, not the Blender geometry. Feeding an illustrated room as the reference gives Runway the window positions in the correct style, producing better-aligned curtains than trying to extract curtain positions from the bare Blender render.

**Result:** Partial success. Runway struggled to fully strip the room — the top row of outputs still showed the room and chair. The bottom row got much closer, with curtains on a mostly clean background. The bottom-left output was clean enough that a background removal tool could finish the job.

**What worked:**
- "Remove the room" was a clearer instruction than the original draft's "use this for positions only"
- Switching the reference from Blender to the illustrated room improved curtain positioning
- The pencil-line style on the curtain folds was consistent with the room layer

**What didn't work:**
- Runway resisted full room removal — it wants to generate a scene, not an isolated element
- Some window mullion lines survived behind the curtains

**Resolution:** Used a background removal tool to clean the best curtain output. This worked well. The curtain PNG ended up with a black/transparent background, suitable for compositing.

---

## Prompt 4 — Chair Layer (First Attempt — Failed)

**Reference image:** Favourite room output from Test 1

**Prompt (original, not used — this was the initial draft):**

> The high-backed egg chair from this reference image, isolated on its own. Same pencil-drawn illustration style — visible pencil lines, crosshatching, soft watercolour wash. Same warm wood and linen tones as the reference. The chair is shown from the same angle and at the same scale as it appears in the reference. Flat pale cream background. NO room, NO floor, NO windows, NO walls, NO table — only the chair and its base on a clean flat background. No shadows cast on the background. Even soft lighting preserving all edge detail for clean masking.

**Why the chair layer was needed:** The original layer stack was room (with chair baked in) → curtains on top. But the curtains hang in front of the windows, not in front of the chair. The correct stack is: empty room → curtains → chair on top. This required separating the chair from the room.

**Result:** The chair rendered correctly in style but filled the entire frame — far too large relative to the room.

**What went wrong:** "Isolated on its own" told Runway to zoom in and fill the frame with the chair. This is a known Runway behaviour — when you ask for isolation, it reframes and enlarges.

**Learning confirmed:** This matches the known issue from earlier Novo work — prompting for an element "isolated on a plain background" causes Runway to zoom and fill the frame. The correct approach is to tell Runway to remove everything AROUND the element while preserving its original scale and position.

---

## Prompt 5 — Chair Layer (Corrected)

**Reference image:** Favourite room output from Test 1

**Prompt:**

> The high-backed egg chair from this reference image, in the exact same position and at the exact same scale as it appears in the reference. Same pencil-drawn illustration style — visible pencil lines, crosshatching, soft watercolour wash. Same warm wood and linen tones. Keep the chair exactly where it sits in the reference scene. Remove everything else — no room, no floor, no windows, no walls, no table. Flat pale cream background replacing all surroundings. The chair must NOT be enlarged or reframed — it stays the same size and position as in the reference image. The overall image dimensions and framing match the reference exactly.

**Why the wording changed:** Instead of "isolated on its own" (which Runway reads as "fill the frame"), this says "same position, same scale, remove everything else." It tells Runway to erase the room around the chair rather than extract and zoom into the chair.

**Result:** Pending — awaiting test.

---

## Prompt for Empty Room (Not Yet Run)

**Reference image:** Blender render (novo_test_final.png)

**Prompt:**

> Pencil-drawn illustration of this interior scene. Maintain the exact perspective, camera angle, window positions, and room proportions from the reference image. Transform into a hand-drawn illustration with visible pencil lines, crosshatching, and soft watercolour washes. Warm muted palette of cream, pale grey, and dusty rose. Bare warm wooden floorboards with subtle grain. Tall floor-to-ceiling windows with clean glass, no curtains, no drapes — windows completely clear. Subtle paper grain texture across the entire image. Soft edges, no harsh lines. Storybook illustration quality. NO chair, NO table, NO furniture of any kind — the room is completely empty. Just the architectural space: walls, windows, floor, ceiling. No people, no text, no objects.

**Why needed:** The empty room becomes the back layer in the three-layer stack (empty room → curtains → chair). The Blender render is used as reference because it's already a furniture-free geometric anchor.

**Result:** Pending — awaiting test.

---

## Prompt 6 — Curtain Layer (Aligned) — supersedes Prompt 3

**Reference image:** Illustrated empty room (from empty room prompt, Blender-anchored)

**Problem:** Curtain layer from Prompt 3 did not align with the room — curtain tops sat too high, above the window frame line. The curtains need to begin at the top of the window frames but the curtain layer cannot show the window frames themselves.

**The reframe:** "Draw curtains where the windows are, then erase the windows" rather than "draw curtains aligned to an invisible point." Give Runway the full room as reference so it can see the window positions, tell it to use those as anchor points, then delete everything except the curtains.

**Why the reference changed:** Switched from illustrated room-with-chair to the illustrated empty room — clearer window visibility without the chair obstructing the view.

**Prompt:**

> Looking at the window positions in this reference image, generate ONLY sheer white muslin curtains hanging from the very top edge of the window frames. The curtains begin exactly where the top of the windows meet the ceiling — that is their anchor line. Full-length translucent fabric falling straight down to floor level with natural vertical folds and gentle draping. The curtains span the full width of the window wall. Pencil-drawn illustration style with visible pencil lines, crosshatching on the fabric folds, soft watercolour wash in white and pale cream tones. REMOVE everything that is not curtain fabric — no window frames, no mullions, no walls, no floor, no ceiling, no room. Replace all non-curtain areas with a flat uniform pale cream background. The curtains are the only drawn element in the image. The overall image framing and dimensions match the reference exactly — do not crop or reframe.

**Result:** Success. Curtains aligned correctly with window frame tops. Background removal cleaned remaining non-curtain elements. Three-layer stack (empty room → curtains → chair) now composites correctly.

**What worked:**
- Giving Runway the full room as reference then telling it to use geometry as anchor points and delete everything except the target element
- "The curtains begin exactly where the top of the windows meet the ceiling — that is their anchor line" — naming the anchor explicitly
- Using the empty room (no chair obstruction) as reference for clearer window visibility

---

## Prompt 7 — Open Curtains with Window Frame

**Reference image:** Illustrated empty room (Blender-anchored)

**Context:** The aligned curtains from Prompt 6 hang straight down, covering the full window width. This variant has the curtains parted from the centre, gathered at the sides, with the window visible through the gap. Needed for compositing over the room layer so the view through the windows is unobstructed.

**Prompt:**

> Looking at the window positions in this reference image, generate sheer white muslin curtains and the window frames. The curtains are OPEN — pulled apart from the centre to each side, gathered naturally at the left and right edges of the window wall. Each curtain panel drapes to its side with soft gathered folds, leaving the central portion of the windows clear and unobstructed. The window frames and mullions from the reference are visible through the gap between the curtains. The curtains begin exactly where the top of the windows meet the ceiling — that is their anchor line. Full-length fabric falling to floor level, fuller and more gathered at the sides where the fabric bunches. Pencil-drawn illustration style with visible pencil lines, crosshatching on the fabric folds, soft watercolour wash in white and pale cream tones. REMOVE the walls, floor, ceiling, and room — keep ONLY the curtain fabric and the window frames. Replace all non-curtain, non-window areas with a flat uniform pale cream background. The overall image framing and dimensions match the reference exactly — do not crop or reframe.

**Result:** Success. Curtains aligned perfectly with the room, parted to the sides, window frame visible through the gap. However the window frame being part of the curtain layer meant the frame moved with the curtain animation — not the desired effect.

**What worked:**
- Alignment held — curtains parted correctly relative to window positions
- Open/gathered draping rendered naturally

**What didn't work:**
- The window frame was included in the curtain layer, so it animated along with the curtains in curtains.js — frames should be static, not moving

---

## Prompt 8 — Remove Frame from Open Curtains

**Reference image:** Output from Prompt 7 (curtain-open.png)

**Problem:** Prompt 7 produced correctly aligned open curtains, but the window frame was included and animated with the curtain. The frame needs to be removed so only the fabric moves.

**Prompt:**

> This exact image with the window frame removed. Keep the curtains exactly as they are — same position, same folds, same fabric, same style. Delete only the window frame and mullions. Replace the window frame area with the same flat pale cream background. Everything else unchanged. Do not reframe, resize, or alter the curtains in any way.

**Result:** Success. Clean open curtains with no frame, aligned to the room, ready for compositing.

**What worked:**
- Feeding a near-perfect output back as its own reference and asking for targeted deletion
- "This exact image minus one thing" — Runway handles this reliably
- The window frame served as **alignment scaffolding**: it ensured the curtains sat correctly relative to the windows, then was removed once it had done its job

**The two-step scaffolding pattern:** Generate with scaffolding (include structural elements that help alignment), then remove the scaffolding in a second pass. More reliable than trying to generate a perfectly isolated element in one pass.

**Animation note for code instance:** Open/gathered curtains will animate differently under curtains.js displacement than straight-hanging curtains. The bunched fabric at the sides has different visual weight. Tuning flagged as needed once the asset is in the stack.

---

## Current Layer Stack (Confirmed)

1. **Empty room** — walls, windows, floor, ceiling, no furniture (back)
2. **Curtains** — sheer muslin, transparent background, animated via curtains.js (middle) — aligned via Prompt 6
3. **Chair** — egg chair at correct scale and position, transparent background (front)

This replaces the original two-layer stack (room with chair → curtains on top) which failed because curtains covered the chair. Three-layer composite confirmed working in-browser.

---

## Key Learnings

**The Blender anchor works.** Geometry, perspective, and object positions are reliably held when the Blender render is used as the image reference. Different prompt wording produces the same composition. This is the core finding.

**Runway resists isolation.** Asking for a single element on a blank background tends to produce either a zoomed/reframed version (filling the frame) or an incomplete removal (room traces left behind). The workaround is either: (a) phrase it as "remove everything else" rather than "isolate this," or (b) generate the full scene and use a separate background removal tool.

**Style and geometry references should be separated by purpose.** Use the Blender render when you need geometry anchoring (room structure, perspective). Use a successful illustrated output when you need style matching (curtain fabric, chair detail). Don't mix both as references in the same generation.

**Naming matters for ambiguous geometry.** The Blender egg shape could have rendered as a literal egg. Naming it "high-backed egg chair with textured linen upholstery" steered Runway to the right object. When the reference image is geometrically simple, the prompt must be specific about what the shapes represent.

**Negative instructions work but aren't absolute.** "No curtains" was respected. "No room, no floor" was partially respected. Runway follows negatives better for omitting elements from a scene than for stripping a scene down to a single element.

**"Draw it here then erase the context" works for alignment.** When an element needs to align with room geometry but not show it, give Runway the full room as reference and instruct it to use the geometry as anchor points then delete everything except the target element. Runway handles this better than "draw it aligned to something that isn't visible." Name the anchor explicitly ("the curtains begin exactly where the top of the windows meet the ceiling").

**"This exact image minus one thing" works for targeted removal.** When Runway produces a near-perfect output with one unwanted element, feed the output back as its own reference and ask for a targeted deletion. Runway handles this reliably. This enables a two-step **scaffolding pattern**: generate with structural elements that help alignment (e.g. window frames to position curtains), then remove the scaffolding in a second pass. More reliable than trying to generate a perfectly isolated element in one pass.

---

## Future Prompt Considerations

**View layer (not yet started):** The brief calls for a seasonal view beyond the windows — soft city, landscape, etc. This will be a separate layer behind the room. The room's clear windows act as the frame. The view needs to match the pencil-and-wash style but can be simpler/softer since it's seen through glass. Consider generating these at lower detail with more watercolour wash and less pencil line, so they read as "distant" rather than competing with the room's detail level.

**Plant element:** There's a fragment in the original prompts for a tall green plant. When this is needed, it should follow the same isolation approach as the chair — generate at correct scale and position within the full canvas, not zoomed in. The "remove everything around it" phrasing should work. The plant will need its own layer if it's going to be independently positioned or if it overlaps with the curtain animation.

**Consistency across future generations:** Now that we know the Blender anchor works, any new room elements should be generated using the same Blender reference to maintain perspective consistency. If the room composition changes (different camera angle, new furniture positions), the Blender scene should be updated first and all layers regenerated from the new anchor.

**Background removal as standard step:** Rather than fighting Runway to produce perfectly isolated elements, treat background removal as a standard post-processing step. Generate the element in context (or near-context), then clean it with a removal tool. This is more reliable than trying to get Runway to produce clean isolation in one pass.

**Shader/grain layer:** The brief mentions a painterly shader pass (hatching, grain, vignette) applied over all layers. This is code, not a Runway job — but the Runway-generated assets should leave room for it. Avoid baking too much grain or vignette into the source images, since the shader will add its own. Keep the Runway outputs clean and let the code layer do the atmospheric work.

---

## Changelog

- **6 June 2026 — Open curtains (parted, no frame):** Added Prompts 7 and 8. New curtain variant with curtains pulled open to the sides, view unobstructed. Prompt 7 generated aligned open curtains with window frame as scaffolding. Prompt 8 removed the frame via targeted deletion. Added scaffolding pattern to Key Learnings. Animation note flagged for code instance.
- **6 June 2026 — Curtain alignment fix:** Added Prompt 6 (curtain layer, aligned). Supersedes Prompt 3. Problem was curtain tops sitting above window frame line. Fix: use illustrated empty room as reference, name the anchor point explicitly, tell Runway to draw curtains at the window positions then erase everything except the curtains. Added alignment learning to Key Learnings. Layer stack status updated from "target" to "confirmed."
- **5–6 June 2026 — Initial log:** Prompts 1–5, empty room prompt, method, style constants, key learnings, future considerations.
