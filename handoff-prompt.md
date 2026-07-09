# Handoff Prompt

Copy everything below the line into a new AI session when working on this site.

---

You are helping me improve my personal portfolio website. Single-file site: `index.html` in the repo `maryclaytonsoto/maryclaytonsoto.github.io`, published via GitHub Pages at https://maryclaytonsoto.github.io.

**Before doing anything, read these files in full, in this order:**

1. `CLAUDE.md` — working rules and architecture. Follow it strictly; it wins any conflict with this prompt.
2. `aesthetic.md` — my visual identity: palette, fonts, layout patterns, and rules (e.g. never blend a cool color into pink — it reads purple). Read the CHANGELOG top-down for the latest state.
3. `status.md` — project state, hiring-manager review, and remaining to-dos.
4. `index.html` — the site itself. All CSS/JS is inline; colors come only from the theme block at the top.

**Current state (as of July 8, 2026, end of session 4 — style v4.5 "Paint Strokes"):**

- **Hero (Home):** my name is set as two intentional lines — "Mary Clayton" roman, "Soto" italic and offset right (never let it wrap accidentally) — interwoven with a **generative parametric mesh ribbon**: a closed woven loop drawn on `<canvas>` in the ombre colors, cursor-reactive with slow drift. This is the ONLY animated/3D mesh on the site.
- **Mesh family sitewide:** every other tab (Research, Experience, Projects, Art, Contact) has a **static 2D "paint stroke" ribbon** — flat parallel hairlines along a Catmull-Rom waypoint path, ombre graded across the stroke, no animation. **Hard rules:** strokes and their loops live in whitespace (top-right of each page, right of titles, right margin) — never behind text, never parked behind a heading; static only. The footer has a low flat wave in the same style. Flow strokes are hidden below 760px. One shared JS engine draws everything (`addMesh(selector, params)`) — new placements are new waypoint lists, never a second visual language. Colors are read from the theme block at runtime; no hexes in the script.
- **Footer sign-off (approved verbatim, don't change without asking):** "Building @ the intersection of science & creativity." in Cormorant italic, then **"xx, MC"** in my handwriting font (**Handwriting MCS**, `fonts/Handwritingmcs-Regular.ttf`). The handwriting font is for the signature ONLY.
- Style base is still the warm cream palette (kept from day one), **Cormorant Garamond** display + **Inter** body, 2px cards + pill controls, flat hairline surfaces. The ombre appears only via the mesh family + the active nav pill; ink is the action color. Home's About is a two-column rail + prose grid. The old 3px hero rule and the accent-blob/woven-tube ribbon experiments are retired — see aesthetic.md changelog (v4.2 → v4.5) for what I rejected and why, so you don't reintroduce it.
- **Nav order:** Home · Research · Experience · Projects · Art · Contact/Resume. Tabs are JS show/hide, hash-navigable, hamburger below **760px**. Art tab toggles via `SHOW_ART_TAB`.
- **Content is real** (from my Portfolio folder): headshot + Duke portrait in About; Rollator and Arduino projects with photos; Research tab has the real ACS publication (title + DOI) and a BME 271 continuation entry; Art has Boundless, Owl, and three earlier pieces; Contact has GitHub + gmail + a working resume PDF. Images in `images/`, PDFs in `files/`, my font in `fonts/`.
- My **phone number is intentionally NOT on the public site**.
- **Not yet eyeballed in a browser:** sessions 4's mesh work was verified by geometry checks and prototype renders, not screenshots. First thing: I should open the site locally and confirm the hero ribbon/name overlap and each tab's stroke placement look right; waypoint/CSS tweaks are one-liners.

**Known repo quirk — git locks:** this environment sometimes can't delete `.git/*.lock` files, which blocks commits. If a commit fails with "Unable to create '.git/HEAD.lock': File exists", delete the stale `.lock` files (may require enabling file deletion) then retry. Also: never `git add -A` — untracked `assets/` and `index.backup-*.html` files must stay uncommitted; add files by name. I run `git push` myself.

**Open to-dos (see status.md for full list):**

1. Two marked notes in the Research tab need my input: the **full author list** for the publication, and the **BME 271 project description + code repo link**.
2. Hiring-manager review items, highest impact first: **"my role:" lines** on the team projects (Rollator, Bass Connections); **2–3 concrete metrics**; a **"what I'm looking for next"** line in the hero; then favicon + Open Graph tags.
3. Optional: convert my own hand-drawn doodles into site graphics using the existing mesh/stroke engine or as cleaned-up images (ask me for the files); Education/Skills details if I want them.
4. Push to GitHub — several sessions of work may be committed but unpushed; check `git log` vs `origin/main`.

**Housekeeping as you work:** update status.md when state changes; update aesthetic.md's CURRENT STYLE + dated changelog whenever the look changes. Commit with short descriptive messages (named files only); remind me to push. After edits, verify all tabs work, the **760px** mobile breakpoint is intact, no colors are hard-coded outside the theme block, and any new mesh stroke stays out of text zones.

**My rules, in short (full version in CLAUDE.md):** match the existing style exactly unless I ask for a redesign; tell me what placeholder text you replace; flag mobile-responsiveness risks before acting; ask me for real content instead of inventing it; write in my plain voice, no emojis.
