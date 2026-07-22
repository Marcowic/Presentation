---
title: Visual Theme
status: proposed — awaiting sign-off
---

# Visual Theme

Brief: "AI-centric but not too busy," smooth animation/transitions unconditional,
tech-focused audience (AI Coding Summit).

## Palette (proposed)

Dark-mode base — reads as "developer tool" not "corporate slide deck."

| Role | Color | Notes |
|---|---|---|
| Background | `#0a0e1a` (near-black navy) | Not pure black — has depth |
| Surface / card | `#131826` | Slightly lifted panels for quotes/code blocks |
| Primary accent | `#6366f1` → `#a855f7` gradient (indigo → violet) | Used sparingly: headings, active state, key numbers |
| Secondary accent | `#22d3ee` (cyan) | Contrast pop for highlights, links, small tags |
| Text primary | `#e8eaf0` | Off-white, not stark |
| Text muted | `#8b93a7` | Captions, metadata, speaker/date labels |

Avoids the cliché "purple/pink AI gradient on everything" — gradient is reserved for
accents (headings, dividers, key stat callouts), not backgrounds or large fills.

## Typography

- **Headings**: a clean geometric sans (e.g. *Space Grotesk* or *Sora* via Google Fonts) —
  slightly technical feel without being a full monospace.
- **Body**: *Inter* — high legibility at presentation distance.
- **Code / quotes / raw excerpts**: *JetBrains Mono* — reinforces "this is a real quote
  from a technical talk," visually distinct from your own commentary.

## Motion principles

- Reveal.js transition: **slide** as the default (directional, reads as "moving through
  a journey" — fits the London trip narrative), with **fade** used for
  section-break/mood slides.
- Fragment reveals: bullets and quote call-outs fade+rise in (`fade-up`), staggered —
  avoids the "everything appears at once" static feel.
- Background: a very sparse, slow-drifting particle/node canvas (looks like a faint
  neural net / constellation) at low opacity behind content — present but never
  competing with text. Toggle-able off per-slide if it's distracting during a
  text-heavy talk recap.
- No motion for motion's sake on data/quotes — animation should support reading order,
  not decorate.

## Layout patterns (to reuse across talks)

Once you start feeding me talks, each will likely use a small set of repeatable slide
templates so the deck feels systematic rather than bespoke-per-slide:

1. **Talk title/divider** — speaker, talk name, in-person vs. remote/async badge,
   session time if known.
2. **Gist slide** — your one-paragraph plain-English summary, large type.
3. **Key takeaways** — fragment-revealed bullet list (2–4 points).
4. **Raw excerpt / quote slide** — monospace, attributed, styled like a terminal or
   quote block.
5. **Synthesis/connection slide** (optional, used between talks) — how this talk
   connects to others / to the bigger theme.

## In-person vs. async badge

Small visual tag system to mark which talks you attended live vs. caught later:
- 🟢 "Live in London" — solid accent pill
- 🔵 "Watched async" — outline pill
(exact icon/wording TBD — open to your preference, could drop emoji entirely for a
more polished text+color-only tag)

## Open items
- [ ] Approve palette / typography direction
- [ ] Decide on particle background: yes/no, and how subtle
- [ ] Confirm in-person/async badge style
