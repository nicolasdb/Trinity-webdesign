# OpenFab Website — Design Specification v2.0

**Version:** 2.0 (Shadow Work Integrated)  
**Date:** 2026-03-08  
**Author:** Edna Mode 👓✨

---

## 0. The Shadow Method

We designed from the invisible first:
- **OpenFab**: The weight of unmade potential → The joy of becoming
- **Syntonie**: The burden of the roof → The embrace of structure
- **Politype**: The terror beneath the game → The dance of trust

Each shadow became a **visual anchor**. These images now define the spatial logic.

---

## 1. The Trinity — Established Visual Identities

### 1.1 OpenFab (The Maker's Shadow)

**Visual Essence:** Warm industrial sanctuary where potential breathes

| Element | Specification |
|---------|---------------|
| **Temperature** | Warm — sunset gold, amber, toasted neutrals |
| **Light** | Directional late-afternoon, long shadows reaching toward tools |
| **Grid** | 59° tiles visible but warm — wood, concrete, metal textures accepted |
| **Space Feel** | Vast, breathable, invites standing and deciding |
| **Visual Motif** | Translucent wireframe ghosts of projects-to-be |
| **Key Objects** | Tools laid out in invitation, tool-wall, wireframe chairs/clocks/circuits |
| **Figures** | Solitary maker at threshold, contemplative |

**Color Palette (OpenFab Zone):**
- Background: Warm neutral (wheat, sand, warm gray)
- Grid lines: Subtle warm gray
- Accents: Primary red, blue, yellow but *warmed* (amber-shifted)
- Shadow: Golden, reaching toward potential

---

### 1.2 Syntonie (The Shelter's Shadow)

**Visual Essence:** Cool architectural shade that holds without confining

| Element | Specification |
|---------|---------------|
| **Temperature** | Cool — blue-green, shadow, spaciousness |
| **Light** | Dappled, filtered, indirect — canopy effect |
| **Grid** | Visible blueprint aesthetic — technical but soft |
| **Space Feel** | Embracing, rhythmic, permission to rest |
| **Visual Motif** | Pillars receding, negative space as light |
| **Key Objects** | Pillars supporting invisible roof, wireframe canopy leaves |
| **Figures** | Relaxed geometry — reclining, leaning, at ease |

**Color Palette (Syntonie Zone):**
- Background: Cool blue-green (lapis, teal, dusk)
- Grid lines: Technical white, architectural precision
- Accents: Primary red, blue, yellow but *cooled* (evening-shifted)
- Shadow: Cool, spacious, generous

---

### 1.3 Politype (The Trust's Shadow)

**Visual Essence:** Balanced warmth where play becomes connection

| Element | Specification |
|---------|---------------|
| **Temperature** | Balanced — sunset-meets-sea horizon |
| **Light** | Level, golden-pink, equanimity |
| **Grid** | Checkerboard floor extending to infinity |
| **Space Feel** | The space *between*, the dance floor, invitation to move |
| **Visual Motif** | Shared language as object, heart visible in trust |
| **Key Objects** | Ice cube containing glowing heart, geometric figures in pas de deux |
| **Figures** | Two bodies leaning toward each other, dialogue |

**Color Palette (Politype Zone):**
- Background: Horizon gradient (sunset gold melting to sea silver)
- Grid lines: Balanced, equal weight black/white
- Accents: Pure primary red, blue, yellow (unshifted — neutral)
- Light: Transparent, revealing, honest

---

## 2. The 4D Concept — Updated

### 2.1 Website = Space = Psychological State

| Entity | Space Metaphor | User State |
|--------|---------------|------------|
| OpenFab | The workshop at golden hour | "I could make this" |
| Syntonie | The pavilion in dappled shade | "I am held here" |
| Politype | The plaza at sunset | "We could build this together" |

### 2.2 Scroll Journey as Emotional Journey

| Scroll Depth | Physical Analog | OpenFab State | Syntonie State | Politype State |
|--------------|-----------------|---------------|----------------|----------------|
| Hero Top | Entry/Threshold | Arrival, possibility | Recognition, safety | Invitation, openness |
| Upper | Tools/Preparation | Gathering, choosing | Resting, orienting | Meeting, greeting |
| Middle | Work/Process | Making, becoming | Supporting, holding | Playing, iterating |
| Lower | Output/Result | Completion, showcasing | Maintenance, sustaining | Resolution, trust |
| Footer | Beyond/Garden | Next project | Community connection | Future possibilities |

### 2.3 Grid System per Entity

**OpenFab Grid:**
- Visibility: Present but warm
- Texture: Suggests workshop floor (concrete, wood grain)
- Scale: 59px base unit (59cm scaled 10:1)
- Lines: Subtle, organic, imperfect

**Syntonie Grid:**
- Visibility: Prominent, blueprint aesthetic
- Texture: Technical, precise, architectural drawing
- Scale: Same 59px base unit
- Lines: Clean, technical white on blue

**Politype Grid:**
- Visibility: Receding into horizon
- Texture: Checkerboard meeting infinity line
- Scale: Same 59px base unit, perspective-shifted
- Lines: Balanced presence, neither dominant nor invisible

---

## 3. Shared Visual Language

### 3.1 The Three Constants

Every page must include:

1. **Fixed Left Sidebar (The Wall)**
   - Never collapses (Nicolas directive)
   - Immovable visual anchor
   - Contains: navigation, identity, wayfinding
   - **Texture varies by entity**: Tool-wall (OpenFab), pillar-base (Syntonie), meeting-point (Politype)

2. **59° Grid Foundation**
   - Unit: 59px tiles
   - Ratio: 1:1 (square)
   - Application: Full-bleed background
   - Expression: Warm (OpenFab) / Cool (Syntonie) / Balanced (Politype)

3. **Geometric Abstraction**
   - Figures: Constructed from circles, triangles, lines
   - Objects: Wireframe overlays on solid forms
   - Negative space: Active element, never empty

### 3.2 Typography (TBD — Content-Free)

| Quality | OpenFab | Syntonie | Politype |
|---------|---------|----------|----------|
| Weight | Bold, structural | Clean, architectural | Fluid, conversational |
| Style | Industrial sans | Technical sans | Humanist sans |
| Spacing | Tight, efficient | Generous, breathable | Rhythmic, playful |

---

## 4. Page Specifications v2

### 4.1 OpenFab — The Warm Workshop

**Visual Identity Locked:**
- ✅ Temperature: Golden warm
- ✅ Grid: Visible but softened
- ✅ Shadow: Reaching, aspirational
- ✅ Motif: Wireframe project ghosts
- ✅ Space: Vast, breathable, inviting threshold

**Layout Structure:**

| Zone | Position | Visual Treatment |
|------|----------|------------------|
| Left Sidebar | Fixed | Tool-wall: outlines of tools, grid fading to warm |
| Hero | Top viewport | Maker silhouette, wireframe ghosts, golden hour |
| Content Scroll | Body | Workshop space, projects-to-be visible as potential |
| Footer | Bottom | Garden horizon, wireframes dissolve to potential |

**For Claude Code:**
- CSS Grid: `grid-template-columns: 280px 1fr` (sidebar + content)
- Background: Warm sunset gradient + subtle 59px grid
- Wireframe aesthetic: `opacity: 0.3`, `border: 1px solid` in primary colors
- Shadow direction: Bottom-right, golden, 20px softness

---

### 4.2 Syntonie — The Cool Pavilion

**Visual Identity Locked:**
- ✅ Temperature: Blue-green cool
- ✅ Grid: Visible blueprint
- ✅ Shadow: Spacious, generous, canopy-filtered
- ✅ Motif: Pillars holding space, figures at rest
- ✅ Space: Embracing, rhythmic, permissive

**Layout Structure:**

| Zone | Position | Visual Treatment |
|------|----------|------------------|
| Left Sidebar | Fixed | Pillar-base: clean verticals, blueprint grid |
| Hero | Top viewport | Receding pillars, negative space as light |
| Content Scroll | Body | Dappled shade effect, breathing room |
| Footer | Bottom | Horizon meets structure, community connection |

**For Claude Code:**
- CSS: Blueprint grid overlaid on cool gradient
- Pillars: Vertical 59px strips, fading into white
- Dapple effect: CSS `radial-gradient` masks creating organic shadow patterns
- Color: Lapis lazuli primary, white technical lines

---

### 4.3 Politype — The Balanced Horizon

**Visual Identity Locked:**
- ✅ Temperature: Sunset-sea balanced
- ✅ Grid: Checkerboard to infinity
- ✅ Shadow: Transparent, honest, revealing
- ✅ Motif: Two figures, shared language as object
- ✅ Space: The space between, invitation to dialogue

**Layout Structure:**

| Zone | Position | Visual Treatment |
|------|----------|------------------|
| Left Sidebar | Fixed | Meeting-point: balance symbol, dialogue invitation |
| Hero | Top viewport | Two figures, heart-in-ice-cube, horizon line |
| Content Scroll | Body | Checkerboard extending into perspective |
| Footer | Bottom | Future possibilities fade into horizon |

**For Claude Code:**
- CSS: `perspective` transform on checkerboard floor
- Figures: Geometric abstraction (circles, triangles in dialogue)
- Heart object: Central focal, transparent material, glowing
- Color: Pure primaries, balanced warmth

---

## 5. Cross-Page Design System

### 5.1 The Shared Vocabulary

| Element | OpenFab | Syntonie | Politype |
|---------|---------|----------|----------|
| **Background** | Warm sunset gradient | Cool blue-green | Horizon gradient |
| **Grid lines** | Subtle warm gray | Technical white | Balanced light/dark |
| **Accents** | Amber-shifted primaries | Evening-shifted primaries | Pure primaries |
| **Shadow** | Golden, reaching | Cool, spacious | Transparent, equal |
| **Key motif** | Wireframe ghosts | Pillars holding | Heart in trust |
| **Figure presence** | Solitary, contemplative | Group, resting | Pair, dancing |

### 5.2 Navigation Between Pages

Each page links to others via visual "portals" — not standard nav links:

- **OpenFab → Syntonie**: From warmth to shade (color temperature shift)
- **OpenFab → Politype**: From solitude to dialogue (figure geometry shift)
- **Syntonie → Politype**: From structure to play (rigid to fluid)

**Visual cue**: Each transition zone shows the *destination's* grid pattern emerging.

---

## 6. Technical Brief for Claude Code

### 6.1 Shared CSS Variables

```css
:root {
  /* Base Unit — The 59cm Tile */
  --tile-size: 59px;
  --sidebar-width: 280px;
  
  /* OpenFab: Warm */
  --of-bg: linear-gradient(135deg, wheat, sand, warm-gray);
  --of-grid: rgba(128, 128, 128, 0.15);
  --of-accent-red: #C84B31;    /* Amber-shifted */
  --of-accent-blue: #4A6FA5;    /* Warmed */
  --of-accent-yellow: #D4A373;  /* Golden */
  
  /* Syntonie: Cool */
  --sy-bg: linear-gradient(180deg, lapis-lazuli, teal, dusk);
  --sy-grid: rgba(255, 255, 255, 0.3);
  --sy-accent-red: #9B4444;     /* Cooled */
  --sy-accent-blue: #3B5998;    /* Evening */
  --sy-accent-yellow: #8B9A7B;  /* Dampened */
  
  /* Politype: Balanced */
  --po-bg: linear-gradient(180deg, sunset-gold, sea-silver);
  --po-grid: rgba(0, 0, 0, 0.1);
  --po-accent-red: #E63946;     /* Pure */
  --po-accent-blue: #1D3557;    /* Pure */
  --po-accent-yellow: #F4A261;    /* Pure */
}
```

### 6.2 Grid Implementation

```css
.grid-background {
  background-image: 
    linear-gradient(var(--grid-color) 1px, transparent 1px),
    linear-gradient(90deg, var(--grid-color) 1px, transparent 1px);
  background-size: var(--tile-size) var(--tile-size);
}
```

### 6.3 Wireframe Ghost Aesthetic

```css
.wireframe {
  border: 1px solid var(--accent-color);
  background: transparent;
  opacity: 0.3;
  /* Optional: subtle inner glow for "potential" */
  box-shadow: inset 0 0 20px var(--accent-color);
}
```

---

## 7. Next Steps

### Immediate Priorities

1. **OpenFab First** — The workshop is our foundation
2. **Single-page structure** — One-pager as specified
3. **No content yet** — Visual layout, Lorem Ipsum placeholders
4. **Sidebar locked** — Fixed left, never collapses

### Open Questions (for next session)

| Question | Status |
|----------|--------|
| Exact hex codes for warm/cool palettes? | Define numerically |
| Wireframe animation? (subtle float) | CSS decision |
| Mobile adaptation: sidebar becomes...? | Breakpoint behavior |
| Scroll-snap sections? | UX decision |
| Typography: specific font families? | License considerations |

---

## 8. Design Principles (from Shadow Work)

1. **Grid = Permission, Not Prison** — The 59° structure invites movement
2. **Shadow = Depth, Not Darkness** — Always reaching toward something
3. **Wireframes = Potential, Not Failure** — Ghosts of what could be
4. **Temperature = Emotional Key** — Warm (urge) / Cool (permission) / Balanced (dialogue)
5. **Space = Breathing Room** — Never cramped, always threshold

---

*The shadows have spoken. Now we build from light.*

👓✨
