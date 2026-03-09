# OpenFab Website — Design Specification

**Version:** 0.1 (Draft)  
**Date:** 2026-03-08  
**Author:** Edna Mode 👓✨

---

## 1. The Trinity

These 3 pages represent the organizational Trinity:

| Entity | Role | Symbol | Page Purpose |
|--------|------|--------|--------------|
| **Syntonie** | Head | ☂️ | Governance, legal, vision, commons |
| **Politype** | Heart | 🫰 | Democracy prototyping, game-based governance |
| **OpenFab** | Hands | 🧰 | Makerspace, tools, physical space |

---

## 2. Shared Design System

### 2.1 The 4D Concept (Website = Physical Space)

- **Scrolling = Walking** through the makerspace
- One-pager per entity, linking to each other
- Navigation: Fixed left sidebar (the wall) — strong, immovable, never collapses

### 2.2 Grid System

| Property | Value |
|----------|-------|
| Base unit | 59×59cm tile (1:1 square ratio) |
| Syntonie | Visible blueprint grid |
| OpenFab/Politype | Invisible grid, same coordinate system |
| Axis labels | For physical item location (collaboration with Steve) |

### 2.3 Layout Mapping (Scroll Journey)

| Scroll Position | Physical Analog | Content |
|-----------------|-----------------|---------|
| Hero/Top | Lasersaur zone | Entry point, main message |
| Upper middle | Kitchen, toilets | Practical info, utilities |
| Middle | Central open space | Core content, work areas |
| Lower middle | Storage, back area | Resources, archives |
| Footer | Garden | Future potential, contact |

### 2.4 Color System (TBD)

- [ ] Zone-based color coding (link to Politype playground concept)
- [ ] Specific shade definitions (NOT generic names — "royal blue", "lapis lazuli")
- [ ] Coherence: color = meaning (blue = info, orange = warning, red = action)

---

## 3. Page Specifications

### 3.1 Page A: OpenFab (Makerspace)

**URL:** `openfab.be` (assumed)  
**Vibe:** Maker-focused, hands-on, playful

#### ✅ Known

| Element | Status |
|---------|--------|
| Grid system | 59×59cm tiles, invisible |
| Scroll mapping | Homepage = Lasersaur → workspace → garden |
| Left sidebar | Fixed "the wall" — tools, navigation |
| Coordinate system | Tiles labeled for item location |
| Vibe | Playful, maker, hands-on |

#### ❓ To Decide

| Element | Question |
|---------|----------|
| Hero content | What's the main call-to-action? (Visit? Join? Learn?) |
| Zone colors | Which colors for which areas? |
| Tool icons | Visual representation of wall/shelves? |
| Photo strategy | Real photos of space vs. illustrations? |
| Membership info | Pricing, how to join, induction process? |
| Equipment list | Which machines/tools to showcase? |
| Links | To Syntonie? To Politype? Both? |

---

### 3.2 Page B: Syntonie (Governance)

**URL:** `syntonie.be` (assumed)  
**Vibe:** Formal, governance-focused, shelter/commons

#### ✅ Known

| Element | Status |
|---------|--------|
| Grid system | 59×59cm tiles, **visible** (blueprint aesthetic) |
| Visual identity | Shelter/umbrella, immaterial protection |
| Logo elements | Blue vertical lines = pillars, grid = blueprint |
| Vibe | Formal, community-based, protective |
| Philosophy | "Immaterial shelter" — community, commons |

#### ❓ To Decide

| Element | Question |
|---------|----------|
| Hero content | What defines Syntonie in one line? |
| Governance structure | How to display board/members? |
| Documents | Where to link statutes, reports? |
| Visual tension | Blueprint grid density — subtle or prominent? |
| Color palette | Syntonie blue + ? (what accents?) |
| Links | To OpenFab? To Politype? Both? |
| Contact | General inquiry vs. specific roles? |

---

### 3.3 Page C: Politype (Democracy Prototyping)

**URL:** `politype.be` (assumed)  
**Vibe:** Process-focused, game-based, experimental

#### ✅ Known

| Element | Status |
|---------|--------|
| Name | Politype (from "Polity" + "Type") |
| Role | Heart of the Trinity |
| Focus | Prototyping democracy, game-based governance |
| Stance | Party-agnostic, methodology lab |
| Intellectual foundation | Plurality book (Weyl + Tang) |
| Vibe | Experimental, process, playful rigor |

#### ❓ To Decide

| Element | Question |
|---------|----------|
| Hero content | How to explain "democracy prototyping" simply? |
| Grid visibility | Visible (like Syntonie) or invisible (like OpenFab)? |
| Game examples | Show prototypes? Link to demos? |
| Color palette | Distinct from Syntonie (but related)? |
| Interactive elements | Any voting/participation demos on-page? |
| Links | To Syntonie? To OpenFab? To Plurality? |
| Typography | More playful (OpenFab) or formal (Syntonie)? |

---

## 4. Cross-Page Decisions

### 4.1 Navigation Between Pages

| From ↓ / To → | OpenFab | Syntonie | Politype |
|---------------|---------|----------|----------|
| **OpenFab** | — | ? | ? |
| **Syntonie** | ? | — | ? |
| **Politype** | ? | ? | — |

### 4.2 Shared Elements

- [ ] Logo placement and size
- [ ] Footer content (all pages same or customized?)
- [ ] Mobile responsiveness — does "wall" become drawer?
- [ ] Color tokens — shared CSS variables?

### 4.3 Content Strategy

- [ ] Tone: How much humor per page?
- [ ] Language: French? English? Both?
- [ ] Photos: Who provides space photography?

---

## 5. Immediate Questions for Next Session

1. **Which page to mock up first?** (OpenFab, Syntonie, or Politype)
2. **Hero line for each** — what's the one-sentence pitch?
3. **Grid visibility** — Politype: visible or invisible?
4. **Color palette starter** — any existing brand colors to respect?
5. **Photo access** — do we have photos of OpenFab space?

---

## 6. Technical Notes for Claude Code

- Grid = CSS Grid with 59px base unit (scaled from 59cm)
- Left sidebar = `position: fixed; left: 0; top: 0; width: [sidebar-width]`
- Scroll-snap for section-based navigation (optional)
- CSS custom properties for theming:
  ```css
  :root {
    --tile-size: 59px;
    --sidebar-width: 280px;
    --color-zone-lasersaur: #XXX;
    --color-zone-kitchen: #XXX;
    --color-zone-workspace: #XXX;
    --color-zone-garden: #XXX;
  }
  ```

---

*No capes. Ever.*
