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

**OpenFab — The Warm Workshop:**
- Temperature: Golden sunset (amber-shifted primaries)
- Grid: Visible but softened (warm gray, subtle)
- Sidebar texture: Tool-wall outline aesthetic
- Key motif: Wireframe project ghosts at 0.3 opacity
- Space feel: Vast, breathable, threshold-like
- Color base: wheat → sand → warm gray gradient

**Syntonie — The Cool Pavilion:**
- Temperature: Blue-green cool (evening-shifted primaries)
- Grid: Visible blueprint aesthetic (technical white lines)
- Sidebar texture: Clean vertical pillars with animation
- Key motif: Pillars receding, negative space as light
- Space feel: Embracing, rhythmic, permissive
- Color base: lapis lazuli → teal → dusk gradient
- **Pillar animation locked:** `@keyframes breathe { 0%,100%: opacity 0.3, blur 1px; 50%: opacity 0.95, blur 0 }` (staggered 0s, 2s, 1s delays)
- **Logo direction:** H-bridge motif (blue pillars + interlocking orange/brown ribbons)

**Politype — The Balanced Horizon:**
- Temperature: Sunset-meets-sea (pure, unshifted primaries)
- Grid: Checkerboard receding to infinity (perspective effect)
- Sidebar texture: Balance symbol, dialogue invitation
- Key motif: Two figures in geometric dialogue, heart-in-ice-cube
- Space feel: The space *between*, invitation to movement
- Color base: sunset gold → sea silver gradient

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

These decisions need to be made before full implementation:

| Question | Entity | Impact | Status |
|----------|--------|--------|--------|
| Exact hex codes for warm/cool palettes? | All | Color implementation | TBD |
| Wireframe animation? (subtle float/float) | OpenFab | Motion design | TBD |
| Mobile adaptation: sidebar becomes...? | All | Responsive behavior | TBD |
| Scroll-snap sections? | All | Navigation behavior | TBD |
| Pillar animation direction: bottom-up only? | Syntonie | Animation sequence | Mostly decided |
| Grid opacity levels per entity? | All | Subtle vs. prominent balance | TBD |

## Approach to Implementation

1. **Start with one entity** (suggest: OpenFab first — foundation)
2. **Build a single-page prototype** before multi-page system
3. **Use CSS Grid + Grid background pattern** for layout and grid
4. **Keep structure semantic** — HTML reflects the spatial hierarchy
5. **Test for contrast** — WCAG standards are baked into the design philosophy, not separate

## Key Constraints

- **No content yet** — Mockups use Lorem Ipsum; focus on visual structure
- **Fixed sidebar** — Must never collapse or disappear
- **59px grid** — Non-negotiable unit across all sites (physical space metaphor)
- **Geometric figures only** — No photographs, no realistic rendering
- **Separate palettes** — Don't mix warm (OpenFab) with cool (Syntonie) on same page

---

*This is a design-first project. Every visual choice reflects organizational philosophy. Read the specs, understand the shadows, respect the constraints, and build coherently.*
