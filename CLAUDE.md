# CLAUDE.md — instructions for AI sessions on this repo

This is Mary Clayton Soto's personal portfolio: a single-file site (`index.html`) published via GitHub Pages at https://maryclaytonsoto.github.io. Read `index.html` and `status.md` in full before making changes — status.md holds project state, the hiring-manager review, remaining to-dos, and a "Next session" queue of changes Mary has already requested. Start there: it includes organic section separators, converting her uploaded doodles into graphics, larger text, front-page reformatting, and adding personal details/photos.

## Architecture

- Single `index.html`: all CSS and JS inline. `font-samples.html` is a standalone font-explorer page, not linked from the site.
- Six tabs (Home, Projects, Experience, Publication, Art, Contact/Resume): JS show/hide panels, URL-hash navigable, hamburger menu below 700px.
- The Art tab is toggleable: `SHOW_ART_TAB` constant at the top of the script. `false` hides it from the rendered site without deleting the section.
- Cards: `.card` with `.card-a/b/c` gradient top borders. New entries = duplicate a card block. `.card-media` divs are photo/file placeholder slots; `.org-link` is the small link under card titles; `.art-grid` holds artwork cards.

## Theming — the only way to change colors

One block at the top of the CSS defines the whole scheme: `--bg`, `--text`, `--text-muted`, `--c1`–`--c4`. Everything else derives via `color-mix()` — the derived mixes are currently tuned for a LIGHT background (see the note in the CSS if switching back to dark). Never hard-code hex colors anywhere else. **Documented exception:** the bubble illustration colors (`FILM` and `SHEEN` arrays in the bubble script) — illustration-only, same pattern as the retired sketch `--taupe`/`--rose`. Current theme: warm cream bg, charcoal text, earthy accents (terracotta), with the bright pink→coral→orange ombre as the signature gradient.

**Hero visual (v5.3, current):** a photoreal **soap-bubble field** on `<canvas>` behind the name — glassy body, faint interior sheen, a THIN iridescent thin-film rim, soft specular highlights, gentle rise and drift. Hero bubbles are poppable on click/tap; every other tab carries the same bubbles idling non-interactively behind the content. One shared engine: `createField(canvas, opts)`.

**Retired — do not reintroduce:** the parametric mesh ribbon and all mesh flow waves (engine left dormant on purpose, no `addMesh` calls); any hazy iridescent gradient background behind the bubbles (rejected twice — real liquid iridescence needs a video or WebGL shader, not CSS blobs); a thick rainbow bubble rim (reads "kiddish" — keep it thin); grey hairline dividers sectioning the content.

**Gradient rule:** never blend a cool color directly into pink — the midpoint renders purple, which Mary hates. Multi-color gradients use short blend zones between stops (see `--grad-strip`). The current palette is all-warm so it's safe, but the rule applies if a cool color ever returns.

Fonts: **Cormorant Garamond** (display/headings) + **EB Garamond** (body, nav tabs, paragraphs) via Google Fonts. Inter is still loaded as a fallback but is no longer the body font. Don't change without being asked. Playfair Display is approved as a reserve option. ⚠️ EB Garamond was matched from a font sample Mary sent and is **unconfirmed** — if it's the wrong face it's a one-line swap in `--body`.

## Mary's working rules — strict

1. Match the existing visual style exactly; no new colors, fonts, or layout patterns unless she explicitly asks for a redesign.
2. Report every placeholder replacement: what was replaced, and with what, so she can review.
3. Flag anything that could break the 700px mobile breakpoint before doing it.
4. Ask for real content (photos, links, publication details, resume PDF) — never invent final-sounding text. Her real info comes from her resume; her phone number is intentionally NOT on the public site.
5. Draft text in her voice, plainly — first person, conversational, no emojis, no AI filler. Nothing that reads like a resume or a brochure. Avoid "curiosity," "passion," "thrive," "journey," and grand metaphors; Mary will call that cheesy and ingenuine.
6. Never mention her AP Lang autoethnography essay in site copy — that example is specific to the paper and not relevant.
7. She iterates fast and reacts to what she sees: make the change and show her rather than writing long explanations. If something genuinely can't be done well, say so plainly instead of shipping a weak approximation.

## Workflow

- Commit with short descriptive messages. Mary runs `git push` herself (requires her credentials). Remind her to push after committing.
- After edits, verify: all tabs navigable, `@media (max-width: 700px)` intact, no cool-into-pink gradient blends, no hard-coded hexes outside the theme block.
- Update status.md when project state changes meaningfully.
- `aesthetic.md` is the portable spec of Mary's visual style. Whenever the site's look changes (palette, fonts, illustration style, layout patterns), update the matching CURRENT STYLE subsection and add a dated changelog line there.
