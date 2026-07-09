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
- Display (name, headings, section titles): **Cormorant Garamond** 500–600. Hero name very large (clamp up to ~8.5rem), set as two intentional lines: "Mary Clayton" roman, "Soto" italic and offset right, nesting into the hero mesh ribbon. Never allow an accidental wrap of the name.
- Body / UI (paragraphs, nav, labels, buttons): **Inter** 400–600, tight tracking (~-0.01em). EB Garamond retired from body.
- Eyebrow labels: Inter 11px, uppercase, 0.14em letterspacing, muted brown.
- Sign-off (footer): catchphrase "Building @ the intersection of science & creativity." in Cormorant italic over the footer stroke, then the signature **"xx, MC"** in Mary's own handwriting font (**Handwriting MCS**, `fonts/Handwritingmcs-Regular.ttf`). Both approved by Mary verbatim. The handwriting font is reserved exclusively for the signature — never headings or body text.
- Disciplines line under the name: Cormorant italic, terracotta "/" separators.
- Hierarchy from size and space first, weight second.
- Approved reserve font: Playfair Display (unused so far). Rejected: Fraunces, Lora (too round).

### Illustration

- Hero graphic: a **generative parametric mesh ribbon** — a closed organic loop (spirograph/Lissajous family: harmonic center curve, ~64 fine strands weaving across the band) drawn live on a `<canvas>`, colored with the ombre (pink→coral→orange), ~0.6px strokes at ~0.55 alpha so overlaps read as translucent woven lattice on the cream ground. Cursor-reactive (eased rotation/warp) with slow ambient drift; `prefers-reduced-motion` gets one static render. Colors are read from the theme block at runtime — no hard-coded hexes in the script.
- **Mesh family (sitewide):** the same engine draws a **flat 2D paint-stroke ribbon** on each tab — a full-bleed static canvas of parallel hairlines (no weave, no animation) along a Catmull-Rom spline, with the ombre graded ACROSS the stroke (pink edge → orange edge), calligraphic width swell, tapered ends, and a hair of per-strand wobble. **Hard rules from Mary:** (1) strokes and especially their loops live in WHITESPACE — right of section titles (x ≳ 0.36 of viewport) and above content, or in the right margin; never behind text and never parked behind a heading; (2) these are static — 2D paint strokes, not dynamic 3D woven tubes (she rejected both the parked blobs and the animated tube ribbons); (3) each tab's route is unique but the language identical. The footer carries a low flat wave in the same style. Flow strokes are hidden below 760px (no whitespace to live in). Only the hero loop is woven/3D/animated/cursor-reactive. New placements reuse this engine with new waypoints, never a second visual language.
- The earlier hand-drawn sketch style (wobbly beziers, construction guides) is retired from the hero but remains an approved accent language.
- Mood: mathematical yet organic — mirrors Mary's art themes (order and spontaneity).
- (Queued: Mary's own doodles will be converted into graphics and may join as accents.)

### Layout & components

- Content column max 1160px, generous whitespace rhythm (sections separated by space, never bands or rules), fully responsive, hamburger nav below 760px.
- Sticky header, hairline bottom border, sans pill nav links; active tab is a pill filled with the signature ombre, white text (same pill inset in the mobile menu).
- Two radii, held: near-square 2px on cards/frames, full-pill (9999px) on controls (nav pills, buttons). Flat surfaces, no shadows; separation via warm hairlines (`color-mix` of ink at 7–14%).
- Projects and Art: gallery-wall grid — 2-up framed pieces (4:3 paper frame, hairline border) with gallery-label text below (eyebrow + dates meta line, serif title, small description). Experience/Publication: editorial two-column hairline rows (meta left, serif title + body right).
- Ombre appears only through the mesh family (hero ribbon, section accents, contact band, footer ribbon — all translucent and quiet) and the active nav pill. No solid ombre fills anywhere else. Terracotta reserved for tiny touches ("/" separators). (Retired: "exactly two moments" rationing, 2026-07-08, when Mary asked for the mesh family sitewide.)
- Home about section: editorial two-column grid — heading rail (eyebrow + serif title) left, prose right; collapses to one column below 760px.
- Action color is warm near-black (ink): pill buttons, ink underlined links. The ombre is never a button fill (the nav pill is its one control appearance).
- Empty media slots render as quiet paper-surface frames with hairline borders (no dashed boxes).
- Motion: subtle scroll reveals (IntersectionObserver, 0.5s rise), 0.15s micro-transitions; `prefers-reduced-motion` respected.

### Implementation convention

All colors flow from one theme block of CSS custom properties (`--bg`, `--text`, `--text-muted`, `--c1`–`--c4`); every other tone derives via `color-mix()`. No hex hard-coded outside that block (exception: muted sketch-only colors, documented in the derived block).

---

## CHANGELOG

- **2026-07-08** — v4.5 "Paint Strokes": Mary rejected the v4.4 animated tube ribbons and their text-overlapping placement. Flow ribbons flattened to static 2D paint strokes (parallel hairlines, ombre across the stroke, no motion) and repositioned so all loops sit in whitespace right of titles / above content; hidden on mobile. Sign-off finalized per Mary: "Building @ the intersection of science & creativity." + handwritten "xx, MC" (replaces draft "curiosity, made tangible" and "Mary Clayton" signature).
- **2026-07-08** — v4.4 "Flow Lines": Mary rejected the static accent blobs behind section titles and the "random"-feeling bands; mesh family reworked into per-tab flowing path ribbons (Catmull-Rom waypoint routes with loops/sweeps modeled on her sketch, full-bleed, behind content). Contact band replaced by a contact flow path; footer ribbon kept. Signature added: her handwriting font (Handwriting MCS) in the footer with a catchphrase (draft text, pending her approval).
- **2026-07-08** — v4.3 "Mesh Family": the hero's parametric mesh language extended sitewide at Mary's request — per-tab title accent blobs (varied lobe counts), open tapered ribbon band on Contact, low ribbon in the footer. One shared canvas engine, slow-drift only for secondary meshes (hero stays cursor-reactive). "Ombre rationed to exactly two moments" rule retired in favor of "ombre only via the mesh family + nav pill."
- **2026-07-08** — v4.2 "Woven Hero": hero redesigned per Mary. Name set as two intentional lines (roman "Mary Clayton" / italic offset "Soto") interwoven with a new generative parametric mesh-ribbon canvas (ombre-colored, cursor-reactive, reduced-motion safe) that replaces the 3px ombre rule. About restructured to a two-column rail+prose grid. Ombre nav pill untouched. Hand-drawn hero sketch language retired from the hero.
- **2026-07-08** — Gallery frames now honor each image's natural aspect ratio (portrait / landscape / square) instead of a forced 4:3 `object-fit: cover` crop; grid uses `align-items: start` so mixed-height pieces align to the top. Empty/text-placeholder frames still fall back to the 4:3 paper slot (via `:frame:not(:has(img))`).
- **2026-07-08** — Content fill (no style change): real photos and copy added from Portfolio/PortfolioInfo.md. Nav reordered (Publication → "Research", moved to lead; order now Home · Research · Experience · Projects · Art · Contact). Projects trimmed to Rollator + Arduino (Yeast Library and Green Space removed) with real photos; Publication given real title + DOI and a BME 271 continuation entry; Art filled (Boundless, Owl, High School collection); About gained a third paragraph + a 2-up portrait pair (reuses the existing `.gallery-grid`/`.piece` pattern — no new CSS); Contact gained GitHub + gmail and a working resume PDF link. Phone still intentionally omitted. Meta description added.
- **2026-07-08** — v4.1 "Gallery Wall" (current): per Mary's feedback on v4 — Projects and Art become a 2-up gallery-wall grid (framed pieces + gallery-label text); Experience/Publication keep editorial rows; ombre-filled active nav pill reinstated (pill controls return, cards stay 2px). Fonts and palette unchanged from v4.
- **2026-07-08** — v4 "Editorial Gallery": restyled per the web-design-system skill at Mary's direction. Palette unchanged. Typography split to Cormorant display + Inter body (EB Garamond retired from body). Near-square 2px radii, flat hairline-row layout, ombre rationed to hero rule + active tab, ink as action color, subtle scroll reveals. Pill nav, gradient active pill, card gradient borders, dashed placeholders, and hand-drawn hero sketch retired. Thin-underline active tab retired same day in v4.1 (Mary preferred the ombre pill).
- **2026-07-06** — v3 "Sketchbook Sunset": cream/charcoal/earthy palette, bright ombre kept as signature, hand-drawn A+B hero sketch, non-italic subhead, bold hero name.
- **2026-07-06** — v2 "Navy Sunset": dark navy bg, cream text, sunset palette (gold/pink/coral/orange), Cormorant + EB Garamond adopted; teal removed; geometric orbit hero (retired — too minimalist/modern).
- **2026-07-06** — v1: black/cream with teal/magenta/orange color-blocking, sans-serif (retired); magenta removed for reading purple; Fraunces/Lora tried and rejected as too round.
