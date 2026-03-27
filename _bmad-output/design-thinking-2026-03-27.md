# Design Thinking Session: Syntonie Fog-of-War Homepage

**Date:** 2026-03-27
**Facilitator:** Nicolas
**Design Challenge:** UX/UI Fine-Tuning for Recipe Discovery & Card Interaction

---

## 🎯 Design Challenge

**Syntonie fog-of-war homepage:** Transform recipe discovery from competing navigation + input field into an integrated, adaptive interface where sidebar becomes dynamic table-of-contents, cards animate in/out of hero space as users explore, and semantic relationships guide deeper discovery paths.

**Core Tensions to Resolve:**
- Sidebar anchor + input field compete for cognitive load → Use nav as adaptive recipe ToC
- Cards below fold feel like "page navigation" → Bring into hero with flowing animations
- Keyword arrays only enable autocomplete → Add recipe-recipe suggestions + breadcrumb trails

---

## 👥 EMPATHIZE: Understanding Users

### User Insights

**Who they are:** Curious explorers and builders with non-linear thinking styles. Not seeking clinical support — they are self-directed, creative, and arrive at Syntonie via their own intuitions. They may not have a precise word for what they're looking for yet.

**What they bring:**
- A vague intention ("I want to build something, but I don't know how to name it yet")
- Low patience for friction, but high appetite for discovery
- Comfort with exploration if affordances are clear and forgiving
- Preference for visible structure without labels that box them in

**What they don't bring:**
- A clear "search query" — they're browsing in intention-space, not keyword-space
- Trust in forms or cold institutional language
- Energy for onboarding or instructions

**Language:** FR primary, EN secondary. Both must be equally natural, not translated-feeling.

### Key Observations

1. **The empty input field is hostile.** A blank cursor says "you already know what to type." Most explorers don't — yet. The placeholder must carry the nudge.

2. **Navigation competes for attention.** A sidebar listing fixed sections (01, 02, 03…) implies a linear document. But Syntonie's content is relational, not sequential. The sidebar should *reflect* where the user is, not announce where to go.

3. **Clickable words > buttons.** Buttons signal "official action." Clickable words feel like invitation. The tonal difference matters for non-linear thinkers who don't want to commit.

4. **Breadcrumbs create pressure.** Displaying history makes some users self-conscious ("I went the wrong way"). Soft fog-of-war: words that were already clicked can feel slightly "known" without being labeled as visited.

5. **Recipes feel like destinations, not conversations.** They should feel more like: "here's what connects to that word you typed." The card *responds* to the user's curiosity, it doesn't broadcast.

6. **Multilanguage must be invisible-but-present.** Same architecture as pantry: FR/EN toggle exists, but content feels native in both, not translated.

### Empathy Map Summary

| | What They **SAY** | What They **THINK** | What They **DO** | What They **FEEL** |
|---|---|---|---|---|
| **Arriving** | "What is Syntonie?" | "Is this for me?" | Scan visually before reading | Cautious curiosity |
| **Input Field** | *(nothing yet)* | "What should I type?" | Hover, hesitate, read placeholder | Mild friction if empty |
| **Topic Words** | "Oh, that one!" | "That word is mine" | Click word → recipe loads | Relief, recognition |
| **Recipe Cards** | "There's more here" | "Does this connect to X?" | Scroll, click related words | Engaged, exploring |
| **No Match** | "Nothing came up" | "I was wrong to try" | Either re-type or leave | Deflation |
| **Returning** | *(no return state yet)* | "Did I see this?" | Rely on memory or re-explore | Slight cognitive overhead |

---

## 🎨 DEFINE: Frame the Problem

### Point of View Statement

**A curious maker arrives at Syntonie with a vague intention but no precise search query. They need to discover whether Syntonie resonates with *their* worldview in under 2 minutes, without feeling like they're filling out a form or reading institutional copy.**

**They succeed when they feel: (1) surprised recognition ("they see me"), (2) community signal ("I'm not alone"), and (3) momentum toward first contact ("I want to reach out").**

### How Might We Questions

1. **How might we create an input field that invites curiosity without being prescriptive?**
   - The placeholder carries all the nudge (no header, no instructions)
   - Vocabulary adapts based on entry recipe (governance language vs maker language)

2. **How might we surface complexity progressively so users feel the "Tardis moment" (bigger on the inside)?**
   - Cards animate in to reveal information at the right time
   - Related recipe suggestions appear only *after* primary recognition
   - Each animation beat has an informational purpose, not decorative

3. **How might we make the three-beat arc (Recognition → Community → Action) feel natural and inevitable?**
   - Recognition: Card loads with vocabulary that mirrors their mental model
   - Community: Related recipe appears as tangential invitation, filtered through their entry vocabulary
   - Action: Single, recipe-specific call-to-action (not generic contact form)

4. **How might we adapt vocabulary and tone by recipe entry without feeling like five different websites?**
   - Load ontology/vocabulary preset based on detected recipe resonance
   - Keep the three-beat structure consistent while vocabulary shifts
   - Sidebar nav reflects their entry point + related pathways

### Key Insights

- **Three beats is the limit.** Shorter = no hook. Longer = lose them. Three-beat arc mirrors Trinity's structure (three entities).
- **Semantic relationships enable vocabulary scoping.** Once we know entry recipe, we serve only the vocabulary that resonates in that context.
- **First contact doesn't mean completion.** Success = user feels recognized, finds community, and wants to reach out. Not "visited all recipes."
- **Animations serve information design.** Cards, transitions, and visual updates communicate: "here's what matters *for your question* right now."
- **Clickable words signal shared language.** Buttons feel like commands. Words feel like invitation to conversation.

---

## 💡 IDEATE: Generate Solutions

### Selected Methods

**Hybrid Approach:**
- **Direct Design** (user already has a clear visual direction)
- **Constraint-Based Ideation** (work within existing pantry components)
- **Progressive Enhancement** (start MVP, grow with content)

### Generated Ideas

**Winning Concept: Conversational Invitation with Keyword Shortcuts**

**Input Field Design:**
- Placeholder text: "What brought you here?" / "Qu'est-ce qui t'amène?"
- Visual: Warm vertical accent bar on left (brand color)
- Below input: Row of clickable keyword chips (neurodiversité, habitat, gouvernance, making, inclusion, autonomous, open source)
- Keywords serve dual purpose: (1) visual suggestion of what Syntonie cares about, (2) quick-click entry points for users who prefer not to type

**Card System:**
- Pull cards from existing pantry (FR/EN already built)
- Each card references semantic vocabulary scope (ontology preset loaded on recipe selection)
- Cards animate in to reveal three-beat arc: Recognition → Community → Action
- Language/imagery adapts based on entry recipe, but card structure remains consistent

**Semantic Architecture (Data Layer):**
- Recipe has `primary_vocabulary` (neurodiversité, habitat, gouvernance, making, inclusion, autonomous, open source...)
- Recipe has `related_recipes` (cross-links for "weird neighbor" community signal)
- Recipe has `action_language` (recipe-specific CTA like "Let's structure this" vs "Let's make this")
- Vocabulary preset loads on recipe entry; UI remains constant

**Scalability:**
- Content grows over time (more projects, pictures, historical examples)
- Semantic layer supports expanded vocabulary without UI redesign
- Language toggle (FR/EN) persists; card content switches via pantry system

### Top Concepts

**Concept 1: MVP — Input + Pantry Cards + Semantic Linking (SHIP THIS)**
- Simple: input field + keywords + pantry cards
- Smart: semantic vocabulary scoping in data layer
- Scalable: grows naturally as content added
- Status: Ready to prototype

**Concept 2: Future — Visual Semantic Graph (LATER)**
- Visualize recipe relationships as web/network
- Interactive path-following between recipes
- Post-MVP when content volume justifies it

**Concept 3: Future — Content Wall (LATER)**
- Gallery of projects/pictures showing real Syntonie stories
- Adds visual weight and proof of work
- Scaffolds the "bigger on the inside" feeling as content grows

---

## 🛠️ PROTOTYPE: Make Ideas Tangible

### Prototype Approach

**Low-Fidelity First:** Use existing pantry components (cards already designed) + Hugo templating to wire the semantic flow. No new design work needed—focus on interaction choreography.

**Build Order:**
1. Input field + keyword chips (HTML/CSS, static)
2. Keyword click handler (JavaScript: clear input, load recipe, display fresh keywords)
3. Card animation from bottom (CSS transitions)
4. Sidebar nav update (synchronized with card load)
5. Language toggle (persist selection, switch content)

### Prototype Description

**User Journey (Sequence):**

1. **Landing State:**
   - Input field at top with placeholder "What brought you here?" / "Qu'est-ce qui t'amène?"
   - Keyword chips below (neurodiversité, habitat, gouvernance, making, inclusion, autonomie, open source)
   - Empty space below for cards
   - Sidebar shows: ACCUEIL → VISION → NOTRE RÔLE → L'ÉCOSYSTÈME → CONTACT

2. **On Keyword Click (e.g., "gouvernance"):**
   - Input field clears
   - Card slides in from bottom (animation: 400-600ms ease-out)
   - Sidebar nav updates to reflect recipe context (still shows institutional structure, but "in context" of governance)
   - Fresh keywords appear (filtered by governance vocabulary scope)

3. **Card Content (Three-Beat Arc):**
   - **Beat 1 — Recognition:** Card headline + intro (e.g., "La structure est à nous. Le projet est à vous.")
   - **Beat 2 — Community:** Recipe description + "CE QUI EST PARTAGÉ" section (signals what Syntonie shares, what others in this space care about)
   - **Beat 3 — Action:** "CE QUI RESTE À VOUS" section (what user keeps control of) + implied next step (hover/click for contact?)

4. **Keyword Refresh (Related Recipes):**
   - After card loads, keywords adapt to show related explorations
   - Example: User in "gouvernance" recipe sees suggestions: "fablab", "making", "inclusion" (weird neighbors in governance context)
   - Clicking new keyword follows same flow: clear, load, animate, refresh

5. **Sidebar Behavior:**
   - Always anchored (left, fixed, never collapses on desktop)
   - On mobile: hamburger menu or toggleable nav (TBD)
   - Updates simultaneously with card load to show user's position in Syntonie map

### Key Features to Test

- [ ] Input field invitation (does placeholder feel like nudge, not instruction?)
- [ ] Keyword click responsiveness (is clearing input + loading card intuitive?)
- [ ] Card animation timing (does slide-in from bottom feel like discovery, not intrusion?)
- [ ] Vocabulary adaptation (do fresh keywords feel relevant to recipe context?)
- [ ] Three-beat clarity (does user feel Recognition → Community → Action in sequence?)
- [ ] Language toggle persistence (FR/EN switches smoothly without page reload?)
- [ ] Sidebar sync (does nav update feel connected to card load, not jarring?)
- [ ] Call-to-action clarity (is path to contact obvious after card exploration?)

---

## ✅ TEST: Validate with Users

### Testing Plan

**Testing Approach: Fog-of-War Iteration** (observe in the field, refine quickly, don't over-specify upfront)

**Test Phases:**

**Phase 1: You (Internal Test)**
- Goal: Does the interaction feel natural to build?
- Method: Spend 15 min with prototype, follow your own user journey
- Observe: Does the three-beat arc land emotionally? Does vocabulary adaptation signal feel clear?
- Adjust: Fix obvious friction before next phase

**Phase 2: Syntonie Members (Collaborators)**
- Goal: Do people aligned with Syntonie's mission resonate?
- Participants: 3-5 ASBL members, collaborators, people who know the mission
- Method: Unmoderated walkthrough (give no instructions, watch what they do)
- Observe:
  - What keyword do they click first?
  - Do they read the card fully or skip?
  - Do they feel recognized by the language?
  - Do they explore related keywords or exit?
  - Do they look for contact/next step naturally?
- Capture: Quick notes on emotional reactions, where they hesitate, what surprised them

**Phase 3: Outsiders (Target Makers)**
- Goal: Do curious builders without Syntonie context resonate?
- Participants: 5-7 makers/builders (neurodivergent preferred, mix of expertise)
- Method: Moderated session (ask them to think aloud)
- Observe: Same as Phase 2, plus—
  - Do they *understand* Syntonie's value prop from the card?
  - Do they feel "this is for me" or "this isn't for me"? (Binary, not scaled)
  - What word would they have typed instead of the suggested keywords?

**Success Signal (Fog-of-War):** User reaches the call-to-action section and pauses—not to leave, but to consider reaching out. That hesitation = resonance.

### User Feedback

_To be captured during testing phases_

**What to listen for:**
- Moments of surprise recognition ("oh, they get it")
- Questions about what Syntonie actually *does* (clarity issue)
- Interest in related keywords (curiosity signal)
- Whether they felt alone or part of community

### Key Learnings

_To be synthesized after testing_

**Questions to answer:**
- Did the three-beat arc create emotional progression, or did it feel flat?
- Did vocabulary adaptation feel smart or invisible (both ok, just different)?
- Should sidebar nav change more visibly, or is subtle update enough?
- Do we need a clearer "contact" affordance, or is it obvious?
- Which recipes resonate most? (informs future content priorities)

---

## 🚀 Next Steps

### Refinements Needed

**From Design Thinking → Implementation:**

1. **Input Field & Keywords**
   - Finalize placeholder text (EN: "What brought you here?" | FR: "Qu'est-ce qui t'amène?")
   - Confirm keyword list + order (currently: neurodiversité, habitat, gouvernance, making, inclusion, autonomie, open source)
   - Define styling: accent bar color, font size, spacing

2. **Card Animation & Choreography**
   - Confirm slide-in timing (propose: 400-600ms ease-out)
   - Define card entry position (below viewport, slides up to where?)
   - Confirm sidebar nav sync (simultaneous, or staggered?)

3. **Semantic Vocabulary Scoping**
   - Map each recipe to its vocabulary preset (governance vocab ≠ making vocab)
   - Define related recipe connections (which recipes link to which?)
   - Build data structure (JSON/YAML for recipes + vocabularies)

4. **Language Toggle & Persistence**
   - Confirm toggle placement (sidebar? top right?)
   - Confirm persistence method (localStorage? session?)
   - Ensure all card content switches between FR/EN

5. **Call-to-Action Path**
   - Define contact affordance (button? link? form?)
   - Ensure it appears after three-beat arc completes
   - Keep friction minimal (no multi-step forms)

### Action Items

**Immediate (This Sprint):**
- [ ] Build prototype with HTML/Hugo + existing pantry cards
- [ ] Wire keyword click handler (clear input → load recipe → refresh keywords)
- [ ] Implement card slide-in animation (bottom → visible area)
- [ ] Sync sidebar nav update with card load
- [ ] Test Phase 1: You — walkthrough and adjust obvious friction

**Next (After Internal Test):**
- [ ] Schedule Phase 2 testing with 3-5 Syntonie members
- [ ] Gather feedback; identify patterns
- [ ] Make quick adjustments based on member feedback

**Following (After Member Test):**
- [ ] Schedule Phase 3 testing with 5-7 target makers (outside network)
- [ ] Gather feedback; synthesize learnings
- [ ] Determine if major pivot needed or iterate forward

**Content Growth (Parallel):**
- [ ] Prepare expanded card content (stories, projects, images from Syntonie history)
- [ ] Define how content scales (does sidebar nav expand? New recipe cards?)
- [ ] Plan multilingual content strategy (current: FR primary, EN fallback; scale to full parallel?)

### Success Metrics

**Phase 1 (Internal Test):**
- ✓ Prototype builds without errors
- ✓ Interaction feels natural (no major friction points)
- ✓ Three-beat arc creates emotional arc (you feel it)

**Phase 2 (Member Test):**
- ✓ Members recognize themselves in at least one recipe
- ✓ No confusion about what Syntonie *does*
- ✓ Curiosity about related keywords (some click to explore)
- ✓ Natural interest in contact/next step

**Phase 3 (Outsider Test):**
- ✓ Makers without Syntonie context resonate with at least one recipe
- ✓ Clear sense of "this is for me" or "this isn't for me" (binary clarity)
- ✓ Feeling of being not alone in their journey (community signal lands)
- ✓ At least 1-2 people want to reach out after exploration

**Long-Term (Content Growth):**
- ✓ Semantic vocabulary system supports 3+ new recipes without UI redesign
- ✓ Content grows as Syntonie history is added (projects, images, stories)
- ✓ FR/EN parity maintained across all content

---

_Design Thinking Workflow in progress..._
