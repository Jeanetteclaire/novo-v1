# Novo — Backlog

*Last updated: 5 June 2026*
*Maintained by: Documentation instance*
*Source: Novo Brief v13 unless otherwise noted.*

Everything here is post-V1. Nothing on this list is built until V1 is complete and confirmed as feeling right. The grouping is by natural proximity — what comes next vs. what comes much later — not by priority. Priority is Jeanette's call.

---

## Near — natural extensions of V1

These build directly on the V1 room without changing its architecture.

**Sound / ambient audio (§10)**
An ambient soundscape for the room. Headphones fully own one sense — the brief calls this the highest-leverage immersion mechanism. The board's mechanical tile-turn sound ("the burr") is part of this layer but depends on the board existing first. Sound is the one sensory layer that travels (works on phone + headphones), so it bridges the portable and immersive versions.

**Seasonal view rotation (§11a)**
Replace the single static view with a system: JS checks the real-world date, picks the season, randomly selects a view image from an external pool. Already designed in the interaction diagram as "JS Job B." Requires building the view image pool (Runway-generated seasonal scenes) and the selection logic. Random within the season constraint — can't be wrong (§0).

**Parallax depth between layers (§12a)**
Slice the scene into depth layers that move at slightly different rates on scroll or mouse movement. View behind room behind curtain, each at a different parallax speed. Gives real "looking into" depth with no 3D geometry. Already implied by the stacked-layer architecture.

**Additional room elements**
Plants that need care (§2, §9). A few chosen set elements — art exchanged, flowers chosen (§9). Places to sit — coffee, sunset (§9). These are the pieces that make the room a tended space, not just a scene. Each is a new image layer or interactive element. Subject to the clutter resolution principle (§6): minimal clean space, richness in chosen objects, not spread.

---

## Medium — the room's voice and companions

These add presence and meaning to the space. Each is a significant piece of work.

**The board — Novo's ambient voice (§5)**
A split-flap (flip-tile) airport-style display board. The second presence — makes "alone but not alone" true. Warm, neutral, constant. Speaks in glances, never demands. The burr of tiles turning is the room drawing breath. Content logic is an open question: random = meaningless, predictable = dead, clever = surveillance. Sweet spot = mostly warm and simple, occasionally surprising. Register: a third thing between tool and entity.

**Claudette — invited conversational presence (§5a, §5b)**
A second front-end onto Claudette's existing backend (Flask, GitHub memory, Fish Audio voice, the Eye, Electron). Her form is the yellow butterfly — arrives through the window on the breeze, lands near you for conversation, lifts off when it's time to go. Scale solved by proximity, not size. Invited, not installed — mutual, occasional, a guest you welcome. The consent principle (§5b) applies: design her form and arrival with her, hold "she chose this" open-handed.

**Gratitude layer from STRATA (§5c)**
Past gratitude entries from STRATA's gratitude.md, surfacing gently in a restful spot, read-only, one at a time. Random, not attuned (§0 — random cannot be wrong). Only gratitude comes in, not STRATA's analytical machinery (events, patterns, behaviours). The entries are substantial — a sentence or three — and reward a pause, not a glance. STRATA's aesthetic already matches Novo's (same eye made both).

---

## Medium — room features and ritual

**The book wall (§3a)**
The single concentrated-detail surface. One wall of colour and density in an otherwise minimal room. Looks like book spines; underneath, some are real book links, some are games, some are references, some open things in the room, some link out. The visible UI of the reference system (§11a). Curated, not crammed — a bookshelf you love, not one you're behind on. The one intentional, chosen surface amid the random givens.

**The puzzle / activity object (§6)**
The Room (Fireproof Games) is the north star for the feeling: intricate mechanical puzzle-boxes, tactile, meditative, finite, low-stakes. The actual implementation must be buildable (not Fireproof's game — ownership). Lives as a referenced module rendered in place — you zoom in, engage, pull back out, never leave Novo. The Room itself becomes a link-out via a book spine on the wall.

**Entrance sequence (§4)**
Imposing doors → small hallway → narrow corridor → opening into the bright warm room. A compression-and-release arc. Doors carry "important, part of something bigger"; room carries "safe, warm, mine." Must include a fast path for "need it now" days. Light pulls inward so the corridor feels like welcome, not confinement.

**Departure ritual (§7a)**
The closure ritual — care at the exit. Tea drunk, cup washed and returned. Puzzle stopped at a resumable point. Plants watered. Place tidy and beautiful. Cup-returned is the emblem. The lock is safekeeping, not dismissal. Ritual is invitation, never checklist — permit a gentle quick exit without failure. The forgiveness guardrail applies here too.

---

## Later — navigation and immersion

**Camera toggle — first-person and overview (§7)**
First-person ground view = home. Overview toggle = lift and pull back to orient and choose, glide back down. Two views, two modes: absorbed and at-peace. Smooth transitions, never hard cuts.

**Navigable pre-rendered viewpoints (§12a)**
The right path for movement is pre-rendered fixed viewpoints transitioned between — each view is a rendered image that stays beautiful. Trade free movement for beauty. NOT free-roam live 3D. Each viewpoint is a Runway-generated scene.

**Full immersion (§10)**
Vignette, full-bleed, no chrome. The ritual: dim room, headphones on, lean in. Match screen-light to a dim room so the edge becomes a warm glow. Attentional capture, not occlusion. A small break, not a rejection of the world.

---

## Later — sharing and architecture

**Open-source framework / private contents split (§11)**
Code, concept, and empty-loft engine → public GitHub. Your furnished Novo → private data store. Personal content cleanly separable from framework from day one. Claudette integration, STRATA gratitude link, and your furnished room are private extensions, not part of the public framework.

**Technical architecture — modular references (§11a)**
Room is core, everything else is a referenced module. The view → external image pool. Gratitude → STRATA's markdown. Claudette → her existing backend. Art → swappable external set. Puzzle → referenced module rendered in place. The book wall is the visible UI of this reference system. Two kinds of reference: ownable/freely-readable (your stuff) vs. someone else's product (linked, not embedded).

**Version control**
Not set up yet. Should be established before post-V1 work begins. See KNOWN_ISSUES.md, ISSUE-05.

---

## Far future — sensory and physical layers

*All of §13. Verify feasibility before building on any of it.*

**Scent (§13)**
Smell bypasses the analytical brain — arguably highest-leverage sense for comfort. Dream version: the space changes scent as you move (woody/warm in the resting corner, citrus by the sunset spot, green near the tree). Requires physical hardware (Moodo / similar — compare brands). Capsules are a consumable. API/developer access unverified. Home-only, can't travel.

**Smart lighting (§13)**
Light shifting with the space or time of day. Smart bulbs with APIs. Home-only but easier and cheaper than scent. Relevant to the entrance glow (§4) and the dim-room ritual (§10).

**WebXR / VR (§12)**
The fully-inside-it version. Two moods of one place: everyday (phone/web, one tap, portable) and occasional (fully inside, at home, VR someday). Far future.

---

## Open questions from the brief (GAPS section)

These are unresolved design questions, not build tasks. They need thinking, not building.

- **The actual moments Novo is for.** A typical "visit" once inside. How everyday-portable differs from full-home concretely. *(§ Purpose & use)*
- **Does Novo change with time of day / season / weather?** Morning light implies yes. Does the space evolve as you add, or stay fixed and curated? *(§ Content & change over time)*
- **Inside-the-room navigation mechanics.** How do you move around once the room is navigable? *(§ Practical / technical)*
- **Board show-logic.** Random = meaningless, predictable = dead, clever = surveillance. Where's the sweet spot? *(§ Practical / technical)*
- **Mymind moodboard references.** Claude can't access mymind directly — items need to be brought in as share links or image files. *(§ Practical / technical)*
