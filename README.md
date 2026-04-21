# Mandeep Kumar Design System

A personal portfolio design system for **Mandeep Kumar — 2026**. Rooted in editorial-Swiss graphic design: oversized neo-grotesque wordmarks, monospaced micro-copy, generous whitespace, and a playful color-flip toggle that recolors every panel on demand.

## Source

- `Portfolio.html` — the canonical home page this system is derived from.
- Inspiration: editorial degree-show websites (huge type + corner labels + COLOR: ON/OFF pattern). All content and visual treatment is original.

## Products / Surfaces

- **Portfolio website** — a fullscreen paged single-page site. One panel per content beat (intro → categories → contact).

---

## CONTENT FUNDAMENTALS

**Voice:** first-person plural / studio-voice (“a small studio making…”). Confident, quiet, not performative. No exclamation marks. No emoji.

**Tone:** editorial. Sentences are short and declarative; em-dashes are common. Body copy dims its second clause (muted color) to create a soft two-beat rhythm.

**Casing rules:**
- `Title Case` for section headings, nav items, project titles.
- `UPPERCASE` for labels, metadata, counters, topic tags — always paired with `letter-spacing: 0.08em` and monospaced type.
- `sentence case` for body paragraphs.

**Examples (from the site):**
- Site title: `Mandeep Kumar — 2026`
- Nav: `Projects`, `Journey`, `Contact`
- Category index: `01 — Digital`, `07 Projects · 2022—2026`
- Category label: `Digital`, `Identity`, `Print`, `Motion`, `Experiments`

**Numbers:** zero-padded (`01`, `07`). En-dash for ranges (`2022—2026`). Middle-dot `·` separates metadata.

**No:** emoji, exclamation, ALL-CAPS headlines, icon-driven decoration, filler adjectives.

---

## VISUAL FOUNDATIONS

**Type system**
- Display + body: **Inter Tight** (Google Fonts substitute for an ABC Diatype / Söhne-like grotesque). Weights: 400, 500, 600.
- Labels + metadata: **JetBrains Mono**, 11px, uppercase, letter-spacing 0.08em.
- Category words: `clamp(120px, 22vw, 360px)` — **enormous**, flush-left, baseline-aligned to bottom of panel.
- Intro paragraph: `clamp(30px, 4.6vw, 72px)`, `max-width: 24ch`, `text-wrap: pretty`, weight 500, letter-spacing -0.025em.
- Line-heights: `0.86` on display, `1.04` on intro, `1.8` on uppercase metadata.

**Color (OFF state — default)**
- `--bg: #ffffff`
- `--fg: #0a0a0a` (near-black, never pure #000)
- `--muted: #6b6b6b`
- `--line: rgba(10,10,10,0.14)`

**Color (ON state — palette cycling)**
- Clicking the COLOR toggle cycles through **5 palettes**; each palette assigns a different `[bg, fg]` pair to every panel. This is the brand's signature interaction.
- Right-click the toggle to return to OFF.
- Palettes are defined in `Portfolio.html` (`palettes` array) — warm editorial, high-contrast primaries, pastel muted, bold saturated, mono ink.

**Spacing**
- Horizontal padding: `--pad-x: clamp(16px, 2vw, 28px)`
- Vertical padding: `--pad-y: clamp(14px, 1.4vw, 22px)`
- Fixed header: `52px` tall, `mix-blend-mode: difference`, white text that inverts over any panel color.
- One idea per panel. Full-viewport snap panels (`100vh × 100vw`).

**Borders & radii**
- Radii: `0` for panels and cards. `999px` only for the pill-shape color toggle.
- Borders: `1px` hairlines at `rgba(10,10,10,0.14)`. Otherwise none — negative space does the work.

**Shadows**
- **None.** The system deliberately avoids drop shadows. Depth comes from scale and contrast.

**Animation + easing**
- Panel transitions: `transform 900ms cubic-bezier(.76, 0, .24, 1)` (strong ease-in-out).
- Micro-interactions (hover, color fade): `380ms cubic-bezier(.2, .7, .2, 1)`.
- Category word on hover: `translateX(10px)` over 700ms.
- No bounces, no spring overshoot. Motion is confident and flat.

**Hover / press states**
- Nav links: 1px underline draws in from left (`transform: scaleX(0 → 1)`).
- Category panels: cursor is pointer; the giant word slides 10px right on hover.
- Contact link: 2px underline fades in via `border-color`.
- No opacity dims, no color shifts, no scaling.

**Layout rules**
- Fixed chrome: `header` top, `pager` right-center, `bottombar` bottom. All three use `mix-blend-mode: difference` so they stay legible over any panel color.
- Category panel composition: `foot` row top-pinned (index + count), big word bottom-pinned and flush-left, `topics` list right-middle.
- Intro and contact panels are center-justified vertically.

**Transparency + blur**
- Minimal. Chrome uses `mix-blend-mode: difference`, not blur.
- Muted text is solid `rgba(10,10,10,.55)` on light panels, `rgba(255,255,255,.7)` on dark.

**Imagery**
- The system currently uses **no imagery**. Type is the image. If imagery is introduced later, treat it full-bleed, no rounding, no caption chrome.

**Backgrounds**
- Flat solid fills only. No gradients, no textures, no noise.

---

## ICONOGRAPHY

**Approach: essentially iconless.** The brand communicates through type, counters, and color. When a graphic element is required:

- **Dot indicator** — 6–7px filled circle (used in pager + "Available" status).
- **Plus sign** — `+` character, rotated 45° into `×` on open state (reserved for drawer patterns).
- **Arrow** — built from 1px CSS borders, not SVG, for scroll hints.
- **No emoji. No icon fonts. No SVG sprites.**

If an icon is genuinely needed in a future surface, use [Lucide](https://lucide.dev) (CDN: `https://unpkg.com/lucide-static@latest/`), 1.5px stroke, black, 20px. Flag any addition clearly.

---

## INDEX

- `README.md` — this file
- `colors_and_type.css` — CSS custom properties (tokens) + semantic classes
- `SKILL.md` — Agent Skill manifest
- `Portfolio.html` — canonical home page
- `preview/` — design-system card specimens
- `ui_kits/portfolio/` — React components + interactive index.html

## Caveats

- **Inter Tight** is a Google Fonts substitute for a paid grotesque (ABC Diatype, Söhne). Swap in the licensed font when acquired.
- No logo file exists yet — the wordmark *is* the identity. A monogram (`MK`) card is provided as a placeholder.
- No photography has been art-directed. When imagery is added, confirm direction (warm vs cool, grain, b&w).
