---
title: Tech Stack & Hosting
status: decided
---

# Tech Stack & Hosting

## Framework: reveal.js

Loaded via CDN (jsdelivr) — no npm install, no build step, no `node_modules`.
The whole site is static files: `index.html`, `css/`, `js/`, `assets/`, `content/`.

Why:
- Built-in smooth GPU-accelerated transitions (slide/fade/convex/zoom) satisfy the
  "smooth animation/transitions, unconditionally" requirement out of the box.
- Fragment-by-fragment reveals for building up bullet points / diagrams within a slide.
- Nested vertical slides let a single talk go "deeper" (raw excerpts, quotes) without
  breaking the horizontal narrative flow.
- Speaker notes view (separate popup window w/ timer) — useful for live presenting.
- Zero build step means content changes (new talk summaries) are just editing HTML —
  fast iteration as content gets fed in over multiple sessions.

## Hosting: GitHub Pages — LIVE

- Repo: `Marcowic/Presentation`, served from `main` branch root via GitHub Pages
  (Settings → Pages → Deploy from a branch → `main` / root).
- Live URL: **https://marcowic.github.io/Presentation/**
- Deploy = push to `main`. No CI, no build step — Pages serves the static files as-is.

## Structure

```
index.html          — reveal.js shell, includes all slide sections, a page-wide
                       .page-halo div (see below), and the inline
                       Reveal.initialize() config + stage-class sync script
css/theme.css        — Paper & Halo theme, .stage-1…stage-5 accent classes
                       (see design/visual-theme.md)
content/             — per-talk source material (source material behind each talk's
                       slides; talks are hand-authored into index.html, not assembled
                       via the markdown plugin — see decision below)
assets/images/       — photos, screenshots, diagrams
design/              — this directory — decisions & storytelling docs
```

## Resolved decisions
- GitHub username/repo: **Marcowic/Presentation** — Pages URL confirmed above.
- Talk content lives **inline in index.html** as hand-authored `<section>` markup, not
  assembled from `content/*.md` via the reveal.js markdown plugin. `content/*.md` files
  remain the source material staging area per talk (summary + raw excerpts) that gets
  hand-converted into slides, per [[storytelling]].

## reveal.js layout notes (post-deploy fixes)

The deck runs at reveal.js's default 4:3 stage size (`960×700`, no explicit
`width`/`height` override), which reveal.js scales/letterboxes to fit the actual
viewport. This caused a few cross-browser and post-deploy issues, all fixed in
`css/theme.css` / `index.html`:

- `Reveal.initialize({ margin: 0, ... })` — removes reveal.js's default padding
  around the fitted stage, so content sits flush against the fitted edge.
- `--r-background-color` and `.reveal-viewport` background overridden to
  `var(--paper)` — the letterboxed area outside the 4:3 stage otherwise shows the
  base reveal.js theme's near-black background instead of the deck's paper ground.
- `overflow-x: hidden` on `html`, `body`, and slide sections — the corner halo
  glow intentionally spills past each slide's edge and was registering as
  page-level horizontal scroll on some browsers.
- The halo glow itself is **not** a pseudo-element scoped to `.reveal` or to
  individual slides — it's a dedicated `.page-halo` div, pinned via
  `position: fixed` + a high `z-index`, appended just before the reveal.js
  `<script>` tags in `index.html`. See [[visual-theme]]'s "Halo implementation
  note" for why a scoped pseudo-element didn't work (paint-order conflicts with
  reveal.js's own stacking/z-index during slide transitions).
