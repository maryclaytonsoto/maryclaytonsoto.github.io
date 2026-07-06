# Project Status — Personal Portfolio Website

Last updated: July 6, 2026

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

1. **Title bars → organic.** Remove the little gradient bars under section headings, or replace them with something organic/hand-drawn (e.g., a sketched squiggle or brushstroke line matching the hero's ribbon style). They currently read too geometric for the new aesthetic.
2. **Convert Mary's own doodles into site graphics.** She will upload photos/scans of her hand drawings. Workflow: she provides image files → clean up (crop, remove background, possibly vectorize or keep as transparent PNGs) → use as hero visual, section separators, or accents. Ask her for the files at session start.
3. **Bigger text.** Increase base body text size sitewide (EB Garamond runs small — consider bumping body to ~1.15–1.25rem and rechecking heading scale against it).
4. **Reformat the front page (Home).** Layout adjustments to hero + About — get her specific direction at session start on what "adjusted formatting" means before changing layout. Flag mobile implications per working rules.
5. **Add personal details and pictures.** More personality in the About section plus real photos in the existing `.card-media` slots and hero/portrait slots. Ask her for the content and image files — do not invent details.

## Remaining to-do

- Publication tab: add the actual publication title, author list, and DOI/link (currently bracketed placeholders).
- Add the resume PDF file to the repo and link it from the Contact/Resume tab button.
- Decide whether to list phone number publicly (intentionally omitted from the site for privacy; it's on the resume).
- Skills and Education details (GPA, coursework, Maclay salutatorian, activities) are not on the site — add if desired.
- Push to GitHub to publish.
