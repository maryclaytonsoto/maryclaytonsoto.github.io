# CLAUDE.md — instructions for AI sessions on this repo

This is Mary Clayton Soto's personal portfolio: a single-file site (`index.html`) published via GitHub Pages at https://maryclaytonsoto.github.io. Read `index.html` and `status.md` in full before making changes — status.md holds project state, the hiring-manager review, remaining to-dos, and a "Next session" queue of changes Mary has already requested. Start there: it includes organic section separators, converting her uploaded doodles into graphics, larger text, front-page reformatting, and adding personal details/photos.

## Architecture

- Single `index.html`: all CSS and JS inline. `font-samples.html` is a standalone font-explorer page, not linked from the site.
- Six tabs (Home, Projects, Experience, Publication, Art, Contact/Resume): JS show/hide panels, URL-hash navigable, hamburger menu below 700px.
- The Art tab is toggleable: `SHOW_ART_TAB` constant at the top of the script. `false` hides it from the rendered site without deleting the section.
- Cards: `.card` with `.card-a/b/c` gradient top borders. New entries = duplicate a card block. `.card-media` divs are photo/file placeholder slots; `.org-link` is the small link under card titles; `.art-grid` holds artwork cards.

## Theming — the only way to change colors

One block at the top of the CSS defines the whole scheme: `--bg`, `--text`, `--text-muted`, `--c1`–`--c4`. Everything else derives via `color-mix()` — the derived mixes are currently tuned for a LIGHT background (see the note in the CSS if switching back to dark). Never hard-code hex colors anywhere else; the only exceptions are `--taupe`/`--rose` in the derived block, used solely inside the hero sketch. Current theme: warm cream bg, charcoal text, earthy accents (terracotta), with the bright pink→coral→orange ombre as the signature gradient. The hero visual is a hand-drawn SVG (architectural guides + flowing ombre ribbon); `design-options.html` holds the four explored directions.

**Gradient rule:** never blend a cool color directly into pink — the midpoint renders purple, which Mary hates. Multi-color gradients use short blend zones between stops (see `--grad-strip`). The current palette is all-warm so it's safe, but the rule applies if a cool color ever returns.

Fonts: Cormorant Garamond (headings/nav) + EB Garamond (body) via Google Fonts. Don't change without being asked. Playfair Display is approved as a reserve option.

## Mary's working rules — strict

1. Match the existing visual style exactly; no new colors, fonts, or layout patterns unless she explicitly asks for a redesign.
2. Report every placeholder replacement: what was replaced, and with what, so she can review.
3. Flag anything that could break the 700px mobile breakpoint before doing it.
4. Ask for real content (photos, links, publication details, resume PDF) — never invent final-sounding text. Her real info comes from her resume; her phone number is intentionally NOT on the public site.
5. Draft text in her voice, plainly — no emojis, no AI filler.

## Workflow

- Commit with short descriptive messages. Mary runs `git push` herself (requires her credentials). Remind her to push after committing.
- After edits, verify: all tabs navigable, `@media (max-width: 700px)` intact, no cool-into-pink gradient blends, no hard-coded hexes outside the theme block.
- Update status.md when project state changes meaningfully.
