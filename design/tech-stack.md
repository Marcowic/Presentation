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
index.html          — reveal.js shell, includes all slide sections plus the inline
                       Reveal.initialize() config and stage-class sync script
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
