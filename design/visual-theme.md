---
title: Visual Theme
status: direction confirmed — Summit Arc; palette/type details still being refined
---

# Visual Theme

Brief: "AI-centric but not too busy" has evolved into something more specific — a
**mountain summit narrative** that mirrors the trip itself (arrival → climb →
obscured middle → clearing → arrival at the top). Discovered through several rounds
of mockup exploration (see change log) after the original dark-navy/indigo-violet
direction tested as too close to a generic "AI product" look.

## Core idea: the Summit Arc

The deck's palette is not fixed — it progresses across five stages as the audience
moves through the trip report, using one consistent visual system (same mountain
silhouette, same sun/moon motif) with only color, light, and atmosphere changing.
The color arc *is* the storytelling device, not decoration on top of it.

| Stage | Beat | Palette register | Sun/moon state | Notes |
|---|---|---|---|---|
| 1. Night | Arrival | Deep purple-black, faint stars, pale moon | Moon, high, cool white glow | Quietest stage — title/cold-open territory |
| 2. Morning Rise | Rising momentum | Indigo fading to dusty rose/coral | Sun breaking at horizon | Transition stage, allowed to feel in-between |
| 3. Foggy Interception | Dense/technical middle | Muted sage-gray, blurred fog bands, desaturated | Sun diffused, no hard edge | Deliberately the hardest-to-read stage — visually mirrors "in the weeds" content. Text must stay high-contrast even as the scene desaturates |
| 4. The Calm | Synthesis / connective tissue | Clear alpine green-blue | Sun soft and steady, mountain fully defined again | The "made it through the fog" payoff — best for slides needing careful reading |
| 5. Summit (Sunrise) | Closing | Warm terracotta-to-gold | Sun high and bright, mountain lit and solid | Earth tones reserved *only* for this stage so the finale reads as earned, not reused |

Color families are intentional, not arbitrary variety:
- **Purples** — night/pre-dawn only (stages 1–2), never reused later.
- **Greens** — the fog/calm middle only (stages 3–4).
- **Earth tones (terracotta/gold)** — reserved entirely for the stage 5 finale.

Full mockup reference (5 stages, one shared shape system): see conversation history
— to be re-published as a static reference image/palette sheet once locked, since
the live artifact link is ephemeral.

### Open question — what triggers a stage boundary?
Two options, not yet decided:
1. **Even split** — talk count divided into fifths. Simple, mechanical, easy to
   maintain as talks get added.
2. **Content beats** — arrival / momentum / dense-middle / synthesis / closing,
   assigned by actual narrative judgment per talk. More upkeep, reads far more
   intentional. **Leaning this direction** but pending enough real talk content to
   test it — see [[storytelling]].

## Shared shape system (keeps all 5 stages reading as one arc, not five decks)

- **Mountain silhouette**: one fixed SVG ridge shape reused across every stage —
  only its fill color and opacity change.
- **Sun/moon motif**: a single circular "orb" element whose position, size, glow,
  and diffusion evolve stage to stage (high pale moon → low breaking sun → diffused
  fog-glow → soft steady sun → full bright sun).
- **Content block placement**: eyebrow / title / subtitle / badge / quote stay in
  consistent positions across stages — only the mountain/sky background and ink
  color shift.

## Compositional elements shortlisted from earlier exploration rounds

Before landing on the Summit Arc, two structural (non-palette) ideas were
shortlisted from a "sleek/nerdy" exploration round:
- **Diff/Changelog** — content hangs off a code-diff-style line-number gutter.
- **Progress Rail** — a persistent tick-mark rail showing position in the talk
  sequence.

**Open item**: neither has been tested against the Summit Arc's mountain/sky visual
system yet — they may not fit tonally (diff/gutter reads as dev-tool-technical,
which is a different register than the mountain narrative) or Progress Rail's
wayfinding idea may fold directly into the Summit Arc's own stage progression
instead of needing a separate rail element. Revisit once more talk content exists.

## Readability: two-tier slide treatment (locked)

Full atmospheric Summit Arc art (gradients, fog bands, mountain silhouette, orb) is
gorgeous but was fighting body text for the same pixels — most acutely on Stage 3
(Foggy Interception), which was *deliberately* designed as the lowest-contrast stage.
Resolved by splitting every stage into two treatments, confirmed via mockup
(Foggy Interception, splash vs. content):

- **Splash / divider slides** — title, stage transitions, section dividers. Full-bleed
  art exactly as designed per stage (mountain, orb, fog bands, gradient). Text stays
  sparse (eyebrow/title/subtitle/badge), so contrast is easy to guarantee.
- **Content slides** — talk recaps, takeaways, quote lists, anything with real reading
  weight. The stage's gradient/fog/orb collapses to a thin identity band (~6px) in that
  stage's two hues, and body content sits on a near-solid panel color pulled from the
  same stage's palette (not the raw gradient). Stage identity still reads at a glance
  (band color, stage label, accent) — it's just no longer literally fogging the words.

Rejected alternative: a foreground modal/frosted panel over full art. On a content-heavy
slide the panel would end up covering most of the artwork anyway, so it pays the
rendering cost of a scene nobody sees while still looking like a patch.

**Guardrail rule going forward**: content slides never sit directly on a stage's raw
gradient or fog layer — only on a flat panel color derived from that stage's palette.
This is the check to apply as real talk content gets slotted in, so per-slide contrast
doesn't regress as talks are added.

## Typography

Not yet finalized against the Summit Arc — earlier proposal (Space Grotesk /
Inter / JetBrains Mono) was written for the old dev-tool direction and needs
re-evaluation now that the visual register is landscape/narrative rather than
terminal/code. Mockups so far have used serif (Georgia-class) for warmer stages
and cleaner sans for cooler stages as a placeholder — not locked.

## Motion principles

- Reveal.js transition: **slide** as default, **fade** for section-break/mood
  slides — unchanged from original proposal.
- Fragment reveals: `fade-up`, staggered — unchanged.
- Stage transitions (as the deck moves from one arc stage to the next) are a
  natural place for a slower/more deliberate transition treatment — not yet
  designed, flagged for follow-up.
- No motion for motion's sake on data/quotes.

## In-person vs async badge

Still open, per constitution — exact icon/wording TBD. Mockups have used a plain
pill badge ("Live in London" / "Watched Async") styled per-stage; final visual
treatment not locked.

## Change log
- 2026-07-22 — Initial proposal: dark navy base, indigo→violet gradient accent,
  cyan secondary, particle/constellation background.
- 2026-07-24 — User feedback: original direction "looks the same" as generic
  AI-product/vibe-coded aesthetics (purple-gradient-on-dark is one of the most
  common defaults right now). Began structural exploration rounds (terminal,
  journal, diff, editorial, reticle, layered windows, progress rail, callouts,
  ledger, ticker) — shortlisted **Diff/Changelog** and **Progress Rail**.
- 2026-07-24 — Explored literal "summit" interpretations (ascent profile,
  diplomatic table, expedition map, broadcast, above-the-clouds) — ascent/climb
  concept resonated but execution (line chart) didn't; iterated (ridge
  silhouette, vertical route, altimeter gauge) — still not right.
- 2026-07-24 — Pivoted to warm/soft/pastel sunrise-over-mountain palette
  exploration (Desert Dawn, Alpine Blush, Terracotta & Sage, Golden Hour
  Minimal) — direction liked, but user wanted more color range (not全 earthy)
  and a stronger tie to the "summit" feeling specifically for a finale moment.
- 2026-07-24 — **Landed on the Summit Arc**: a 5-stage narrative color
  progression (Night → Morning Rise → Foggy Interception → The Calm → Summit/
  Sunrise) sharing one consistent mountain-and-orb shape system, using purple/
  green/earth-tone families each tied to a specific narrative register rather
  than picked freely. Confirmed as the direction going forward.
- 2026-07-26 — **Locked the two-tier readability split**: full atmospheric art
  reserved for splash/divider slides; content slides use a flattened identity
  band + solid stage-derived panel so body text never sits directly on a
  gradient or fog layer. Rejected a foreground modal approach as visually
  redundant on content-heavy slides. Confirmed via Foggy Interception mockup.

## Open items
- [ ] **Reconsider whether 5 stages is right at all** (raised 2026-07-26, once
      content started landing) — user is conscious of overall slide count/length
      and wants themes/messages consolidated rather than drawn out across too many
      beats. 5 stages may be more granularity than the actual talk content
      supports. Decide once all talk content docs are in and theme clusters are
      visible — see [[storytelling]].
- [ ] Decide stage-boundary trigger: even split vs. content-beat judgment
- [ ] Re-evaluate Diff/Changelog and Progress Rail against the Summit Arc, or
      retire them in favor of the arc's own built-in progression
- [ ] Finalize typography pairing per stage (currently placeholder serif/sans)
- [ ] Design stage-to-stage transition treatment
- [ ] Finalize in-person/async badge visual style
- [ ] Lock exact hex values per stage, and per-stage content-panel colors,
      audited for contrast/accessibility (splash vs. content treatment now
      locked in structure — exact hex still mockup-stage)
