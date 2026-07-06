# Handoff Prompt

Copy everything below the line into a new AI session when working on this site.

---

You are helping me edit my personal portfolio website. It is a single-file site: `index.html` in the repo `maryclaytonsoto/maryclaytonsoto.github.io`, published via GitHub Pages at https://maryclaytonsoto.github.io. Before making any changes, read `CLAUDE.md`, `index.html`, and `status.md` in full — CLAUDE.md has the full working instructions, and status.md documents the project state and remaining to-dos. Follow CLAUDE.md if anything below conflicts.

Key facts about the code:

- All styling is inline CSS in `index.html`. Colors are controlled by ONE theme block at the top of the CSS (`--bg`, `--text`, `--text-muted`, `--c1` through `--c4`). To recolor anything, edit only those 7 hex values — everything else derives via `color-mix()`. Never hard-code new hex colors elsewhere.
- Never create a gradient that blends a cool color directly into pink — the midpoint renders as purple, which I hate. Multi-color gradients must use short blend zones between color stops (see `--grad-strip` for the pattern). The current palette is all-warm (sunset: gold, pink, coral, orange), so this only matters if a cool color is reintroduced.
- Fonts: Cormorant Garamond (headings/nav) + EB Garamond (body), loaded from Google Fonts. Don't change fonts unless I ask.
- Six tabs (Home, Projects, Experience, Publication, Art, Contact/Resume) are JS-driven show/hide panels navigable by URL hash, collapsing to a hamburger menu below 700px. Keep this structure. The Art tab is hidden/shown via the `SHOW_ART_TAB` constant at the top of the script.
- Cards use `.card` with `.card-a/b/c` gradient top borders; new project/experience entries are made by duplicating a card block. `.card-media` divs are placeholder slots for photos/files; `.org-link` is the small link under card titles.

My working rules — follow these strictly:

1. Match the existing visual style exactly. No new colors, fonts, or layout patterns unless I explicitly ask for a redesign.
2. If you replace any placeholder text (anything in [brackets]), tell me exactly what you replaced and with what.
3. Flag any change that could break mobile responsiveness (the 700px breakpoint) before making it.
4. Ask me for real content (photos, links, publication details, resume PDF) — never invent text that sounds final.
5. Write drafts in my voice, plainly — no emojis, no AI-sounding filler.

Current remaining to-dos (also in status.md): publication title/authors/DOI, resume PDF file + link, real photos for the `.card-media` slots, company links for Tallahassee Research Institute / FSU Microparticle Lab / Victor Tech, and deciding whether to add Skills/Education details.

After edits, verify: all five tabs still navigable, the mobile media query intact, no teal-into-pink gradient blends introduced. Commits should have short descriptive messages; I handle `git push` myself.
