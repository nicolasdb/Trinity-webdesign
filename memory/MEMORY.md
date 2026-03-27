# Trinity Project Memory

## Project Identity (Always Relevant)
- **Trinity**: Ecosystem of 3 entities (Syntonie, Politype, OpenFab) with shared vision but distinct roles
- **Repository Type**: Design specifications + Hugo sites (three separate entities, each with distinct identity)
- **Primary Deliverable**: Three websites + institutional credibility pages
- **Current Focus**: Syntonie fog-of-war homepage (maker-friendly entry experience) + /about institutional page (validators)

## Entity Positioning (LOCKED 2026-03-11)

**Core insight: None of the three entities DO the thing. They all ENABLE.**

| Entity | Verb | Role | Audience |
|--------|------|------|----------|
| Syntonie | **permet** | Legal shelter, assets, strategic continuity | Erasmus agencies, Ixelles, institutional partners (secondary) + makers (primary) |
| OpenFab | **équipe** | Right tool for the right job. Makerspace as kitchen. | Local makers, creative technologists |
| Politype | **prototype** | Digital democracy + game-based governance. WIP. | Civic activists, governance practitioners |

### KILLED Framings (Do Not Revert)
- ❌ Head/Heart/Hands metaphor in public copy (internal only)
- ❌ "Trinity" word in user-facing content (too loaded)
- ❌ "Là où les idées deviennent réelles" (generic makerspace)
- ❌ "Vous avez le cœur, il vous manque les mains" (patronizing)
- ❌ Cold contact forms or phone numbers on Syntonie site

## Core Values (Schwartz Dimensions)
Auto-determination, Stimulation, Humanity, Security (from community) — invariants across all three entities

---

## ACTIVE: Syntonie Fog-of-War Site (2026-03-27)

**See**: `project_syntonie_fogofwar.md` for complete details.

**Status**: Hugo scaffolding complete, all 11 recipe blocks built, recipes.js + topics.json wired, builds cleanly.

**Architecture**:
- **Primary `/`**: Fog-of-war homepage (warm cream #faf8f4, input field, 5 recipes)
  - Target audience: Curious explorers, builders with non-linear thinking
  - Experience: Input field invites curiosity → reveal relevant recipes
- **Secondary `/about`**: Institutional page (dark #0f1216, hero/vision/role/trinity/contact)
  - Target audience: LEBIJ, Ixelles, validators
  - Experience: Linear institutional narrative, credibility signals
  - **Status**: TODO — move old index.html content to /about page

**5 Recipes**:
1. `shelter` — ASBL/governance/structure (trigger: gouvernance, asbl, légal, cadre, financement)
2. `inclusion` — neurodiversity/accessibility (trigger: neurodiversité, inclusion, adhd, invisible, allo-ia)
3. `constellation` — making/fablab (trigger: fablab, maker, making, openfab, makerspace)
4. `values` — open source/philosophy (trigger: open source, communs, indépendant, imparfait)
5. `about` — fallback narrative (trigger: any input > 2 chars)

**Git Branch**: `syntonie-fogofwar` (active)

**Design Thinking Outcomes (2026-03-27):**

**Core Philosophy:**
- **Three-beat arc**: Recognition (surprised resonance) → Community (signal they're not alone) → Action (clear path to contact)
- **Tardis feeling**: Simple interface hiding adaptive complexity; cards reveal what user needs, when they need it
- **Vocabulary scoping**: Each recipe loads its own ontology/semantic preset; UI stays simple, data layer adapts

**Input Field Design:**
- Placeholder: "What brought you here?" / "Qu'est-ce qui t'amène?"
- Keywords below: neurodiversité, habitat, gouvernance, making, inclusion, autonomie, open source (clickable)
- Keywords serve dual purpose: visual suggestion + quick-access shortcuts

**Card Interaction:**
- Click keyword → input clears → card slides in from bottom (400-600ms ease-out)
- Sidebar nav updates simultaneously (reflects recipe context)
- Fresh keywords appear (filtered by recipe vocabulary scope)
- Card structure: Headline + intro → "CE QUI EST PARTAGÉ" → "CE QUI RESTE À VOUS" → contact signal

**Semantic Architecture:**
- Recipe has `primary_vocabulary` (adapts keyword suggestions)
- Recipe has `related_recipes` (for "weird neighbor" tangent suggestions)
- Recipe has `action_language` (recipe-specific CTA)
- Vocabulary preset loads on recipe entry; card content from pantry (FR/EN)

**Testing Plan:**
- Phase 1: You (internal validation)
- Phase 2: Members (3-5 Syntonie collaborators)
- Phase 3: Outsiders (5-7 target makers)
- Success signal: User reaches call-to-action section and pauses (hesitation = resonance)

**Key Principles** (Do Not Violate):
- Radical absence: `display:none`, never `opacity:0`
- Warm palette: full contrast, no low-opacity text
- Autocomplete on 2+ chars (proposal)
- Vocabulary-scoped keywords (not all at once)
- Keyboard navigation: ↑↓Enter in dropdown
- **NEW:** Three-beat arc governs all interactions
- **NEW:** Sidebar nav always fixed, updates in context of recipe (never collapses desktop)
- **NEW:** Language toggle persists (FR/EN switching via existing pantry system)

---

## ARCHIVED: Institutional Site Design

**See**: `project_syntonie_institutional_archived.md` for reference.

Status: Design complete (De Stijl composition, dark palettes for all 3 entities), Hugo layouts exist but will become `/about` page. Pentool artboard details, section specs, typography locked.

---

## Key References
- `trinity-charter-draft.md` — Mission/philosophy
- `_bmad-output/audience-content-strategy.md` — Full strategy with resolved questions
- `assets/floorPlan.svg` — OpenFab physical space
- plurality.net — Politype intellectual lineage
- Polis 2.0 — opinion mapping inspiration

---

## Feedback
- [Neurodiversity Language Guidance](feedback_language_neurodiversity.md) — Avoid clinical terms; address non-diagnosed curiosity-driven users
