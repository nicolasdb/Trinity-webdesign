# Design Decisions Log — 2026-03-08

**Session:** Syntonie Website Pivot  
**Status:** V6 in progress — clean restart from v3 specs  

---

## The Pivot

**Problem:** Context pollution with Claude Code iterations. Design drift from De Stijl vision toward "professional dark mode."

**Solution:** Strip to essentials. Define 6 critical decisions. Restart from clean spec.

---

## What Survived (Locked)

| Element | Decision | Source |
|---------|----------|--------|
| Fonts | Atkinson Hyperlegible, Syne, Syne Mono | Working well |
| Pillar animation | Blur + opacity breathe | Successfully implemented |
| Left sidebar | Fixed, never collapses | Core concept |
| 59px grid unit | Foundation | Physical space metaphor |
| H-bridge motif | Logo direction | Reference image liked |

---

## What Died (Rejected)

| Element | Reason |
|---------|--------|
| "Subtle" grid | Weak. De Stijl demands visible structure. |
| Parchment warmth | Too generic. Cool shade = true to shadow work. |
| Dense text sections | Corporate, not manifesto. |
| Centered symmetry | Safe, not De Stijl. |
| Rounded corners | 90° or nothing. |
| "Professional" polish | Boring, forgettable. |

---

## The 6 Questions

1. **Grid visibility:** Visible structural lines OR implied only?
2. **Sidebar color:** Very dark navy OR solid orange block?
3. **Main background:** White, off-white, OR cool gray?
4. **Hero style:** White text on dark OR dark text on light?
5. **Pillar prominence:** Minimal accent OR hero element?
6. **H-bridge logo:** Sidebar watermark OR next to wordmark?

---

## The Attempted Directions

| Version | Approach | Result |
|---------|----------|--------|
| v1 | Full blue, visible grid, bold | Too dark, noisy |
| v3 | Lighter, parchment | Corporate, lost De Stijl |
| v5 | Dark navy, subtle | Professional but safe |
| v6 (to be) | ?? | Pending 6 decisions |

---

## WCAG Reality Check

**Neurodiverse-friendly boldness:**
- ✓ High contrast (not pastels)
- ✓ Visible structure (grid, not subtle)
- ✓ Clear hierarchy (typography as architecture)
- ✓ Generous breathing room (not dense)

**Neurodiverse-hostile safety:**
- ✗ Gray-on-gray
- ✗ "Subtle" anything
- ✗ Centered symmetry (cognitive dead zone)
- ✗ Too much text density

**Conclusion:** WCAG and De Stijl are compatible. WCAG and "corporate bland" are not.

---

## Next Step

Define the 6 questions → Fresh Claude prompt → v6.

*No context pollution. Clean slate.* 👓✨
