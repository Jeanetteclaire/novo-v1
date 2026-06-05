# NOVO — Design Brief (v1, living document)

*Working name: Novo. A comfort space — a place to go for comfort and a reminder of who I mostly am. Built as the first instance of the retirement mission: build useful beautiful things that inspire and awe, share them freely, for the one person who stops and says "oh."*

*This is a living document. It will be rebuilt whole as it grows, so it stays one file, not many.*

---

## 1. THE FEELING (the spine — everything serves this)
* Coming home.
* Beautiful and peaceful but NOT passive — something that needs care.
* Wraps around you like a warm blanket on a cold day; brings joy and curiosity on other days.
* A place to rest AND a place to play.
* Safe and warm in my own space, but part of something bigger.
* The feeling of Amsterdam, made portable — that feeling, with me when I'm elsewhere.

## 2. THE CORE PRINCIPLE: care, not passivity
* Comfort that reciprocates — you tend it, it responds.
* A comfort that asks nothing = a screensaver. Novo asks for a little care.
* Plants that need tending are the emblem of this.
* Same instinct as Claudette: a presence you maintain, not a tool you consume.
* This is what makes Novo HERS, not a generic calm app.

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
* Plants that need care.
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

## 7. MEDIUM & BUILD PATH
* Don't lock the medium early — design the feeling first.
* START: flat, web-based pan/scroll canvas. Cheap to iterate, get the FEELING right where failure is cheap.
* LATER (optional): immersive / WebXR layer if it sings and is wanted.
* Two moods of one place:
    * Everyday: phone/web, one tap, always there (the portable feeling).
    * Occasional: fully inside it, at home, high effort (VR someday).

## 8. SENSORY LAYERS (home/immersive tier — capture now, build much later)
* Sound — the ONE layer that can travel (phone + headphones); may bridge portable + immersive.
* Light — smart bulbs, mostly have APIs; home-only but easier to integrate.
* Scent — highest emotional leverage, but physical + single-location, consumable cost, API unverified. Home-only. (Moodo was one example; compare brands.)
* Verify any device API exists and works before relying on it.

---

## GAPS — things still to think about
*(The point of the brief is to fill these in over time. Not urgent — flagged so they're not forgotten.)*

### Purpose & use
* [GAP] What are the actual MOMENTS Novo is for? (low day, restless day, needing focus, needing play, needing to remember who I am?)
* [GAP] What does a typical "visit" look like start to finish? What do I do when I arrive?
* [GAP] How is the everyday-portable version different from the full-home version, concretely?

### The "needs care" mechanic
* [GAP] What does the care actually consist of? (water plants? return regularly? something decays if ignored?)
* [GAP] What's the line between "rewarding to tend" and "a chore / guilt machine"? (must not become an obligation that punishes absence.)

### People & visitors
* [GAP] Is this private-first or shareable? The mission says "share freely" — but a comfort space is intimate.
* [GAP] If visitors can come, what can they see / do / not see? Where's the privacy line?
* [GAP] "People are there or links to them" — represented how? (avatars? photos? just links?)

### Content & change over time
* [GAP] Does Novo change with time of day / season / weather? (morning light implies yes.)
* [GAP] The diary/log — freeform? prompted? private always?
* [GAP] Does the space evolve as you add to it, or is it a fixed room you furnish?

### Emotional safety
* [GAP] On a genuinely bad day, what should Novo do — and NOT do? (must comfort without being saccharine or hollow.)
* [GAP] How does it "remind me who I mostly am" — what carries that? (objects? words? the collected wall?)

### Scope & first step
* [GAP] What is the SMALLEST version that still delivers the feeling? (the thing to build first.)
* [GAP] What's explicitly OUT of scope for v1, to avoid it ballooning?

### Practical / technical
* [GAP] Where does it live + persist? (own server? static site? builds on your existing stack?)
* [GAP] Is it just yours, or eventually a thing others can make their own version of?
* [GAP] Reference the mymind moodboard items here as they're brought in.

---

## CHANGELOG
* v1 — consolidated the morning's brief: feeling, care-principle, anchor, aesthetic (+ hatching/boil), elements, navigation, medium/build path, sensory layers. Gaps flagged.
