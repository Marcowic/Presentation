# AI Coding Summit — Trip Report

A stylised, tech-focused presentation recapping talks from an AI Coding Summit —
covering both sessions attended in person and talks caught up with async — with a
focus on the ideas, themes, and takeaways from a developer/AI-tooling perspective.

Built as a static [reveal.js](https://revealjs.com/) site, hosted free on GitHub Pages
at **https://marcowic.github.io/Presentation/**.

## Running locally

No build step, no dependencies to install — just a static file server.

```bash
python3 -m http.server 8080
```

Then open **http://localhost:8080** in a browser. Use arrow keys / spacebar / swipe to
navigate slides.

(Any static file server works — e.g. `npx serve`, VS Code's Live Server extension, etc.
`python3 -m http.server` is just the zero-install default.)

## Project structure

```
index.html          reveal.js shell — all slides, plus inline Reveal.initialize()
                     config and stage-class sync script
css/theme.css        custom Paper & Halo visual theme (5-stage accent system)
content/             per-talk source material (summary + raw excerpts, one file per
                     talk — all 8 are now built into index.html)
assets/images/       photos, screenshots, diagrams
design/              decision docs — see below
```

## Design docs

The `design/` directory tracks the reasoning behind how this deck is built:

- `design/constitution.md` — hard requirements, source of truth
- `design/tech-stack.md` — framework/hosting decisions
- `design/visual-theme.md` — palette, typography, motion
- `design/storytelling.md` — narrative structure
- `design/content-log.md` — index of talks covered

## Deployment

Hosted via GitHub Pages, served directly from static files in this repo (no CI/build
required). See `design/tech-stack.md` for details.
