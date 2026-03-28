# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

**The Trinity** is an ecosystem of three entities with shared vision but distinct roles:

- **Syntonie** (☂️ Head) — ASBL governance, legal structure, asset ownership, strategic vision
- **Politype** (🫰 Heart) — Game-based governance, civic tech prototyping, democracy as design problem
- **OpenFab** (🧰 Hands) — Makerspace, tools, physical workshops, making real

This repository contains **design specifications, visual systems, and HTML mockups** for websites representing these three entities. See `trinity-charter-draft.md` for complete organizational context.

## Design Philosophy

### The Shadow Method
All three websites were designed from emotional/psychological state first (the "shadow work"), then translated to visual metaphors:

- **OpenFab**: Unmade potential → golden-hour workshop, wireframe ghosts, solitary threshold
- **Syntonie**: Burden of structure → cool pavilion, supporting pillars, dappled shade
- **Politype**: Terror of trust → balanced horizon, paired dialogue, heart-in-ice

This shapes everything: color temperature, grid expression, figure presence, spatial language.

### Design Principles (Non-Negotiable)

1. **Grid = Permission, Not Prison** — 59px base unit (59cm scaled 1:10 ratio) invites structure without constraint
2. **Shadow = Depth, Not Darkness** — Always reaching toward something meaningful
3. **Wireframes = Potential, Not Failure** — Visual ghosts of what could be made
4. **Temperature = Emotional Key** — Warm (OpenFab urge) / Cool (Syntonie permission) / Balanced (Politype dialogue)
5. **Space = Breathing Room** — Neurodiverse-friendly: high contrast, visible structure, generous spacing

## Locked Design Decisions

### Shared Constants (Across All Three Sites)

| Element | Specification | Rationale |
|---------|---------------|-----------|
| **Left Sidebar** | Fixed position, never collapses | Immovable visual anchor (Nicolas directive) |
| **Grid Foundation** | 59px tiles, 1:1 square ratio, full-bleed | Physical space metaphor; consistent scale |
| **Typography Suite** | Atkinson Hyperlegible (headers/body), Syne Mono (technical), Syne (accents) | Accessible, bold, geometric |
| **Geometric Abstraction** | Circles, triangles, lines (wireframe overlays) | De Stijl language, not photorealistic |
| **Negative Space** | Active element, never empty | Visual richness through restraint |

### Per-Entity Visual Identity

> **CRITICAL — Palette assignment corrected 2026-03-11. Do not revert.**

**Syntonie — The Neutral Pavilion:** *(canonical reference artboard)*
- Temperature: Neutral/natural steel blue
- BG: `#0f1216` / Sidebar BG: `#0b0e12` / Accent: `#4a7fa5` (steel blue)
- Grid: Visible blueprint aesthetic (technical white lines)
- Sidebar texture: Clean vertical pillars with animation
- Key motif: Pillars receding, negative space as light
- Space feel: Embracing, rhythmic, permissive
- **Pillar animation locked:** `@keyframes breathe { 0%,100%: opacity 0.3, blur 1px; 50%: opacity 0.95, blur 0 }` (staggered 0s, 2s, 1s delays)
- **Logo direction:** H-bridge motif (blue pillars + interlocking orange/brown ribbons)

**OpenFab — The Cold Workshop:**
- Temperature: Cold/blue
- BG: `#0c1520` / Sidebar BG: `#0e1a28` / Accent: `#2d6a9f` (cold blue)
- Grid: Visible but softened (cold gray, subtle)
- Sidebar texture: Tool-wall outline aesthetic
- Key motif: Wireframe project ghosts at 0.3 opacity
- Space feel: Vast, breathable, threshold-like

**Politype — The Warm Horizon:**
- Temperature: Warm amber
- BG: `#150d08` / Sidebar BG: `#130c08` / Accent: `#c47a2a` (amber)
- Grid: Checkerboard receding to infinity (perspective effect)
- Sidebar texture: Balance symbol, dialogue invitation
- Key motif: Two figures in geometric dialogue, heart-in-ice-cube
- Space feel: The space *between*, invitation to movement

## Current Implementation State — `pencil-Trinity.pen`

### Artboard Node IDs
| Artboard | Node ID | Status |
|----------|---------|--------|
| Syntonie — Cool Pavilion | `665dI` | **Canonical reference — approved** |
| OpenFab — Warm Workshop | `8Hu7D` | Propagated from Syntonie |
| Politype — Balanced Horizon | `qLhKi` | Propagated from Syntonie |

### Syntonie Key Nodes (`665dI`)
| Section | Node ID | Height |
|---------|---------|--------|
| Sidebar | `TjMQq` | full-height |
| Main Content | `pC7En` | — |
| Hero | `nbECT` | 708px (12×59) |
| Vision | `pegwj` | 590px (10×59) |
| Role | `sRb4o` | 590px (10×59) |
| Trinity | `aDQsE` | 708px (12×59) |
| Contact | `B9AHb` | 472px (8×59) |

### Locked Sidebar Structure (All Three Artboards)
```
Sidebar (236px wide, padding [36,28,32,28], vertical, justifyContent: space_between)
  ├── Brand (name + glyph + tag + tag2)
  ├── Nav  (5 items: 00 ACCUEIL / 01 / 02 / 03 LA TRINITY / 05 CONTACT)
  ├── Spacer (fill_container — pushes bottom content down)
  ├── Lang Toggle (FR active / EN muted)
  └── Ecosystem Portals (two sibling entities, labeled ÉCOSYSTÈME)
```

### Section Padding Standard (All Three Artboards)
- **Hero**: `[118, 59, 59, 118]` — asymmetric (extra left indent)
- **Content sections**: `[118, 59]` — 2×59 top/bottom, 1×59 sides
- **Gap between section children**: `59px`

### De Stijl Composition (Implemented in Syntonie, reference for others)
- Hero: 2-column horizontal — left (accent bar + eyebrow + title + sub) + right (definition card 236px)
- Vision: 2-column horizontal — body (fill) + pull quote (320px with left accent border)
- Role: vertical stack — label + title + lead + 2-column do/don't (gap 59px)
- Trinity: 3 cards (gap 59px) — card 2 (Politype) drops 30px vertical stagger
- Contact: label + title + lead + 3 horizontal tracks

## Hugo Site — Syntonie (`syntonie/`)

The active implementation is a Hugo static site in `syntonie/`. The design-spec HTML mockups above are reference only; the Hugo site is what gets deployed.

### Build & Development

```bash
cd syntonie
hugo server          # dev server at http://localhost:1313/syntonie/
```

**Deployment**: `syntonie/` is pushed as a git subtree to `openfab-lab/syntonie`. CI builds with `hugo --minify --baseURL "https://syntonie.be/"`. Live at https://syntonie.be/

**CRITICAL**: `public/` is gitignored — CI builds it fresh. Never commit it. `hugo.toml` baseURL is for local dev only; CI overrides it.

### Site Structure

```
syntonie/
  hugo.toml              # baseURL for local dev (CI overrides for production)
  .gitignore             # excludes public/, .hugo_build.lock
  .github/workflows/     # build-deploy.yml (Hugo build + GitHub Pages deploy)
  layouts/
    index.html           # fog-of-war homepage (fogzone + recipe reveal)
    _default/baseof.html # shell: sidebar, main, JS/CSS includes
  static/
    css/main.css         # all styles (fog, recipes, sidebar, about)
    js/recipes.js        # RECIPE_SECTIONS (DOM mapping) + TRIGGERS + revealRecipe()
    js/topics.json       # keyword→recipe mapping (loaded by recipes.js)
  data/
    navigation.json      # project metadata from TTL (enrichment only, NOT for DOM reveals)
  content/
    _index.md            # homepage front matter
```

### Fog-of-War System (homepage)

- Input field triggers autocomplete from `topics.json`
- On match (2+ chars or topic-chip click): recipe `<section>` reveals via `display:none` → visible
- **`RECIPE_SECTIONS`** (hardcoded in `recipes.js`) maps recipe keys to DOM section IDs — this is the source of truth
- **`navigation.json`** provides project metadata only — must NOT overwrite `RECIPES` used by `revealRecipe()`
- **Radical absence rule**: hidden elements use `display:none`, never `opacity:0` or `visibility:hidden`
- **CSS var cleanup**: `revealRecipe(null)` must `removeProperty()` inline vars (`--padding-centered`, `--min-height-collapsed`) so CSS defaults take over
- **Asset paths**: always use `{{ .Site.BaseURL }}` in templates, never hardcoded paths

### About Page (TODO)

The `/about` route will hold the institutional content currently in `syntonie-baseline.html`. Not yet implemented in Hugo.

---

## Key Files & Their Purpose

| File | Purpose | Status |
|------|---------|--------|
| `trinity-charter-draft.md` | **Read this first** — Organizational mission, roles, philosophy | Foundation document |
| `design-spec-website-v2-2026-03-08.md` | Master design system across all three sites (4D concept, shared vocabulary, technical brief) | Current spec (v2) |
| `design-spec-syntonie-v3.md` | Syntonie-specific deep dive (locked decisions, pillar animation, color TBDs) | Foundation locked, details TBD |
| `design-spec-website-2026-03-08.md` | OpenFab initial exploration | Superseded by v2 |
| `design-decisions-2026-03-08.md` | Decision log (what survived v1-v5 iterations, what died) | Strategy document |
| `syntonie-feedback-v3.md` | Iteration notes on Syntonie direction | Reference for context drift |
| `syntonie-mockup*.html` | Visual prototypes at various design stages (v1-v5) | Implementation refs |

## Design Workflow

### Before Making Changes

1. **Check the decision log** (`design-decisions-2026-03-08.md`) — What decisions are locked vs. TBD?
2. **Read the relevant spec** — OpenFab/Syntonie/Politype has specific color, grid, and motif requirements
3. **Understand the shadow first** — Why this temperature? Why this grid? The specs explain the *why*

### Common Tasks

**Defining missing color codes:**
- Extract hex values from the design spec's CSS variable section (section 6.1)
- Maintain palette separation: warm (OpenFab), cool (Syntonie), balanced (Politype)
- Test for WCAG contrast (high-contrast requirement for neurodiverse accessibility)

**Implementing grid:**
```css
.grid-background {
  background-image:
    linear-gradient(var(--grid-color) 1px, transparent 1px),
    linear-gradient(90deg, var(--grid-color) 1px, transparent 1px);
  background-size: 59px 59px;
}
```

**Implementing wireframe ghosts:**
```css
.wireframe {
  border: 1px solid var(--accent-color);
  background: transparent;
  opacity: 0.3;
  box-shadow: inset 0 0 20px var(--accent-color);
}
```

**Sidebar layout:**
```css
grid-template-columns: 280px 1fr;  /* sidebar + content */
.sidebar { position: fixed; width: 280px; height: 100vh; }
```

### Avoiding Context Drift

- **Don't dilute the temperature** — Warm stays warm, cool stays cool, balance stays balanced
- **Don't hide the grid** — "Subtle" is neurodiverse-hostile; visible structure is a feature
- **Don't add rounded corners** — 90° angles or nothing (De Stijl constraint)
- **Don't center content symmetrically** — Asymmetry is intentional (cognitive accessibility)
- **Don't make it "professional bland"** — Bold geometry, clear hierarchy, generous breathing room

The design decisions log (v1-v5 iterations) documents what was tried and why it failed. Don't repeat those paths.

## Open Questions (For Future Sessions)

| Question | Entity | Impact | Status |
|----------|--------|--------|--------|
| Wireframe animation? (subtle float) | OpenFab | Motion design | TBD |
| Mobile adaptation: sidebar becomes...? | All | Responsive behavior | TBD |
| Scroll-snap sections? | All | Navigation behavior | TBD |
| Grid opacity levels per entity? | All | Subtle vs. prominent balance | TBD |
| Hero 2-column layout for OpenFab/Politype? | OF, PO | De Stijl composition | TBD — only done for Syntonie so far |
| Definition card content for OF/PO heroes? | OF, PO | Hero right column | TBD |
| Trinity cards in OF/PO: accent colors correct? | OF, PO | Cross-entity refs | Verify next session |

## Next Steps (Prioritized)

1. **Apply De Stijl hero restructure to OpenFab and Politype** — 2-column with entity-specific right card
2. **Add geometric figures** — wireframe ghosts (OpenFab), pillar animation (Syntonie), dialogue figures (Politype)
3. **Verify Trinity section cards** in OF and PO artboards — accent colors should match entity palette
4. **Export HTML prototypes** from approved .pen layouts

## Key Constraints

- **Fixed sidebar** — 236px, never collapses, never hidden
- **59px grid** — Non-negotiable unit (section heights, padding, gaps must be multiples of 59)
- **Geometric figures only** — No photographs, no realistic rendering
- **Separate palettes** — Don't mix temperatures across artboards
- **Syntonie is the canonical reference** — When in doubt, match its structure/rhythm

---

*This is a design-first project. Every visual choice reflects organizational philosophy. Read the specs, understand the shadows, respect the constraints, and build coherently.*
