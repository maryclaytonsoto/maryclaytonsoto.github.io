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

- All serif. Hierarchy via size and color, not weight stacking.
- Headings / nav / name: **Cormorant Garamond** 600–700. Hero name large and bold (~2.9rem).
- Body: **EB Garamond** regular. (Queued: increase base size, ~1.15–1.25rem.)
- Subtitle lines: EB Garamond, no italics, smaller, muted brown, letter-spaced, middot separators colored pink and orange.
- Approved reserve font: Playfair Display (unused so far). Rejected: Fraunces, Lora (too round).

### Illustration

- Hand-drawn, never geometric-perfect: sketched SVG with wobbly bezier paths, round caps, varied stroke weights.
- Motifs: dashed architectural construction guides + measurement ticks (taupe/charcoal, blueprint feel) combined with flowing ribbon waves; exactly one thick ribbon carries the sunset ombre; tiny bright dots as punctuation.
- Mood: organized and professional, not chaotic. See `design-options.html` for the explored directions (A+B chosen).
- (Queued: Mary's own doodles will be converted into graphics and may replace/join these motifs.)

### Layout & components

- Content column max 960px, generous spacing, fully responsive, hamburger nav below 700px.
- Sticky header with thin ombre color-block strip on top; pill nav links, active pill filled with the warm ombre.
- Cards: 14px radius, soft warm shadow, 6px gradient top border rotating through accent variants.
- Section headings: short gradient underline bar. (Queued: replace bars with organic/hand-drawn separators.)
- Hero: bordered rounded panel, text left / sketch right, stacks on mobile.
- Empty media slots render as dashed-border placeholders.

### Implementation convention

All colors flow from one theme block of CSS custom properties (`--bg`, `--text`, `--text-muted`, `--c1`–`--c4`); every other tone derives via `color-mix()`. No hex hard-coded outside that block (exception: muted sketch-only colors, documented in the derived block).

---

## CHANGELOG

- **2026-07-06** — v3 "Sketchbook Sunset" (current): cream/charcoal/earthy palette, bright ombre kept as signature, hand-drawn A+B hero sketch, non-italic subhead, bold hero name.
- **2026-07-06** — v2 "Navy Sunset": dark navy bg, cream text, sunset palette (gold/pink/coral/orange), Cormorant + EB Garamond adopted; teal removed; geometric orbit hero (retired — too minimalist/modern).
- **2026-07-06** — v1: black/cream with teal/magenta/orange color-blocking, sans-serif (retired); magenta removed for reading purple; Fraunces/Lora tried and rejected as too round.
