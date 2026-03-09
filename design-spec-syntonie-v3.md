# Syntonie Design Spec v3.0 — Clean Restart

**Date:** 2026-03-08  
**Status:** Foundation locked. Details TBD.  
**Mood:** De Stijl shelter. Bold geometry, soft embrace.

---

## 1. The Core Concept (Locked)

**"The shelter and safe legal space"**

Visual translation:
- **Left side = The wall** (solid, structural)
- **Right = Open space** (light, stepping into)
- **Pillars hold up the roof** (the structure that enables freedom)
- **Grid = Blueprint** (visible planning, technical precision)

---

## 2. What We Keep (Non-Negotiable)

### 2.1 Fonts (Locked)
- **Display/Headlines:** Atkinson Hyperlegible (Bold, structural, accessible)
- **Body:** Atkinson Hyperlegible Regular
- **Mono/Labels:** Syne Mono (Technical, architectural)
- **Accent:** Syne (Bold, geometric)

### 2.2 The Pillar Animation (Locked)
```css
.sb-pillar {
  animation: breathe 8s ease-in-out infinite;
}
@keyframes breathe {
  0%,100% { opacity: 0.3; filter: blur(1px); }
  50%      { opacity: 0.95; filter: blur(0); }
}
```
- Three vertical lines, bottom-up
- Staggered animation (0s, 2s, 1s delay)
- Blur creates "inhale/exhale" physicality

### 2.3 The Reference Image
**The "H-bridge" motif:**
- Blue vertical bars (pillars)
- Interlocking orange/brown shapes
- Overlapping ribbon effect
- Bridge/structure as shelter symbolism
- **This is the logo direction we liked**

---

## 3. Visual System (TBD — Define These)

### 3.1 Color Palette
**Needs definition:**
- [ ] Sidebar: Solid navy OR dark navy? (v1 dark vs v5 lighter)
- [ ] Grid lines: Visible weight? (De Stijl demands bold lines)
- [ ] Accent: Pure orange or burnt orange?
- [ ] Main background: White, parchment, or cool gray?
- [ ] Text contrast: White-on-dark (hero) OR dark-on-light (body)?

**Guidance:** 
- High contrast (neurodiverse-friendly)
- Primary colors (De Stijl, not pastels)
- Structure > decoration

### 3.2 The Grid (Critical Decision)
**Options:**
- **A:** Visible grid lines on light background (blueprint aesthetic)
- **B:** No visible grid, only implied structure
- **C:** Grid on sidebar only
- **Decision needed:** _Which feels like "blueprint"?_

### 3.3 Layout Architecture
**The left wall = strong**
- Fixed position
- Never collapses
- Pillars animate
- Links arranged vertically
- **Density:** Sparse, not crowded

**The main space = stepping into**
- Offset by sidebar width
- Breathing room (but how much?)
- Grid visible or invisible?
- **Flow:** Hero → sections → footer

---

## 4. Content Structure (Draft)

```
[sidebar — fixed, pillared, dark]
├── Syntonie logo (wordmark)
├── Navigation (numbered 00-05)
├── Lang toggle
└── Ecosystem portals (Politype/OpenFab stubs)

[main — scrollable, grid-based, light]
├── HERO
│   ├── Title: "Être en résonance"
│   ├── Subtitle
│   └── Etymology card: "syn-to-nie"
├── VISION
├── NOTRE RÔLE
├── LA TRINITY
├── POUR QUI
├── CONTACT
└── Footer
```

**TBD:** 
- How much text per section? (Density)
- Section size? (Rhythm)
- Cards or clear blocks?

---

## 5. WCAG Considerations (Non-Boring)

### 5.1 What Neurodiverse Users Need
- **High contrast** (not gray-on-gray)
- **Structure visible** (lines, blocks, clear hierarchy)
- **Breathing room** (not dense)
- **Predictable** (grid creates spatial logic)

### 5.2 What WCAG Approves That's Also Bold
- White on very dark navy (21:1 ratio possible)
- Visible focus indicators (can be orange blocks)
- Clear section breaks (can be geometric)
- Typography hierarchy (structure, not decoration)

### 5.3 What We Reject
- Pastels (cognitive load, unclear hierarchy)
- "Subtle" anything (worse than explicit)
- Gray-on-gray (invisible structure)

---

## 6. The Logo/Motif Direction

**The H-bridge concept:**
- Vertical = Pillars (blue)
- Horizontal/Diagonal = Shelter (orange/brown)
- Interlocking = Community/connection
- Geometric = De Stijl precision

**Application:**
- Sidebar background? Subtle?
- As monogram next to wordmark?
- Animated element?

**TBD:** How prominently? Literal or abstracted?

---

## 7. Open Questions (For This Session)

Before you restart, decide:

1. **Grid visibility:** Visible lines OR implied only?
2. **Sidebar color:** Very dark navy OR solid orange block?
3. **Main background:** White, off-white, or cool gray?
4. **Hero:** White text on dark OR dark text on light?
5. **Pillar animation:** Minimal OR the hero element?
6. **The H-bridge logo:** Sidebar watermark OR next to wordmark?

---

## 8. The "No" List

**This iteration REJECTS:**
- [ ] Text-heavy sections marching down
- [ ] Generic "corporate dark mode"
- [ ] Rounded corners (De Stijl = 90° only)
- [ ] Pastels
- [ ] "Subtle" grid
- [ ] Centered content symmetry
- [ ] More than 3 pillars
- [ ] Decorative elements with no structure

---

## 9. Claude Code Ready Prompt

```
Build Syntonie one-page from ZERO context.

FONTS (Google): Atkinson Hyperlegible, Syne, Syne Mono
SIDEBAR: Fixed left, 268px, pillars animate (breathing keyframes)
GRID: [DECIDE: visible lines OR implied structure]
COLORS: [DECIDE: palette]
LAYOUT: Hero → sections → footer
LOGO: [DECIDE: H-bridge motif placement]

Constraint: De Stijl geometry. 90° angles. High contrast. Structure as content.
No pastels. No subtlety. Bold or nothing.
```

---

## 10. Success Criteria

This spec succeeds when:
- [ ] Sidebar pillars are the first thing you notice
- [ ] Grid feels structural, not decorative
- [ ] High contrast without being "startup dark mode"
- [ ] Light side opens up, not closes in
- [ ] Typography is architecture, not decoration
- [ ] H-bridge motif feels natural, not forced
- [ ] A neurodiverse user could navigate by structure alone

---

**The goal:** A website that is simultaneously **rigid** (grid, structure) and **welcoming** (breathing, shade).

*Let's define those 6 questions, then build.* 👓✨
