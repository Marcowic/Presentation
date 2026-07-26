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
4. **Visual theme is restrained, not gimmicky.** Current direction is the Summit
   Arc (see [[visual-theme]]) — a narrative mountain/sunrise motif tied to the trip
   itself, not a literal tech/circuit aesthetic. Must not tip into busy, gimmicky, or
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
- Visual direction: **the Summit Arc** — a 5-stage narrative color progression
  (Night → Morning Rise → Foggy Interception → The Calm → Summit/Sunrise) that
  mirrors the trip itself, sharing one consistent mountain-silhouette-and-sun/moon
  shape system across all five stages. Replaces the original dark-navy/
  indigo-violet direction, which tested as a generic "AI product" look. Full
  detail and rationale in [[visual-theme]].
- Typography and exact per-stage hex values: not yet finalized (see
  [[visual-theme]] open items).
- Slide treatment: **two-tier**, locked. Splash/divider slides get full
  atmospheric Summit Arc art; content slides (talk recaps, takeaways, quotes)
  use a flattened identity band + solid stage-derived panel so text never sits
  directly on a gradient/fog layer. See [[visual-theme]].

## Open decisions
- [ ] GitHub username/repo name for the Pages URL
- [ ] Summit Arc stage-boundary trigger: even talk-count split vs. content-beat
      judgment (leaning content-beat) — see [[visual-theme]]
- [ ] Badge style for in-person vs async (emoji vs. text+color only)
- [ ] Theme clusters for talk grouping — pending enough talk content to see patterns

## Change log
- 2026-07-22 — Initial constitution written, consolidating decisions from project kickoff.
- 2026-07-22 — Added local-preview requirement, always-current README requirement, and
  no-sensitive-info-committed requirement.
- 2026-07-24 — Visual direction pivoted from dark-navy/indigo-violet to the
  **Summit Arc** (5-stage narrative color progression) after the original direction
  tested as a generic/overused "AI product" look. See [[visual-theme]] change log
  for the full exploration trail.
- 2026-07-26 — Locked the two-tier splash/content slide treatment to resolve a
  readability tension with the Summit Arc's atmospheric backgrounds (most acute
  on Stage 3, Foggy Interception). See [[visual-theme]] for detail.
