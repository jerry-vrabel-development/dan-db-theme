# dan-db.com — Theme Refresh

A refreshed WordPress theme and a set of article cover images for Dan Davis-Boxleitner's
developer blog (dan-db.com). Built as a GeneratePress child theme, developed locally with DDEV.

## What this project delivers

1. **A custom child theme** (`gp-dan-db-child`) — a minimal, typography-first design inspired by
   the Drupal-community blogs Dan cited (dri.es, jrockowitz.com, hojtsy.hu, Palantir.net/ideas).
2. **Six cover images** — one per existing article, a cohesive abstract-geometric set.

## Design decisions & rationale

### Foundation: GeneratePress + child theme
GeneratePress is a lightweight, well-coded theme with a documented hooks/filters system and a
large free feature set. Building a **child theme** on top of it (rather than a theme from scratch)
means we inherit a solid, maintained foundation — accessibility, RSS, comments, responsive
behavior — and only write the code that makes the design ours. Updates to the parent theme won't
overwrite our work.

### Typography: Source Serif 4 (headings) + Inter (body)
The current trend for editorial/reading sites has moved back toward **serif headings paired with a
humanist sans-serif body** — it reads as credible and modern while keeping long-form text highly
legible on screen. This matches the reference blogs, which lean editorial. Fonts are **self-hosted**
(`.woff2` in the theme's `/fonts` folder) rather than loaded from Google, which is faster and avoids
third-party privacy concerns.

- Body: Inter, 19px, line-height 1.6 — a generous, comfortable reading size.
- Headings: Source Serif 4, tighter line-height for a confident editorial feel.

### Layout: single column, ~720px reading measure
All the reference sites use a single centered column with no sidebar. We constrained the content to
roughly 720px so line length stays in the comfortable 65–75-character range for reading. GeneratePress
defaults are wider because they accommodate sidebars we're not using.

### Color: slate-blue accent (#3a5a78)
A restrained palette — near-black text on off-white, with a single slate-blue accent for links and
small highlights. The cover images use the same palette so the site and the artwork read as one system.

### Cover images
Six abstract-geometric covers, one per article, generated with AI image tools (Ideogram, then Gemini
using the first image as a style reference to keep the set consistent). Each is an abstract visual
metaphor for its article's topic — layered isometric forms, thin linework, subtle grid texture, the
shared slate/navy/off-white/coral palette. All cropped to **1200×630** (the Open Graph / social-share
standard, so they display cleanly when shared on LinkedIn).

## Local development environment

- **DDEV** (Docker-based) running WordPress locally — no live-site risk during development.
- **WordPress** installed at the project root, served at `https://dan-db-wptheme.ddev.site`.
- Six placeholder posts created locally, mirroring the real article titles and dates, so the
  design could be tested against realistic content.

### Getting the local site running
```bash
ddev start
ddev wp theme activate gp-dan-db-child
```
Visit the URL DDEV prints. If starting fresh on a new machine, WordPress core and the database
are not committed (see below) — you'd re-run the DDEV WordPress setup and re-import content.

## What IS and ISN'T in this repo

**Committed:**
- The child theme (`wp-content/themes/gp-dan-db-child/`) — CSS, functions.php, self-hosted fonts.
- The source cover images (`_covers/`) and their cropped 1200×630 versions.
- This documentation.

**Not committed** (intentionally — see `.gitignore`):
- WordPress core files (downloadable, not our work).
- The database, uploads, and DDEV runtime files.
- Other themes and plugins.

## Outstanding / next steps

- **Deploy to live site**: package the theme and install on the live dan-db.com WordPress
  (method depends on the access available — admin upload, SFTP, or control panel).
- **Assign covers on live**: upload the six cropped images and set each as the matching post's
  featured image.
- **Content note**: the existing articles (2015–2016) lean toward web-marketing topics. If Dan is
  repositioning as a developer blog, he may want to prune or refresh them over time. Out of scope
  for this pass.

## Credits
Design & build: JV. Client: Dan Davis-Boxleitner (dan-db.com).
