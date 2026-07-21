# Project Status — Personal Portfolio Website

Last updated: July 20, 2026 (end of session 5)

## Session 5 (July 9–20, 2026) — v5 → v5.3 "Bubbles"

Mary explored four layout directions from style references she supplied (dope.security
boarding-pass, Integrated Biosciences lab, monopo saigon editorial, and an aurora-blob
page she uploaded). Proof-of-concept pages were built in `Website/` — `poc-boardingpass.html`,
`poc-lab.html`, `poc-editorial-bubbles.html`, `poc-aurora-blobs.html` — all in her existing
palette. She chose the **bubble** direction and it was merged into the real site.

**Landed:**

- **Hero rebuilt.** Name is now ONE line, ALL CAPS, one uniform Cormorant style,
  `clamp(1.9rem, 7.4vw, 5.6rem)`, `0.05em` tracking, `nowrap`, centered in a tall opening
  view (`min-height: min(86vh, 780px)`). Two-line roman/italic-offset name retired.
- **Bubble field** replaces the hero mesh ribbon: photoreal soap bubbles on `<canvas>` —
  glassy Fresnel body, drifting interior sheen pockets, a THIN conic thin-film rim, thin
  white glass edge, big soft specular + glint + lower-right crescent, gentle rise/drift/squash.
  Hero bubbles are **poppable** (click/tap → expanding ring + droplets → respawn). All other
  tabs got `.bubble-idle` canvases: same bubbles, non-interactive, fewer/smaller, wafting
  behind content. One shared engine `createField(canvas, opts)`; hidden tabs skip work.
- **Mesh waves killed** entirely (hero ribbon, per-tab flow waves, footer wave) at her request.
  Engine left dormant (no `addMesh` calls); `.mesh-flow`/`.mesh-footer` set to `display:none`.
- **Grey hairline dividers removed** (hero bottom, `.entry` rows, footer top) — she disliked
  lines sectioning/interrupting content. Header + mobile-nav hairlines kept.
- **Body font** switched Inter → **EB Garamond**, matched from a font sample she sent.
  ⚠️ Unconfirmed — may be the wrong face; one-line swap in `--body` if so.
- **Copy rewritten to first person**, conversational, across all project, experience, and
  publication blurbs (was reading like a resume).
- **About rewritten twice.** A multiplicity-themed draft (drawn from an old personal essay
  about bubbles as a "bounded infinity" self-portrait) was rejected as "fake and cheesy and
  ingenuine." Current version is plain and grounded. The multiplicity/bubble meaning now
  lives on the **Art page** instead, tied to her recurring hands + bubbles imagery.
  **Her AP Lang autoethnography must never be mentioned** — not relevant.
- Small: nav wordmark ALL CAPS + `0.06em`; disciplines separator `/` → **×** (terracotta);
  tagline forced to one line (wraps again below 760px); About heading kept as
  "Where Fields Overlap."

**Rejected — do not reintroduce:** the mesh waves; any hazy iridescent gradient background
behind the bubbles (tried twice — real liquid iridescence needs a video or WebGL shader, not
CSS blobs); a thick rainbow bubble rim ("kiddish"); grey sectioning hairlines.

**Blocked:** a stale `.git/index.lock` prevented committing. Last commit is `094e106`
("Hero: photoreal poppable bubble field, name on one line; retire mesh waves"); **everything
after that is uncommitted.** Delete the lock locally, commit, and push.

**Not eyeballed by the assistant:** no headless browser was available this session, so all
work was verified by syntax/structure checks. Mary reviewed rendering in her own browser.

## Session 4, part 4 (July 8, 2026) — v4.5 "Paint Strokes" + final sign-off

Mary rejected the v4.4 ribbons: loops must sit in whitespace (not behind text), and the ribbons should be static 2D paint strokes, not dynamic 3D woven tubes (mesh look kept). She also finalized the sign-off text.

- Flow ribbons redrawn as flat strokes: parallel hairlines, ombre graded across the stroke (pink edge → orange edge), calligraphic width swell, slight per-strand wobble, tapered ends. No animation — drawn once (redrawn on resize/tab show). Hero loop unchanged (still woven + cursor-reactive).
- All five routes repositioned into whitespace: top-right of each tab, loops right of the titles, tails down the right margin. Verified against title/content exclusion zones in a rendered layout check (no collisions at 1440px). Footer band converted to the same flat language. Flow strokes hidden below 760px — phones have no whitespace for them (flagged per mobile rule; footer + hero still show).
- Sign-off finalized by Mary: catchphrase "Building @ the intersection of science & creativity." (Cormorant italic, over the footer stroke) then "xx, MC" in her handwriting font. Draft "curiosity, made tangible" retired. Glyph coverage for "xx, MC" verified.
- JS: drawOpen removed, drawFlow rewritten (static, non-wrapping stroke gradient); rAF loop skips static meshes after first paint.

## Session 4, part 3 (July 8, 2026) — v4.4 "Flow Lines" + signature

Mary reviewed v4.3 live and rejected the accent blobs parked behind section titles and the "random line" feel; she sketched a flowing route (enter from an edge, loop, sweep through whitespace) and asked for unique-but-cohesive per-page graphics. She also uploaded her handwriting font (`Handwritingmcs-Regular.ttf`) and asked for a signature with a short catchphrase.

- Accent blobs and the Contact band removed. Each tab (Research, Experience, Projects, Art, Contact) now has a full-bleed **flow ribbon**: mesh strands weaving around a Catmull-Rom spline through per-tab waypoints — Research loops beside the title then sweeps right (her sketch), Experience S-curves right-to-left, Projects loops right of the title, Art waves mid-page, Contact dives through the grid gap. Same engine, slow drift, behind content (z-index −1), tapered ends, `html{overflow-x:hidden}` guards the full-bleed. Footer ribbon kept.
- Signature: font copied to `fonts/`, `@font-face` "Handwriting MCS" (81 glyphs, verified covers "Mary Clayton"), used ONLY for the footer signature over the ribbon. **Catchphrase "curiosity, made tangible" is my draft (from her About wording) — Mary must approve or replace it.**
- Verified: JS syntax, tag balance, flow-spline math (217 finite points, sane y-range), font glyph coverage. Same caveat: no rendered screenshot; Mary should eyeball locally, then push.

## Session 4, part 2 (July 8, 2026) — v4.3 "Mesh Family"

Mary asked for more blobby mesh graphics throughout the site — same idea as the hero, not identical, dynamic and cohesive. Her choices: integrated throughout; slow drift only for secondary meshes (hero stays cursor-reactive).

- Hero ribbon script refactored into a shared mesh engine (one IIFE, `addMesh(selector, params)`); all seven canvases run off a single rAF loop that skips hidden tabs and off-screen meshes.
- New placements: section-title accent blob behind Research (4-lobe), Experience (5-lobe), Projects (4-lobe pinched), Art (free 3-lobe) — 200px, 34 strands, 0.4 alpha, tucked left of/behind the serif title; an open tapered ribbon band on Contact between the heading and the grid; a low open footer ribbon on every page. All parameter variations were prototyped and visually confirmed before implementation.
- Mobile: accents shrink to 150px, bands shorten; reduced-motion renders every mesh as one static frame.
- aesthetic.md updated: mesh-family rules added; the "ombre rationed to exactly two moments" rule formally retired (moved to changelog per spec convention).
- Same caveat as v4.2: verified by code checks + prototype renders, not a browser screenshot — Mary should eyeball locally, then push.

## Session 4 summary (July 8, 2026) — v4.2 "Woven Hero"

Landing-page redesign per Mary (she disliked the accidental line break in her name and wanted a more creative, dynamic hero with parametric mesh-ribbon graphics). Her choices via clarifying questions: name interwoven with the graphic; interactive; full Home tab scope; graphic replaces the small ombre rule (ombre nav pills kept).

- **Hero:** name set as two intentional lines — "Mary Clayton" roman, "Soto" italic offset right — up to ~8.5rem, nesting into a new generative **parametric mesh ribbon**: a closed organic loop (harmonic/spirograph curves, 64 fine woven strands) drawn on `<canvas>` in the ombre colors, read from the theme block at runtime (no new hexes). Interactive: eased cursor rotation/warp plus slow ambient drift; pauses off-screen/on other tabs; static single render under `prefers-reduced-motion`; fewer strands below 760px. The 3px ombre rule is retired. Disciplines + tagline unchanged.
- **Home about:** editorial two-column grid (eyebrow + "Where fields overlap" rail left, prose right), collapsing below 760px. Prose and photo pair unchanged — no content invented.
- Verified: JS syntax, tag balance, no hard-coded hexes outside the theme block, 760px breakpoint intact, all-warm gradient. Ribbon math prototyped and visually confirmed (woven lattice at crossing frequency q=2, 64 strands).
- aesthetic.md updated (typography, illustration, layout, v4.2 changelog).
- **Mary should eyeball locally before pushing** — mesh/name overlap was verified by geometry calculation, not a rendered screenshot (no headless browser this session). Ribbon position/size tweaks are one line: `.hero-canvas` in the CSS.

## Session 2 summary (July 8, 2026)

Full restyle to v4 "Editorial Gallery" per the web-design-system skill, at Mary's direction (keep palette, revise everything else; her choices: serif+sans split, near-square corners, all-light staging, subtle reveals only). Palette, tab structure/behavior, big-name hero, and SHOW_ART_TAB all preserved. Changes: Inter adopted for body/UI (EB Garamond retired from body), 2px radii, flat hairline entry rows, pill nav replaced with quiet text links + ombre underline active state, gradient bars/dashed placeholders removed, ink-filled button, scroll reveals with prefers-reduced-motion support. aesthetic.md updated (CURRENT STYLE + changelog). Queue effects: item 1 (gradient bars) resolved by removal; item 3 (bigger text) resolved via Inter body sizing; item 4 (front page reformat) done as part of the restyle. Items 2 and 5 (Mary's doodles, personal details/photos) still open — need her files.

Follow-up same session (v4.1 "Gallery Wall"): Mary liked the fonts/palette but wanted a gallery layout and the ombre tabs back. Projects and Art now share a 2-up gallery-wall grid (4:3 framed image slot + gallery-label text below); Experience/Publication keep the editorial hairline rows; active nav tab is again a pill filled with the ombre (controls are pill-radius, cards stay 2px). Project frames are new empty image slots — they raise the priority of getting real project photos (hiring-manager review item 1).

## Session 1 summary

Built from scratch to a complete, content-filled site in one session: skeleton with tab navigation → dark navy serif redesign → resume content filled in → cream "Sketchbook Sunset" redesign (see `aesthetic.md`) with hand-drawn A+B hero sketch chosen from `design-options.html`. Repo docs established: `CLAUDE.md` (working rules), `aesthetic.md` (living style spec), `handoff-prompt.md` (session starter — kept current, points here). Site is committed locally; Mary pushes to GitHub Pages herself. Next session starts with the queue below.

## What this project is

A single-file personal portfolio site (`index.html`) for Mary Clayton Soto, Duke BME freshman interested in biomedical engineering, patent law, and the intersection of art and science. The repo is `maryclaytonsoto/maryclaytonsoto.github.io`, which publishes automatically to https://maryclaytonsoto.github.io via GitHub Pages once pushed.

## What has been provided so far

- Six-tab structure: Home, Projects, Experience, Publication, Art, Contact/Resume. Tabs are JS-driven (show/hide panels), navigable by URL hash, and collapse to a hamburger menu below 700px. The Art tab can be hidden from the public site via the `SHOW_ART_TAB` flag at the top of the script in `index.html`.
- Theming: one block at the top of the CSS (`--bg`, `--text`, `--text-muted`, `--c1`–`--c4`) controls all colors; derived tokens are currently tuned for a LIGHT background. Current theme (July 6, 2026 redesign): warm cream bg #f5f0e8, charcoal text #3a3a38, earthy brown muted text, terracotta #c9845f, plus the bright pink #ff4f87 / coral #ff6f61 / deep orange #e85d04 ombre trio. Hero uses a hand-drawn SVG blending architectural construction lines with a flowing ombre ribbon (chosen from design options A+B in `design-options.html`).
- Real content filled in from Mary's resume (July 6, 2026): bio, 4 projects, 6 experience entries, publication contribution, and contact info. Remaining placeholders: publication title, author list/DOI, and the resume PDF link.
- Original design: gradient color-blocking accents (teal #00b3a4, pink #ff4f87, coral #ff6f61, deep orange #e85d04 (magenta removed — read as purple)) against a near-black header and cream content background.
- Current revision (in progress): dark navy background overall, cream/white text, serif typography (Cormorant Garamond for headings, EB Garamond for body), with teal/pink/coral/orange accent pops.

## Working rules for revisions

1. Read all files before making changes; understand tab navigation and design language first.
2. Match the existing visual style exactly — no new palette, font, or layout pattern unless a redesign is explicitly requested.
3. Keep the five-tab structure unless told otherwise.
4. When replacing placeholder text, clearly report what was replaced and with what, for review.
5. Flag any change that could break mobile responsiveness before making it.
6. Ask for real content (bio, project details, resume file, contact info) — never invent final-sounding text.

## How revisions are approached

Styling lives entirely in CSS custom properties in `:root` at the top of `index.html`, so palette changes are made by redefining those variables rather than hunting through rules — this keeps every component (cards, hero, nav, placeholders) consistent automatically. Structural content is organized in clearly commented `<section>` blocks; new projects or experience entries are added by duplicating an existing `.card` block. Any change is verified against the 700px mobile breakpoint (hamburger menu, single-column grids, reduced type sizes) before committing. Changes are committed locally with descriptive messages; pushing to GitHub is done by Mary since it requires her credentials.

## Hiring-manager review (July 6, 2026)

Evaluation of the current site through an interviewer's eyes, framed by three portfolio principles: showcase decision-making, explain your role, present measurable impact.

**What already works:** clean and readable, real resume-grade content, clear organization, distinctive visual identity, mobile-friendly. A recruiter skimming for 30 seconds gets the essentials.

**Prioritized improvements:**

1. **No visuals yet (highest impact).** Every media slot is an empty placeholder. Hiring managers skim images before reading anything. Fill the hero photo, 2–3 project photos, and the FSU segmentation figure first — real photos of the hydrogel models and rollator prototype will do more than any text edit.
2. **Show decision-making, not just outcomes.** Cards currently say what was built, not what was considered and rejected. For 1–2 flagship projects (Rollator, Bass Connections), add a short "process" line: the options weighed, the constraint that drove the choice, why the final design won. Side-by-side iteration photos would be ideal.
3. **Clarify your individual role.** Bass Connections and the Rollator project are team efforts, but the cards don't say what Mary personally owned vs. contributed to. Interviewers probe this immediately. Add "my role:" phrasing (e.g., "I owned the mold design and material tuning; the team...").
4. **Add measurable impact.** Only one number appears on the whole site (~20,000 cells). Candidates for: classification accuracy improvement (%), hydrogel model cost vs. commercial trainers, users/patients affected by the rollator design, students taught in EGR105. Even rough "before → after" comparisons count.
5. **Finish the credibility items.** Resume PDF link is still dead; publication title/authors/DOI still bracketed. An empty "Publication" tab hurts more than no tab.
6. **State what you're looking for.** The hero says who Mary is but not what she wants next (e.g., "seeking Summer 2027 internships in medical devices / IP"). Recruiters need a call to action.
7. **Add proof links.** A GitHub profile for the coding work, and testimonials or a one-line quote from a PI/professor if obtainable.
8. **Small polish items:** meta description + Open Graph tags for link previews, a favicon, alt text on all images when added.

## Next session — Mary's requested changes (queued July 6, 2026)

Work these in order, then move to the hiring-manager review items. Housekeeping: mark items done here as they land, and update `aesthetic.md` (CURRENT STYLE + changelog) whenever the look changes.

1. **Title bars → organic.** Remove the little gradient bars under section headings, or replace them with something organic/hand-drawn (e.g., a sketched squiggle or brushstroke line matching the hero's ribbon style). They currently read too geometric for the new aesthetic.
2. **Convert Mary's own doodles into site graphics.** She will upload photos/scans of her hand drawings. Workflow: she provides image files → clean up (crop, remove background, possibly vectorize or keep as transparent PNGs) → use as hero visual, section separators, or accents. Ask her for the files at session start.
3. **Bigger text.** Increase base body text size sitewide (EB Garamond runs small — consider bumping body to ~1.15–1.25rem and rechecking heading scale against it).
4. **Reformat the front page (Home).** Layout adjustments to hero + About — get her specific direction at session start on what "adjusted formatting" means before changing layout. Flag mobile implications per working rules.
5. **Add personal details and pictures.** More personality in the About section plus real photos in the existing `.card-media` slots and hero/portrait slots. Ask her for the content and image files — do not invent details.

## Session 3 summary (July 8, 2026)

Content fill from `Portfolio/PortfolioInfo.md` and the Portfolio image folder (no style change). Nav reorganized: Publication renamed "Research" and moved to lead (Home · Research · Experience · Projects · Art · Contact) — done by reordering nav links only, panels left in source order since tabs show one at a time. Projects trimmed to Rollator + Arduino (Yeast Genomic Library and Green Space removed per Mary's note) with real optimized photos. Publication filled with real title + DOI (acsami.5c25569) and a second entry for the BME 271 final project as a continuation (links the PDF). Art filled: gallery intro, Boundless + Owl, and a High School Collection (Holding Rainbow, Iridescent Fabric, Tiny Flame). About gained a third paragraph and a 2-up headshot + Duke portrait pair (reuses existing gallery pattern). Contact gained GitHub + gmail and a working resume PDF link. Images optimized (EXIF-rotated, ≤1600px) into `images/`; PDFs into `files/`. Meta description added. `_cand/` scratch folder is gitignored.

Placeholders remaining (marked `.note` in the Publication tab): full author list; BME 271 description + code repo link — Mary to supply.

## Remaining to-do

- **Clear the stale `.git/index.lock`, commit the session-5 work, and push** (last commit `094e106`).
- **Confirm the body font** — verify EB Garamond is the face Mary meant, and whether the base size needs a bump (serif runs smaller/lighter than Inter at 16px).
- Publication: add full author list and the BME 271 project description + repository link (marked as notes in the tab).
- Decide whether to list phone number publicly (still intentionally omitted; it's on the resume).
- Consider the hiring-manager review items still open: "my role" phrasing on team projects, measurable impact numbers, a "what I'm seeking next" line in the hero, favicon/OG tags.
- Skills and Education details (GPA, coursework, Maclay salutatorian, activities) are not on the site — add if desired.
- Push to GitHub to publish.
