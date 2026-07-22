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

## Hosting: GitHub Pages

- Repo root (or `/docs`) served directly as static site — free, no CI needed initially.
- URL format: `https://<username>.github.io/<repo-name>/`
- Deploy = push to `main` (or a `gh-pages` branch, TBD once repo is connected to GitHub).

## Structure

```
index.html          — reveal.js shell, includes all slide sections
css/theme.css        — custom AI-centric theme (see design/visual-theme.md)
js/custom.js         — custom background/interaction effects
content/             — per-talk markdown/HTML fragments (source material, staging)
assets/images/       — photos, screenshots, diagrams
design/              — this directory — decisions & storytelling docs
```

## Open items
- [ ] Confirm GitHub username/repo name for Pages URL
- [ ] Decide whether talk content lives inline in index.html or gets assembled from
      `content/*.md` via reveal.js's markdown plugin (leaning: markdown plugin, keeps
      index.html thin and each talk easy to edit independently)
