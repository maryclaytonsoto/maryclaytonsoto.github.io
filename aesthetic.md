# Aesthetic Spec — "Sketchbook Sunset"

Portable design system for Mary Clayton Soto's visual identity. Any agent building or restyling a site for Mary should follow the CURRENT STYLE section. This file is a living document: whenever the site's look changes, update the relevant subsection below and add a line to the changelog at the bottom.

**How to update:** edit only the subsection that changed (palette, type, illustration, layout). Keep entries short. Date every changelog line. If a rule is retired, move it to the changelog rather than deleting it silently.

---

## CURRENT STYLE

### Palette

| Role | Value | Notes |
|---|---|---|
| Background | `#f5f0e8` | warm off-white cream |
| Card surface | cream mixed ~50% toward white | near-white warm paper |
| Text | `#3a3a38` | dark charcoal; headings slightly darker |
| Secondary text | `#8b6d54` | earthy brown |
| Earth accents | `#c9845f` terracotta, `#a89080` taupe, `#b8797a` dusty rose | muted, quiet |
| Signature ombre | `#ff4f87` pink → `#ff6f61` coral → `#e85d04` deep orange | the ONLY loud element; use sparingly |
| Vibrant accent option | `#f9a03f` gold, `#ff4f87` pink, `#ff6f61` coral, `#e85d04` deep orange | approved alternate quad when Mary wants brighter/more vibrant accents (the v2 sunset palette); gold extends the ombre to a four-stop gold→pink→coral→orange if desired |

**Standing rule (do not retire without asking Mary):** never blend a cool hue directly into pink — the gradient midpoint reads purple, which is forbidden. Multi-color strips use soft color-blocking (mostly-solid segments, short blend zones). Warm-only ombres may blend fully.

### Typography

- Serif display + neutral sans body split (the editorial system's signature move).
- Display (name, headings, section titles): **Cormorant Garamond** 500–600. Hero name very large (clamp up to ~7.5rem).
- Body / UI (paragraphs, nav, labels, buttons): **Inter** 400–600, tight tracking (~-0.01em). EB Garamond retired from body.
- Eyebrow labels: Inter 11px, uppercase, 0.14em letterspacing, muted brown.
- Disciplines line under the name: Cormorant italic, terracotta "/" separators.
- Hierarchy from size and space first, weight second.
- Approved reserve font: Playfair Display (unused so far). Rejected: Fraunces, Lora (too round).

### Illustration

- Hand-drawn, never geometric-perfect: sketched SVG with wobbly bezier paths, round caps, varied stroke weights.
- Motifs: dashed architectural construction guides + measurement ticks (taupe/charcoal, blueprint feel) combined with flowing ribbon waves; exactly one thick ribbon carries the sunset ombre; tiny bright dots as punctuation.
- Mood: organized and professional, not chaotic. See `design-options.html` for the explored directions (A+B chosen).
- (Queued: Mary's own doodles will be converted into graphics and may replace/join these motifs.)

### Layout & components

- Content column max 1160px, generous whitespace rhythm (sections separated by space, never bands or rules), fully responsive, hamburger nav below 760px.
- Sticky header, hairline bottom border, sans pill nav links; active tab is a pill filled with the signature ombre, white text (same pill inset in the mobile menu).
- Two radii, held: near-square 2px on cards/frames, full-pill (9999px) on controls (nav pills, buttons). Flat surfaces, no shadows; separation via warm hairlines (`color-mix` of ink at 7–14%).
- Projects and Art: gallery-wall grid — 2-up framed pieces (4:3 paper frame, hairline border) with gallery-label text below (eyebrow + dates meta line, serif title, small description). Experience/Publication: editorial two-column hairline rows (meta left, serif title + body right).
- Ombre rationed to exactly two moments: the 3px rule under the hero name and the active nav pill. Terracotta reserved for tiny touches ("/" separators).
- Action color is warm near-black (ink): pill buttons, ink underlined links. The ombre is never a button fill (the nav pill is its one control appearance).
- Empty media slots render as quiet paper-surface frames with hairline borders (no dashed boxes).
- Motion: subtle scroll reveals (IntersectionObserver, 0.5s rise), 0.15s micro-transitions; `prefers-reduced-motion` respected.

### Implementation convention

All colors flow from one theme block of CSS custom properties (`--bg`, `--text`, `--text-muted`, `--c1`–`--c4`); every other tone derives via `color-mix()`. No hex hard-coded outside that block (exception: muted sketch-only colors, documented in the derived block).

---

## CHANGELOG

- **2026-07-08** — Content fill (no style change): real photos and copy added from Portfolio/PortfolioInfo.md. Nav reordered (Publication → "Research", moved to lead; order now Home · Research · Experience · Projects · Art · Contact). Projects trimmed to Rollator + Arduino (Yeast Library and Green Space removed) with real photos; Publication given real title + DOI and a BME 271 continuation entry; Art filled (Boundless, Owl, High School collection); About gained a third paragraph + a 2-up portrait pair (reuses the existing `.gallery-grid`/`.piece` pattern — no new CSS); Contact gained GitHub + gmail and a working resume PDF link. Phone still intentionally omitted. Meta description added.
- **2026-07-08** — v4.1 "Gallery Wall" (current): per Mary's feedback on v4 — Projects and Art become a 2-up gallery-wall grid (framed pieces + gallery-label text); Experience/Publication keep editorial rows; ombre-filled active nav pill reinstated (pill controls return, cards stay 2px). Fonts and palette unchanged from v4.
- **2026-07-08** — v4 "Editorial Gallery": restyled per the web-design-system skill at Mary's direction. Palette unchanged. Typography split to Cormorant display + Inter body (EB Garamond retired from body). Near-square 2px radii, flat hairline-row layout, ombre rationed to hero rule + active tab, ink as action color, subtle scroll reveals. Pill nav, gradient active pill, card gradient borders, dashed placeholders, and hand-drawn hero sketch retired. Thin-underline active tab retired same day in v4.1 (Mary preferred the ombre pill).
- **2026-07-06** — v3 "Sketchbook Sunset": cream/charcoal/earthy palette, bright ombre kept as signature, hand-drawn A+B hero sketch, non-italic subhead, bold hero name.
- **2026-07-06** — v2 "Navy Sunset": dark navy bg, cream text, sunset palette (gold/pink/coral/orange), Cormorant + EB Garamond adopted; teal removed; geometric orbit hero (retired — too minimalist/modern).
- **2026-07-06** — v1: black/cream with teal/magenta/orange color-blocking, sans-serif (retired); magenta removed for reading purple; Fraunces/Lora tried and rejected as too round.
