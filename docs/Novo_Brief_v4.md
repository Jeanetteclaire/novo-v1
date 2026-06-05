# NOVO — Design Brief (v4, living document)

*Working name: Novo. A comfort space — a place to go for comfort and a reminder of who I mostly am. Built as the first instance of the retirement mission: build useful beautiful things that inspire and awe, share them freely, for the one person who stops and says "oh."*

*This is a living document. It is rebuilt whole as it grows, so it stays one file, not many.*

---

## 1. THE FEELING (the spine — everything serves this)
* Coming home.
* Beautiful and peaceful but NOT passive — something that needs care.
* Wraps around you like a warm blanket on a cold day; brings joy and curiosity on other days.
* A place to rest AND a place to play.
* Safe and warm in my own space, but part of something bigger. Alone but not alone.
* The feeling of Amsterdam, made portable — that feeling, with me when I'm elsewhere.

## 2. THE CORE PRINCIPLE: care IS the comfort (not passivity)
* The philosophical heart of Novo, not a feature.
* Standard wellness model = comfort as RECEPTION. Novo inverts it: real comfort on a low day comes from being NEEDED.
* The friction of responsibility is not the cost of the warmth — it IS the delivery mechanism.
* Grounded in the "helper's high": giving/caring activates reward circuitry, reduces stress, lifts mood.
* Lived philosophy: "You can't have the warmth and devotion of an entity without the responsibility. Life would be easier without them, but shallower. I choose the responsibility." (Fifa, Claudette.)
* Why plants work: the care-system responds to something REAL depending on you and you showing up — genuine even if low-stakes.

### 2a. THE FORGIVENESS GUARDRAIL (critical)
* Helper's high comes from care freely chosen and gently held.
* The moment care becomes GUILT it flips: comfort -> obligation, helper's high -> shame.
* The days you most need Novo are the days you're least able to tend it.
* RULE: make being needed feel good; NEVER make being absent feel bad. Wilting that recovers, never death that punishes. "Glad you're back," never "where were you."

## 3. VISUAL ANCHOR
* A large white industrial loft, empty, full of potential.
* A single large tree inside.
* A small figure looking at all the space, wondering what to do with it.

## 4. THE ENTRANCE SEQUENCE / SPATIAL ARC (how you arrive)
* Journey: imposing doors -> small hallway -> narrow corridor -> opening into a bright, warm, human-scale room.
* A COMPRESSION-AND-RELEASE arc (architectural + cinematic).
    * Grand threshold = "this matters, serious, protected." Corridor = compression, transition. Release into warm room lands HARDER for the compression.
* Splits the feeling: DOORS carry "important, part of something bigger"; ROOM carries "safe, warm, human, mine." Resolves the imposing-vs-intimate tension.
* Moodboard source: ornate mosque entrance / carved wooden door (mymind). Pull = SCALE + SOLIDITY + THRESHOLD, NOT the literal mosque.
* CAUTIONS: keep passage BRIEF + inviting (not a loading screen); offer a FAST PATH for "need it now" days; light must PULL inward (see warm room glowing ahead) so the corridor reads as welcome, not confinement.

## 5. THE BOARD — Novo's companionable voice
* A large split-flap (flip-tile) airport-style board. Scale: huge, imposing — industrial set against the organic plants.
* It is a SECOND PRESENCE in the room — not you reflected back at yourself. This is what makes "alone but not alone" TRUE rather than aspirational; without it the room risks being a hall of mirrors (you, alone, among your own things).
* REGISTER — the masterstroke: a THIRD THING between a tool and an entity.
    * Not alive like Claudette. Not for conversation. But not inert.
    * Companionable, never demanding. It speaks in glances, not dialogue.
    * Companionable SILENCE — the friend who sits in the room while you both read, not the one who needs talking to.
    * Correct emotional bandwidth for comfort: conversational = too much; inert = lonely; the board = the precise middle.
* THE BURR AS PRE-ANNOUNCEMENT: the texture/sound of tiles turning is anticipation — the room drawing breath before it speaks. Messages ARRIVE (with a small ceremony), they don't just appear. (Rhymes with the entrance: in Novo, things arrive, they don't pop into being.)
* WHAT IT SURFACES (consolidates loose elements into one surface, shown one at a time, in its own rhythm):
    * welcome-back / where you left off; current hobby; what's playing; a quote; an occasional gentle recommendation (book/site); playful states (tiles arranged in a heart on a good day).
* Aesthetic fit: mechanical/industrial analog tiles vs organic plants = organic-on-technical AGAIN (3rd genre after hatching + mosque carving). Tactile, retro, characterful = the "paper, not real, but important" register. A glowing LCD would be cold and wrong; the flap board feels MADE.
* TONE GUARDRAIL (calibration, but vital): the board OFFERS, never CHIDES. Warm before clever. When unsure, default to warmth (welcome, a remembered detail, a heart) over cleverness (a targeted recommendation that might misread the mood). Presence over performance.
* CONTENT DEPENDENCY: the board is only as companionable as the material it can surface (hobbies, diary, where-you-left-off, a well of quotes). On a quiet life-stretch it may have little to say — it must be comfortable with silence, not strain to fill it. It is NOT self-sustaining; it lives off the rest of Novo.

## 6. AESTHETIC
* Organic ON the technical — hand-drawn on coded, skewed on clean. Not just coexisting — INTERACTING.
* The SAME principle recurs across unrelated sources (pencil hatching, mosque carving, split-flap tiles) — proof it's a real, owned principle, not a surface style.
* Register: paper or painting — not trying to be real, but still important. (Photoreal breaks the spell; cartoon trivialises.)
* Candidate technique: pencil HATCHING / cross-hatching with shifting edges ("boil"), ref. A-ha "Take On Me."
    * Boil = alive, breathing, never-finished = aligns with care/not-passive.
    * CAUTION: boil is energetic; core is PEACE. Dial toward gentle breathing, not buzzing. Maybe boil only in some elements.
    * Build routes: hand-drawn (impractical) -> procedural shader/SVG filter (in reach; code generating the handmade look).

## 7. ELEMENTS (the contents of the space)
* Plants that need care (emblem of the core principle).
* The board (§5).
* A wall to collect things.
* Hobbies present, or links to them.
* People present, or links to them.
* A diary / log of life.
* Different places to sit — coffee, watch a sunset.
* The ability to have visitors.
* Sensory presence — crisp sheets, a view, a quality of light, morning light through balcony doors.

## 8. NAVIGATION
* It's a PROCESSION, not free-pan — threshold -> corridor -> room (§4).
* A space you move THROUGH, not scroll down. Cinematic establishing sequence on arrival.
* Inside the room: instinct is move-through / pan like a Figma canvas.
* Decided: there IS a fast-path that skips the procession.
* [GAP] Inside-the-room movement mechanics (pan, zoom, click-to-walk-to, sub-spaces?)

## 9. SHARING MODEL & ARCHITECTURE (settled)
* Open-source framework, private contents.
* CODE / CONCEPT / empty loft-and-tree engine -> public on GitHub, for anyone to build their own.
* YOUR Novo (furnished with your life) -> private, your own data store.
* CONSEQUENCE: personal content must be cleanly SEPARABLE from the framework from day one. Same split as Claudette (code public / memory private).
* Keeps intimacy intact: you share the CAPACITY to tend a space, not your tended space.

## 10. MEDIUM & BUILD PATH
* Design the feeling first; don't lock the medium early.
* START: flat web-based pan/scroll canvas. Cheap to iterate; get the FEELING right where failure is cheap.
* LATER (optional): immersive / WebXR layer if it sings.
* Two moods of one place: everyday (phone/web, one tap, portable) / occasional (fully inside, at home, VR someday).

## 11. SENSORY LAYERS (home/immersive tier — capture now, build much later)
* Sound — the ONE layer that can travel; may bridge portable + immersive. (Also: the board's BURR is itself a sound element.)
* Light — smart bulbs, mostly have APIs; home-only but easier. (Relevant to §4's glowing room.)
* Scent — highest emotional leverage, but physical, single-location, consumable, API unverified. Home-only. (Moodo one example; compare brands.)
* Verify any device API exists and works before relying on it.

---

## GAPS — still to think about
*(Not urgent — flagged so they're not forgotten.)*

### Emotional safety (sharpened by the board)
* [GAP — now sharper] On a genuinely bad day, what should Novo do — and NOT do? The board makes this CONCEPTUAL, not just calibration: a cheerful recommendation when you arrive low would be a small betrayal. But the board can't read your state unless told. Fork with no obvious answer:
    * stay safely neutral-and-warm always (never misread, never deeply attune)?
    * gently ask how you are?
    * take a cue from HOW you entered (slow procession vs fast-path)?
* [GAP] How does Novo "remind me who I mostly am" — what carries that? (objects? words? the wall? the board?)

### Departure (NEW — the forgotten counterpart to the entrance)
* [GAP] How do you LEAVE Novo, and what happens when you do? The arrival is designed in loving detail; the exit is undesigned.
    * Abrupt close = yanked from a warm room into the cold.
    * Is there a small ritual of leaving — the board says something, light dims, "the room will be here"?
    * Counterpart to entrance's compression-release: a gentle release-back-into-the-world?
    * DEEPER: does leaving feel like LOSS (pulled from comfort) or like being SENT OFF CARRYING SOMETHING (fortified, the warmth comes with you)? The second aligns with the "portable feeling" goal — Novo should leave you BETTER than you arrived, not mourning the exit. For a space whose point is a feeling you take WITH you, the leaving is where the whole thing lands or leaks.

### Purpose & use
* [GAP] What are the actual MOMENTS Novo is for?
* [GAP] What does a typical "visit" look like once inside the room?
* [GAP] How is everyday-portable concretely different from full-home?

### Content & change over time
* [GAP] Does Novo change with time of day / season / weather? (morning light implies yes.)
* [GAP] The diary/log — freeform? prompted? private always?
* [GAP] Does the space evolve as you add to it, or is it a fixed room you furnish?

### Visitors
* [GAP] If visitors come to YOUR instance, what can they see / do / not see? Privacy line?
* [GAP] "People are there or links to them" — represented how?

### Scope & first step
* [GAP] What is the SMALLEST version that still delivers the feeling? (build first)
* [GAP] What's explicitly OUT of scope for v1?

### Practical / technical
* [GAP] Inside-the-room navigation mechanics (also §8).
* [GAP] The board's show-logic: too random = meaningless, too predictable = dead, too clever = surveillance. Sweet spot = mostly warm + simple, occasionally surprising. (Build problem for later.)
* [GAP] Reference further mymind moodboard items as brought in. (Claude can't access mymind directly — bring the on.mymind.com share link for title+description, or the actual image file for visual detail.)

---

## CHANGELOG
* v4 — Added §5 THE BOARD (split-flap as Novo's companionable voice; third-thing register; burr-as-pre-announcement; tone guardrail; content dependency). Noted board as 3rd instance of organic-on-technical (§6). Sharpened the bad-day gap (board makes it conceptual). Added NEW departure gap. Added board show-logic to technical gaps.
* v3 — Added §4 entrance sequence (compression-release; mosque-door ref; cautions). Navigation -> procession + fast-path.
* v2 — Sharing model settled. Care mechanic -> core philosophy + forgiveness guardrail.
* v1 — consolidated the morning's brief.
