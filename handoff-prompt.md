# Handoff Prompt

Copy everything below the line into a new AI session when working on this site.

---

You are helping me improve my personal portfolio website. Single-file site: `index.html` in the repo `maryclaytonsoto/maryclaytonsoto.github.io`, published via GitHub Pages at https://maryclaytonsoto.github.io.

**Before doing anything, read these files in full, in this order:**

1. `CLAUDE.md` — working rules and architecture. Follow it strictly; it wins any conflict with this prompt.
2. `aesthetic.md` — my visual identity: palette, fonts, layout patterns, and rules (e.g. never blend a cool color into pink — it reads purple). Read the CHANGELOG top-down for the latest state.
3. `status.md` — project state, hiring-manager review, and remaining to-dos.
4. `index.html` — the site itself. All CSS/JS is inline; colors come only from the theme block at the top.

**Current state (as of July 8, 2026, session 3):**

- Style is **v4.1 "Editorial Gallery / Gallery Wall"**: warm cream palette (kept from day one), **Cormorant Garamond** display + **Inter** body (EB Garamond retired), near-square 2px cards + full-pill controls, flat hairline surfaces, the pink→coral→orange **ombre rationed to two moments** (the hero rule + the active nav pill). Ink (warm near-black) is the action color; the ombre is never a button fill.
- **Nav order:** Home · Research · Experience · Projects · Art · Contact/Resume. Tabs are JS show/hide, hash-navigable, hamburger below **760px**. Art tab toggles via `SHOW_ART_TAB`.
- **Content is filled with real material** (from my Portfolio folder): headshot + Duke portrait in About; Rollator and Arduino projects with photos (Yeast Library and Green Space were removed); Research tab has the real ACS publication (title + DOI) and a BME 271 continuation entry; Art has Boundless, Owl, and three earlier pieces (Holding Rainbow, Iridescent Fabric, Tiny Flame) in one gallery; Contact has GitHub + gmail + a working resume PDF. Images live in `images/`, PDFs in `files/`.
- **Gallery frames now honor each image's natural aspect ratio** (portrait/landscape/square, no forced crop); empty frames fall back to a 4:3 paper slot.
- My **phone number is intentionally NOT on the public site**.

**Known repo quirk — git locks:** this environment sometimes can't delete `.git/*.lock` files, which blocks commits. If a commit fails with "Unable to create '.git/HEAD.lock': File exists", run `rm -f .git/HEAD.lock .git/index.lock` then retry. I run `git push` myself.

**Possibly-uncommitted work:** the last edit (dropping the "Portfolio" label + hero kicker, clearer resume button, merging the Art gallery) may still be uncommitted due to the lock above — check `git status` / `git log` at the start and commit it if needed.

**Open to-dos (see status.md for full list):**

1. Two marked notes in the Research tab need my input: the **full author list** for the publication, and the **BME 271 project description + code repo link**.
2. Hiring-manager review items, highest impact first: **"my role:" lines** on the team projects (Rollator, Bass Connections); **2–3 concrete metrics**; a **"what I'm looking for next"** line in the hero; then favicon + Open Graph tags.
3. Optional: convert my own hand-drawn doodles into site graphics (ask me for the files); Education/Skills details if I want them.

**Housekeeping as you work:** update status.md when state changes; update aesthetic.md's CURRENT STYLE + dated changelog whenever the look changes. Commit with short descriptive messages; remind me to push. After edits, verify all tabs work, the **760px** mobile breakpoint is intact, and no colors are hard-coded outside the theme block.

**My rules, in short (full version in CLAUDE.md):** match the existing style exactly unless I ask for a redesign; tell me what placeholder text you replace; flag mobile-responsiveness risks before acting; ask me for real content instead of inventing it; write in my plain voice, no emojis.
