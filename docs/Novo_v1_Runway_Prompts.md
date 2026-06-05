# NOVO v1 — Runway Image Prompts

*Source art for the v1 "living illustration" (per Novo brief §12a). Generate each element SEPARATELY so layers can move and swap independently (per §12b / §11a). Generate several per prompt and pick by eye — image generation is a slot machine; these are starting points to tune, not finished incantations.*

---

## THE GOLDEN RULE
Keep these words in EVERY prompt — they are the defence against the clunky / over-realistic / kitchen-planner look:
**painterly, illustration, soft edges, not photorealistic, muted, calm.**

Anything you want to MOVE later (curtain, tree) must be generated as its OWN separate element on a plain background, not baked into the room.

---

## 1. THE ROOM (the core scene — generate first)
> Interior of a large calm minimalist loft, painterly illustration, soft muted palette, a high-backed armchair in the corner facing tall floor-to-ceiling windows, thin muslin curtains, warm soft natural light, gentle hand-painted texture, visible brushwork, soft edges, atmospheric, serene, intimate yet spacious, not photorealistic, storybook illustration quality, warm and inviting, subtle grain --no people, harsh lighting, clutter, text

## 2. THE CURTAIN (separate element — for the motion layer)
> Thin white muslin curtain hanging by a tall window, soft painterly illustration, gently billowing, translucent fabric catching warm light, isolated against a soft neutral background, hand-painted texture, delicate, soft edges, not photorealistic --no people, text, hard edges

## 3. (OPTIONAL) A FICUS / TREE (separate element — if you want a swaying plant)
> A large potted ficus tree, soft painterly illustration, full leafy canopy, isolated against a plain soft neutral background, warm gentle light, hand-painted texture, soft edges, calm, not photorealistic --no people, text, pot clutter
*(Generate it standalone so it can sit on its own layer and sway — anchored sine-wave motion, trunk still, canopy rippling, per §12b.)*

---

## 4. THE SEASONAL VIEW PLATES (the swappable external pool — §11a)
*Generate the VIEW separately from the room so the window scene can change with the season without rebuilding the room. Make a few of each. Random within the season (per §0 — can't be wrong because all are beautiful + season-appropriate).*

**Spring**
> View through a window of a soft painterly landscape, gentle spring light, blossom and fresh green, hazy distance, dreamy atmospheric illustration, muted warm palette, calm, beautiful, not photorealistic, soft edges --no people, text

**Summer**
> View through a window of a soft painterly landscape, warm golden summer light, a calm meadow or distant sea under gentle haze, dreamy atmospheric illustration, muted warm palette, serene, beautiful, not photorealistic, soft edges --no people, text

**Autumn**
> View through a window of a soft painterly landscape, low golden autumn light, warm amber and rust foliage, hazy distance, dreamy atmospheric illustration, muted palette, calm, beautiful, not photorealistic, soft edges --no people, text

**Winter**
> View through a window of a soft painterly landscape, pale blue-grey winter light, soft snow and bare trees, quiet stillness, dreamy atmospheric illustration, muted cool palette, calm, beautiful, not photorealistic, soft edges --no people, text

---

## USAGE NOTES
* Layer order, back to front (per the v1 interaction diagram): VIEW -> ROOM (with window) -> CURTAIN -> (optional TREE) -> shader/grade pass on top.
* The painterly "boil," grain, vignette and colour grade are applied in CODE over all layers — NOT generated into the images. Keep the source images clean + soft; the shader adds the final character.
* Tune the adjectives toward what your eye wants once you see the first batch — that's the taste-practice, pointed at prompts.
* Don't name living artists/photographers/studios as style anchors; describe the visual qualities instead (palette, light, brushwork, era, mood).
