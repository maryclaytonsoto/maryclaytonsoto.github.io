# Handoff Prompt

Copy everything below the line into a new AI session when working on this site.

---

You are helping me improve my personal portfolio website. Single-file site: `index.html` in the repo `maryclaytonsoto/maryclaytonsoto.github.io`, published via GitHub Pages at https://maryclaytonsoto.github.io.

**Before doing anything, read these files in full, in this order:**

1. `CLAUDE.md` — working rules and architecture. Follow it strictly; it wins any conflict with this prompt.
2. `aesthetic.md` — my visual identity: palette, fonts, layout, illustration rules. Read the CHANGELOG top-down for the latest state.
3. `status.md` — project state and remaining to-dos.
4. `index.html` — the site itself. All CSS/JS is inline; interface colors come only from the theme block at the top.

**Current state (July 20, 2026 — style v5.3 "Bubbles"):**

- **Hero (Home):** my name is ONE line, ALL CAPS, one uniform style — `MARY CLAYTON SOTO` in Cormorant Garamond 500, `clamp(1.9rem, 7.4vw, 5.6rem)`, `letter-spacing: 0.05em`, `white-space: nowrap` — vertically centered in a tall opening view (`min-height: min(86vh, 780px)`) on the plain cream ground. The old two-line roman/italic-offset treatment is retired.
- **Bubble field (the site's one visual motif):** photoreal soap bubbles drawn on `<canvas>` float behind the name. Each is built from a glassy Fresnel-bright body, faint drifting interior sheen pockets, a **THIN** iridescent thin-film rim (conic pastel spectrum, `lineWidth ≈ R*0.032`, alpha ~0.7), a thin white glass edge, a large soft specular highlight, a sharp glint, and a lower-right reflected crescent, plus gentle rise/drift/organic squash.
  - **Hero bubbles are interactive** — click/tap pops one into an expanding ring + colored droplets, and a new bubble rises to replace it.
  - **Every other tab** (Research, Experience, Projects, Art, Contact) has a `.bubble-idle` canvas: the same bubbles, **non-interactive**, fewer and smaller, wafting idly behind the content.
  - One shared engine: `createField(canvas, opts)`. New placements are new option objects, never a second visual language. Options: `interactive, area, min, max, maxR, speed, opacity`.
  - The bubbles' pastel thin-film/sheen colors (`FILM`, `SHEEN` arrays) are an **illustration-only documented exception** to the no-hardcoded-color rule, exactly like the retired sketch `--taupe`/`--rose`.
- **RETIRED — do not reintroduce:**
  - The **mesh waves** (hero parametric ribbon, per-tab flow waves, footer wave). Killed at my request. The mesh engine is left dormant in the script (no `addMesh` calls) and `.mesh-flow`/`.mesh-footer` are `display:none`.
  - **Iridescent background washes.** I tried a hazy gradient behind the bubbles twice and rejected both. The hero ground stays plain cream. If I ever ask for real liquid iridescence again, it needs an actual looping video or a WebGL shader — a CSS/blob approximation is not good enough.
  - The **thick rainbow rim** on bubbles — it read "kiddish." The rim must stay thin and delicate.
- **Grey hairline dividers removed** — I disliked lines sectioning/interrupting the content. Gone from the hero bottom, the `.entry` rows, and the footer top. The only hairlines left are under the sticky header and on the mobile nav dropdown.
- **Fonts:** display = **Cormorant Garamond**; body/UI (nav tabs + paragraphs) = **EB Garamond** (serif). Inter is still loaded as a fallback but is no longer the body font. ⚠️ **Unconfirmed:** EB Garamond was matched from a font sample I sent ("My wishlists"); if it's not the exact face I meant, it's a one-line swap in the `--body` token.
- **Copy voice:** all project / experience / publication blurbs are **first person and conversational** — not resume bullets. My About was rewritten plain and grounded after I said an earlier draft sounded "fake and cheesy and ingenuine." **Keep it unpretentious.** Avoid: "curiosity," "passion," "thrive," "journey," grand metaphors, and anything that sounds like a brochure.
- **The bubble motif has meaning** (from an old personal essay about my multiplicity): a bubble is a bounded infinity, a surface that never settles, refusing to be one thing — which is how I think about myself across math, art, and science. That idea lives on the **Art page**, tied to the recurring hands + bubbles imagery in my work. Keep the homepage and Art page from repeating each other. **Never mention the AP Lang autoethnography essay** — that example is specific to the paper and not relevant.
- Small details: nav wordmark is ALL CAPS with `0.06em` tracking; the disciplines line uses **×** (multiply sign, terracotta) not `/`; the tagline "Duke University, Pratt School of Engineering · Class of 2028" is forced to one line (`nowrap`, wraps again below 760px).
- **Footer sign-off (approved verbatim, don't change without asking):** "Building @ the intersection of science & creativity." then **"xx, MC"** in my handwriting font (**Handwriting MCS**, `fonts/Handwritingmcs-Regular.ttf`). That font is for the signature ONLY.
- Palette unchanged since day one: warm cream `#f5f0e8`, charcoal, earthy brown, terracotta, and the pink → coral → orange ombre. Never blend a cool color into pink — the midpoint reads purple.
- **Nav order:** Home · Research · Experience · Projects · Art · Contact/Resume. Tabs are JS show/hide, hash-navigable, hamburger below **760px**. Art tab toggles via `SHOW_ART_TAB`.
- My **phone number is intentionally NOT on the public site**.

**Known repo quirk — git locks (currently blocking!):** this environment often can't delete `.git/*.lock`, which blocks commits. There is a **stale `.git/index.lock` right now**. Delete it on my machine, then commit. Last commit is `094e106`; **everything after that is uncommitted.** Also: never `git add -A` — untracked `assets/` and `index.backup-*.html` must stay uncommitted; add files by name. I run `git push` myself.

**Open to-dos (see status.md for the full list):**

1. **Confirm the body font** — is EB Garamond the face I wanted, and does it need a size bump? (Serif runs smaller/lighter than Inter at 16px.)
2. Two marked notes in the Research tab need my input: the **full author list** for the publication, and the **BME 271 project description + code repo link**.
3. Hiring-manager items, highest impact first: **"my role:" lines** on team projects (Rollator, Bass Connections); **2–3 concrete metrics**; a **"what I'm looking for next"** line; then favicon + Open Graph tags.
4. Commit and push — several sessions of work are unpushed.

**Housekeeping as you work:** update `status.md` when state changes; update `aesthetic.md`'s CURRENT STYLE + a dated changelog line whenever the look changes. Commit with short messages (named files only); remind me to push. After edits verify: all tabs navigable, the **760px** breakpoint intact, no interface colors hard-coded outside the theme block, and no cool-into-pink gradient blends.

**My rules, in short (full version in CLAUDE.md):** match the existing style exactly unless I ask for a redesign; tell me what placeholder text you replace; flag mobile-responsiveness risks before acting; ask me for real content instead of inventing it; write in my plain voice, no emojis, no AI filler.

**How I work:** I iterate fast and react to what I see, so show me changes rather than describing them at length. I'll tell you bluntly when something's wrong — take the note and fix it without over-apologizing. If you genuinely can't do something (like exact photoreal iridescence in CSS), say so plainly instead of shipping a weak approximation.
