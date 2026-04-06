---
project_name: 'Trinity'
user_name: 'Nicolas'
date: '2026-04-06'
status: 'complete'
sections_completed: ['technology_stack', 'hugo_rules', 'js_rules', 'testing_rules', 'code_quality_rules', 'workflow_rules', 'anti_patterns']
rule_count: 42
optimized_for_llm: true
---

# Project Context for AI Agents

_Critical rules and patterns AI agents must follow when implementing code in this project. These are the non-obvious details — things that will silently break if missed._

---

## Technology Stack & Versions

- **Hugo** `0.152.2` (extended) — static site generator, no npm, no node_modules
- **Vanilla JS** — no framework, no bundler, no transpilation; ES2020+ browser-native
- **Plain CSS** — single file (`static/css/main.css`), no preprocessor, no PostCSS
- **Deployment** — GitHub Actions → GitHub Pages via `peaceiris/actions-hugo@v3`
- **Live domain** — `https://syntonie.be/` (subtree push: `Trinity/syntonie/` → `openfab-lab/syntonie`)

---

## Critical Implementation Rules

### Hugo Rules

- **Asset paths always use `{{ .Site.BaseURL }}`** — never hardcode paths. Subtree deploy changes
  the path prefix; `BaseURL` is the only safe anchor.
- **`baseURL` in `hugo.toml` is for local dev only** — CI overrides with
  `hugo --minify --baseURL "https://syntonie.be/"`. Never set it to the prod URL; breaks `hugo server`.
- **Never use `.Permalink` in templates** — embeds the dev `baseURL` in static output.
  Use `.RelPermalink` or hardcode production domain for canonical/OG tags (see `baseof.html`).
- **`[[module.mounts]]` is load-bearing** — never run `hugo mod tidy` or edit module config
  without understanding it. The mount exposes `data/navigation.json` at `/data/navigation.json`
  in the browser. Removing it silently breaks the `recipes.js` fetch.
- **`disableKinds = ["taxonomy", "term"]`** — frontmatter `tags`/`categories` are silently
  ignored. Don't add them expecting taxonomy pages.
- **Template types**: `layouts/index.html` = homepage; `layouts/_default/baseof.html` = shell
  for all pages; `layouts/projets/single.html` = project pages. Sidebar nav switches on `.IsHome`
  and `.Type` — preserve those conditionals.
- **`?v={{ now.Unix }}` cache-buster on CSS is intentional** — forces stylesheet reload every
  build to isolate CSS misalignment causes. Keep unless explicitly switching to Hugo fingerprinting.

### JavaScript Rules

- **No build step** — never introduce `import`/`export`, bundlers, or `require()`. All JS is
  loaded via plain `<script>` tags in `baseof.html`; scripts share a single global scope.
- **Global state is intentional** — `RECIPE_SECTIONS`, `TRIGGERS`, `RECIPE_META`, `currentRecipe`,
  `currentLang` are globals in `recipes.js`. Do not scope them inside an IIFE.
- **Async init order matters** — `navigation.json` is fetched inside `DOMContentLoaded`. Never
  access `RECIPE_PROJECTS` before that async block resolves.
- **`fetch()` paths use `window.TOPICS_URL` / `window.NAVIGATION_URL`** — Hugo templates can
  set these to inject the correct baseURL. Never hardcode `/js/topics.json`.
- **Event delegation on `#fog-topics`** — chips are rebuilt by `updateKeywordChips()` on every
  recipe switch. Never bind individual click handlers to chips; they'll be orphaned after rebuild.
- **Safari animation fix is mandatory** — double `requestAnimationFrame` + 16ms `setTimeout`
  fallback for any `display:none` → visible transition. Never remove either.
- **All `localStorage` keys must be prefixed `syntonie-`** — existing: `syntonie-lang`. New
  persistent state follows the same namespace.

### Testing Rules

- **No test framework exists** — zero automated tests. Do not scaffold a suite unless asked.
- **Manual verification model** — `hugo server` → `http://localhost:1313/syntonie/`.
- **Critical smoke tests**:
  1. Type 2+ chars → autocomplete appears
  2. Click topic chip → correct recipe reveals, URL hash updates
  3. Navigate to `/#contact` directly → Tally form loads
  4. Press Escape → fog resets, inline CSS vars cleared (verify in DevTools)
  5. Switch FR↔EN → chips and sidebar label update

### Code Quality & Style Rules

- **No linter, no formatter** — no ESLint, Prettier, Stylelint. Do not add tooling.
- **CSS lives in one file** — `static/css/main.css`. Never create additional CSS files.
- **59px grid unit is non-negotiable** — all section heights, padding, gaps must be multiples
  of 59: `59`, `118`, `177`, `236`, `472`.
- **Typography stack (locked)**:
  - `--f-head`: Atkinson Hyperlegible — UI chrome: nav, brand, labels, inputs, small text
  - `--f-body`: Atkinson Hyperlegible — body/recipe text (accessibility-first, neurodiverse)
  - `--f-display`: Spectral — large display headings only: `.hero-title`, `.sec-title`,
    `.shelter-title`, `.fog-tagline`, `.pull-quote` (26px+)
  - `--f-mono`: Syne Mono — technical labels only
  - Never introduce a fifth font. Spectral only at display sizes; never on small or UI text.
- **Color palette is entity-locked** — Syntonie: steel blue `#4a7fa5` on `#0f1216`.
  No warm tones (amber, orange); those belong to Politype. No cross-entity temperature mixing.
- **No rounded corners** — `border-radius: 0` everywhere. De Stijl constraint.
- **Asymmetric layouts are intentional** — resist symmetrical centering.
- **`display:none` / `hidden` attribute for invisible elements** — never `opacity:0` or
  `visibility:hidden`. Hidden content must be absent from layout flow.
- **Inline CSS vars need `removeProperty()` on reset** — empty-string overwrite does not
  restore the stylesheet default. See `revealRecipe(null)` in `recipes.js` for the pattern.
- **Sidebar stays left on all breakpoints** — solid-wall metaphor (physical makerspace has
  glass top/right/bottom walls, one solid left wall). Never move to top bar. On narrow viewports
  it narrows to an icon strip (~60px); it does not relocate.
- **WCAG: AAA target for body text, AA minimum everywhere** — verify contrast against `#0f1216`
  on any color change.
- **Decorative elements get `aria-hidden="true"`** — animated pillars, grid overlays, geometric
  shapes. Maintain on any new decorative additions.

### Development Workflow Rules

- **Deploy is manual and milestone-gated** — `git subtree push --prefix=syntonie origin main`
  from Trinity root. A normal `git push` to this repo does NOT trigger Syntonie CI.
- **`public/` is gitignored** — CI builds it fresh. Never commit it.
- **No PR process** — Nicolas works directly on branches; no review gates.
- **Backlog lives in memory** — `memory/project_tidy_backlog.md` is the active task list.
- **TRIGGERS ↔ topics.json must stay in sync** — every keyword in `TRIGGERS` (`recipes.js`)
  must also exist in `static/js/topics.json`. Autocomplete silently drops keywords that are
  in TRIGGERS but missing from topics.json. Always edit both files together.

### Critical Anti-Patterns

- **Don't add a recipe without the full quad** — `RECIPE_SECTIONS` key → DOM `id` → `TRIGGERS`
  entry → `topics.json` keyword must all be consistent. `revealRecipe()` silently no-ops on
  missing IDs; autocomplete silently drops missing topics.
- **Don't reset fog state manually** — always call `revealRecipe(null)`. It handles inline var
  cleanup, chip rebuild, sidebar nav update, and URL hash atomically.
- **Don't use `navigation.json` to drive recipe reveals** — project metadata only. `RECIPE_SECTIONS`
  in `recipes.js` is the source of truth. Never overwrite `RECIPES` from nav data.
- **Tally embed must exist in DOM before first `revealRecipe('contact')`** — it must be present
  as `hidden` in the initial HTML. Never insert the contact block dynamically post-load.
- **`hashchange` is not handled** — `currentRecipe` reflects in-session state only. After
  browser back/forward the hash can drift from displayed state. Don't assume hash = active
  recipe when adding navigation features.
- **Subtree push ships everything in `syntonie/`** — no inner `.gitignore` filters content.
  Delete temp/debug files before any milestone push.
- **`/spaceapi/spaceapi.json` is a live public API endpoint** — do not move, rename, or
  restructure `static/spaceapi/`. External services poll it.
- **Don't use photographs or realistic rendering** — geometric abstraction only (circles, lines,
  wireframe overlays).
- **Don't dilute palette temperature** — Syntonie is cool steel blue. Temperature is the
  emotional key of each entity; mixing temperatures corrupts the design system.

---

## Usage Guidelines

**For AI agents:** Read this file before implementing any code. When in doubt, prefer the more
restrictive option. Flag new patterns to Nicolas rather than silently extending conventions.

**For humans:** Update when the stack or patterns change. The typography swap (Atkinson → body,
Spectral → head) was decided 2026-04-06 and is not yet reflected in the CSS — implement before
next milestone push.

_Last updated: 2026-04-06_
