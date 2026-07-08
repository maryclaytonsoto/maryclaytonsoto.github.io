# Website Redesign — What to KEEP

Context note for the redesign. Everything listed here should carry over; everything *not* listed is open to being redesigned. No changes have been made to the site yet.

## 1. The tab structure (keep the tabs, redo their formatting)

Keep all six tabs and their order. These are the sections; only their look/layout should change.

1. Home
2. Projects
3. Experience
4. Publication
5. Art
6. Contact / Resume

Also worth keeping about the tabs, as behavior (not styling):
- They work as a single-page tab switcher (one panel visible at a time, no full page reload).
- Deep-linking works — a URL like `#projects` opens straight to that tab.
- The Art tab has a built-in on/off switch (`SHOW_ART_TAB`) so it can be hidden from the public site without deleting the content.

I like the tabs themselves. I do **not** like the current formatting of them (the pill/rounded nav styling, the gradient "active" pill, etc.) — that's fair game to redesign.

## 2. My name, big, on the home page

Keep the hero treatment where my name — **Mary Clayton Soto** — is set large and prominent at the top of the Home page. The large display-type name is a feature I want to preserve. The surrounding hero layout (the sketch graphic, subhead, tagline placement) can be redesigned.

Current specifics of that name treatment (for reference):
- Font: **Cormorant Garamond** (display serif), weight 700
- Size: ~2.9rem desktop
- Directly beneath it: a smaller subhead line — "Biomedical Engineering · Mathematics · Visual Arts"

## 3. The color scheme

Keep the current palette. It's a warm cream background with charcoal text, an earthy brown accent, and a signature pink → coral → orange ombre gradient.

Exact values (from the `:root` theme block):

| Role | Variable | Hex |
|------|----------|-----|
| Page background (warm cream) | `--bg` | `#f5f0e8` |
| Main text (dark charcoal) | `--text` | `#3a3a38` |
| Muted / accent text (earthy brown) | `--text-muted` | `#8b6d54` |
| Terracotta / burnt sienna | `--c1` | `#c9845f` |
| Bright warm pink (ombre) | `--c2` | `#ff4f87` |
| Bright coral (ombre) | `--c3` | `#ff6f61` |
| Deep orange (ombre) | `--c4` | `#e85d04` |

The pink→coral→orange gradient (`--c2 → --c3 → --c4`) is the signature accent and should stay as the site's identity color. The whole palette is already centralized in one `:root` block, which makes it easy to preserve exactly.

## 4. Fonts (tied to the name, worth keeping)

- **Cormorant Garamond** — display serif used for the name, headings, and nav.
- **EB Garamond** — body serif for paragraph text.

Keeping these keeps the feel of the big-name treatment consistent.

---

## Open to redesign (NOT on the keep list)

Just to make the boundary clear, these are the things I want to rethink:
- Overall page layout and formatting of each tab
- The nav/tab styling (rounded pills, gradient active state)
- Card styling (gradient top-borders, shadows, dashed placeholder boxes)
- The hand-drawn hero SVG sketch
- Section-title gradient underline bars, uppercase tags, buttons
- General spacing, structure, and how content is presented within each section
