# Project Status — Personal Portfolio Website

Last updated: July 6, 2026

## What this project is

A single-file personal portfolio site (`index.html`) for Mary Clayton Soto, Duke BME freshman interested in biomedical engineering, patent law, and the intersection of art and science. The repo is `maryclaytonsoto/maryclaytonsoto.github.io`, which publishes automatically to https://maryclaytonsoto.github.io via GitHub Pages once pushed.

## What has been provided so far

- Five-tab structure: Home, Projects, Experience, Publication, Contact/Resume. Tabs are JS-driven (show/hide panels), navigable by URL hash, and collapse to a hamburger menu below 700px.
- Skeleton only: all content is bracketed placeholder text (e.g., "[Bio paragraph goes here]"). No real bio, project, resume, or contact details exist yet — none should be invented.
- Original design: gradient color-blocking accents (teal #00b3a4, pink #ff4f87, coral #ff6f61, deep orange #e85d04 (magenta removed — read as purple)) against a near-black header and cream content background.
- Current revision (in progress): dark navy background overall, cream/white text, serif typography (Fraunces for headings, Lora for body — matching the soft serif reference provided), with the same teal/magenta/orange accent pops retained.

## Working rules for revisions

1. Read all files before making changes; understand tab navigation and design language first.
2. Match the existing visual style exactly — no new palette, font, or layout pattern unless a redesign is explicitly requested.
3. Keep the five-tab structure unless told otherwise.
4. When replacing placeholder text, clearly report what was replaced and with what, for review.
5. Flag any change that could break mobile responsiveness before making it.
6. Ask for real content (bio, project details, resume file, contact info) — never invent final-sounding text.

## How revisions are approached

Styling lives entirely in CSS custom properties in `:root` at the top of `index.html`, so palette changes are made by redefining those variables rather than hunting through rules — this keeps every component (cards, hero, nav, placeholders) consistent automatically. Structural content is organized in clearly commented `<section>` blocks; new projects or experience entries are added by duplicating an existing `.card` block. Any change is verified against the 700px mobile breakpoint (hamburger menu, single-column grids, reduced type sizes) before committing. Changes are committed locally with descriptive messages; pushing to GitHub is done by Mary since it requires her credentials.

## Remaining to-do

- Replace all bracketed placeholders with real content (needs: bio, project details, experience entries, publication info, email/LinkedIn, resume PDF).
- Add the resume PDF file to the repo and link it from the Contact/Resume tab.
- Push to GitHub to publish.
