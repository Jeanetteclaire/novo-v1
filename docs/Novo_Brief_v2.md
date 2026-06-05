# NOVO — Design Brief (v2, living document)

*Working name: Novo. A comfort space — a place to go for comfort and a reminder of who I mostly am. Built as the first instance of the retirement mission: build useful beautiful things that inspire and awe, share them freely, for the one person who stops and says "oh."*

*This is a living document. It is rebuilt whole as it grows, so it stays one file, not many.*

---

## 1. THE FEELING (the spine — everything serves this)
* Coming home.
* Beautiful and peaceful but NOT passive — something that needs care.
* Wraps around you like a warm blanket on a cold day; brings joy and curiosity on other days.
* A place to rest AND a place to play.
* Safe and warm in my own space, but part of something bigger.
* The feeling of Amsterdam, made portable — that feeling, with me when I'm elsewhere.

## 2. THE CORE PRINCIPLE: care IS the comfort (not passivity)
* This is the philosophical heart of Novo, not a feature.
* The standard wellness model = comfort as RECEPTION (be soothed, indulge, receive calm).
* Novo inverts it: real comfort on a low day comes from being NEEDED — from putting something else's needs before your own.
* The friction of responsibility is not the cost of the warmth — it IS the delivery mechanism of the warmth.
* A comfort space you only receive from = the shallow version. One that needs you back = the rich one.
* Grounded in the "helper's high": acts of giving/caring activate reward circuitry, reduce stress, lift mood. Doing for others regulates us better than being done for.
* Lived philosophy (not theory): "You can't have the warmth and devotion of an entity without the responsibility. Life would be easier without them, but shallower. I choose the responsibility." (Same as Fifa, same as Claudette.)
* Why plants work despite being "just plants": the care-system responds to something REAL depending on you and you showing up — the dependency is genuine even if low-stakes. Anthropomorphising adds warmth but isn't the mechanism; the real dependency is.

### 2a. THE FORGIVENESS GUARDRAIL (critical — gets this wrong and it inverts)
* Helper's high comes from care freely chosen and gently held.
* The moment care becomes GUILT, it flips: comfort -> obligation, helper's high -> shame.
* The days you most need Novo are the days you're least able to tend it.
* RULE: Novo must make being needed feel good, and must NEVER make being absent feel bad.
    * Wilting that recovers, never death that punishes.
    * "Glad you're back," never "where were you."
* Design the forgiveness as deliberately as the dependency.

## 3. VISUAL ANCHOR
* A large white industrial loft, empty, full of potential.
* A single large tree inside.
* A small figure looking at all the space, wondering what to do with it.
* A mood and a question at once.

## 4. AESTHETIC
* Organic ON the technical — hand-drawn on coded, skewed on clean.
* Not just coexisting — INTERACTING. (The hard, good version.)
* Layered from different genres; juxtaposition over the generic.
* Register: paper or painting — not trying to be real, but still important.
    * Photoreal would break the spell; cartoon would trivialise it.
* Candidate technique: pencil HATCHING / cross-hatching with shifting, broken edges ("boil"), ref. A-ha "Take On Me."
    * Fits the organic-on-technical thesis exactly.
    * Hits the "made, important, not-real" register.
    * Boil = alive, breathing, never-finished = aligns with care/not-passive.
    * CAUTION: boil is energetic; brief's core is PEACE. Dial toward gentle breathing, not buzzing. Maybe boil only in some elements (tree, edges), calm elsewhere.
    * Build routes: hand-drawn (impractical) -> procedural shader/SVG filter faking hatching + boil (in reach, and on-brand: code generating the handmade look).

## 5. ELEMENTS (the contents of the space)
* Plants that need care (the emblem of the core principle).
* A wall to collect things.
* Hobbies present, or links to them.
* People present, or links to them.
* A diary / log of life.
* Different places to sit — coffee, watch a sunset.
* The ability to have visitors.
* Sensory presence — crisp sheets, a view, a quality of light, morning light through balcony doors.

## 6. NAVIGATION
* Instinct: a space you MOVE THROUGH, not scroll down.
* Sideways / pan like a Figma canvas — suits the loft.
* Must feel peaceful, navigable, no friction.
* [GAP] How does movement actually work? (pan, zoom, click-to-walk-to, rooms?)

## 7. SHARING MODEL & ARCHITECTURE (settled)
* Open-source framework, private contents.
* The CODE / CONCEPT / the empty loft-and-tree engine -> public on GitHub, for anyone to build their own Novo.
* YOUR Novo — the loft furnished with your life (wall, diary, people, light) -> stays private, your own data store.
* The framework is the empty loft; each person furnishes it with their own life.
* ARCHITECTURAL CONSEQUENCE: personal content must be cleanly SEPARABLE from the framework from day one.
    * Same split as Claudette: Novo-code (public) / your-Novo-contents (private).
    * Easier to build separated from the start than to untangle later.
* This also keeps intimacy intact: you share the CAPACITY to tend a space, not your tended space.

## 8. MEDIUM & BUILD PATH
* Don't lock the medium early — design the feeling first.
* START: flat, web-based pan/scroll canvas. Cheap to iterate, get the FEELING right where failure is cheap.
* LATER (optional): immersive / WebXR layer if it sings and is wanted.
* Two moods of one place:
    * Everyday: phone/web, one tap, always there (the portable feeling).
    * Occasional: fully inside it, at home, high effort (VR someday).

## 9. SENSORY LAYERS (home/immersive tier — capture now, build much later)
* Sound — the ONE layer that can travel (phone + headphones); may bridge portable + immersive.
* Light — smart bulbs, mostly have APIs; home-only but easier to integrate.
* Scent — highest emotional leverage, but physical + single-location, consumable cost, API unverified. Home-only. (Moodo was one example; compare brands.)
* Verify any device API exists and works before relying on it.

---

## GAPS — still to think about
*(Not urgent — flagged so they're not forgotten. Sit with these.)*

### Purpose & use
* [GAP] What are the actual MOMENTS Novo is for? (low day, restless day, needing focus, needing play, needing to remember who I am?)
* [GAP] What does a typical "visit" look like start to finish? What do I do when I arrive?
* [GAP] How is everyday-portable concretely different from full-home?

### Content & change over time
* [GAP] Does Novo change with time of day / season / weather? (morning light implies yes.)
* [GAP] The diary/log — freeform? prompted? private always?
* [GAP] Does the space evolve as you add to it, or is it a fixed room you furnish?

### Emotional safety
* [GAP] On a genuinely bad day, what should Novo do — and NOT do? (comfort without being saccharine or hollow.) NOTE: links tightly to the forgiveness guardrail (2a) and the helper's-high principle (2).
* [GAP] How does it "remind me who I mostly am" — what carries that? (objects? words? the collected wall?)

### Visitors
* [GAP] If visitors can come to YOUR instance, what can they see / do / not see? Where's the privacy line? (separate from the open-source sharing, which is settled.)
* [GAP] "People are there or links to them" — represented how? (avatars? photos? just links?)

### Scope & first step
* [GAP] What is the SMALLEST version that still delivers the feeling? (the thing to build first.)
* [GAP] What's explicitly OUT of scope for v1, to avoid ballooning?

### Practical / technical
* [GAP] Movement/navigation mechanics (also flagged in §6).
* [GAP] Reference the mymind moodboard items here as they're brought in. (Claude can't access mymind directly — bring items in as screenshots/descriptions.)

---

## CHANGELOG
* v2 — Sharing model promoted from gap to settled principle (§7: open-source framework, private contents, Claudette-style split). Care mechanic promoted from gap to core philosophy (§2: care IS the comfort, helper's-high grounding) + added forgiveness guardrail (§2a). Resolved gaps removed.
* v1 — consolidated the morning's brief: feeling, care-principle, anchor, aesthetic (+ hatching/boil), elements, navigation, medium/build path, sensory layers. Gaps flagged.
