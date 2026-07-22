---
title: Project Constitution
status: source of truth — update when a requirement changes, don't let other docs drift from this
---

# Constitution

The non-negotiables and functional requirements for this project. Other `design/*.md`
files hold the *reasoning* and detail; this file holds the *rules*. If something here
conflicts with another doc, this file wins — fix the other doc.

## Purpose

A stylised, tech-focused presentation recounting the user's trip to the AI Coding
Summit in London — talks attended in person plus talks caught async/remote. Built
collaboratively: user feeds raw material per talk, Claude acts as co-director on
storytelling and visual presentation.

## Hard requirements (non-negotiable)

1. **Hosted on GitHub Pages, free.** No paid hosting, no services requiring a
   credit card. Must be reachable from any device via a plain URL.
2. **Smooth animations/transitions — unconditional.** Not a nice-to-have. Every
   navigation and reveal should feel fluid, not abrupt.
3. **No slide-count ceiling.** Never prune or compress content to "fit a deck size."
   User paces live and will explicitly say if/when something should be cut.
4. **Visual theme is AI-centric but restrained.** Tech/AI-flavored (dark UI, subtle
   network/circuit motifs, monospace accents) — must not tip into busy, gimmicky, or
   cliché "AI slop" aesthetics (no default purple-gradient-everything, no stock
   robot/brain imagery).
5. **Static site, no build step required to run it.** Editing content should mean
   editing a file and refreshing — not running a build pipeline. (Currently: reveal.js
   via CDN.)
6. **Must be runnable locally to preview before hosting.** A trivial local server
   (e.g. `python3 -m http.server`) is enough — no dependency on the site actually
   being deployed to check how it looks/feels.
7. **README exists and is kept current.** Must always contain: local preview/testing
   steps, and a generic, non-personal blurb describing the content (AI knowledge
   sharing recap) — not a diary entry. Update it whenever local run steps or the
   top-level structure changes.
8. **Never commit sensitive information.** No personal contact details, internal
   company info from talks, unpublished/embargoed material, credentials, or anything
   the user wouldn't want public — this repo is public-hostable via GitHub Pages.
   Check content before committing; ask the user if a raw excerpt looks borderline.

## Roles

- **User**: supplies raw material per talk — attendance mode (in-person London /
  async), their own summary + gist of understanding, talk details (speaker, title,
  context), raw excerpts/quotes. Also the final call on pacing, pruning, and any
  creative direction disagreement.
- **Claude (co-director)**: proposes how to structure each talk into slides, how talks
  connect to each other thematically, visual/motion treatment, and flags when a
  storytelling choice trades off against another. Maintains `design/` docs as
  decisions are made. Does not prune content unless asked.

## Content intake format (per talk)

See [[storytelling]] for full detail. Minimum fields per talk:
- Attendance mode (in person / async)
- User's summary/gist
- Talk details (speaker, title, session context)
- Raw excerpts

Each talk gets logged in `design/content-log.md` and a source file under `content/`.

## Current stack decisions (see [[tech-stack]] for rationale)

- Framework: **reveal.js** (CDN-loaded, no npm/build step)
- Hosting: **GitHub Pages**
- Typography: Space Grotesk (headings) / Inter (body) / JetBrains Mono (quotes/code)
- Palette: dark navy base, indigo→violet gradient accent, cyan secondary accent
- Background motion: sparse drifting node/constellation canvas, low opacity

## Open decisions
- [ ] GitHub username/repo name for the Pages URL
- [ ] Particle background density/speed — pending user feedback on current scaffold
- [ ] Badge style for in-person vs async (emoji vs. text+color only)
- [ ] Theme clusters for talk grouping — pending enough talk content to see patterns

## Change log
- 2026-07-22 — Initial constitution written, consolidating decisions from project kickoff.
- 2026-07-22 — Added local-preview requirement, always-current README requirement, and
  no-sensitive-info-committed requirement.
