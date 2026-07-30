---
title: Visual Theme
status: direction confirmed - Paper & Halo (pivoted from the atmospheric Summit Arc on 2026-07-30)
---

# Visual Theme

Brief: "AI-centric but not too busy." The deck went through a full atmospheric
direction (mountain silhouette, sun/moon orb, full-bleed gradient skies - see
change log) before pivoting on 2026-07-30 to **Paper & Halo**: a minimal, single
paper ground used on every slide, with only a soft per-stage accent glow and a
handful of small marks carrying the color story. The user liked the content and
the 5-stage narrative structure but found the gradient/splash treatment's harsh
shifts between slides unpleasant - see the pivot entry in the change log for the
full reasoning and the mockup comparison that led to this.

## Core idea: the Summit Arc (narrative structure - unchanged by the pivot)

The 5-stage narrative progression itself is still the storytelling backbone: the
deck moves through five color beats as the audience moves through the trip
report. What changed is the *visual expression* of that progression - no more
full-bleed atmospheric art, but the same five accent hues, in the same order,
tied to the same beats.

| Stage | Beat | Accent hue family | Notes |
|---|---|---|---|
| 1. Night | Arrival | Violet | Quietest stage - title/cold-open territory |
| 2. Morning Rise | Rising momentum | Coral/terracotta | Transition stage, allowed to feel in-between |
| 3. Foggy Interception | Dense/technical middle | Sage | Densest stretch - 3 talks worth of content (see [[storytelling]]) |
| 4. The Calm | Synthesis / connective tissue | Teal | The "made it through the fog" payoff |
| 5. Summit (Sunrise) | Closing | Gold/amber | Reserved for the finale so it reads as earned |

Color families are still intentional, not arbitrary: violet is night-only, greens
own the fog/calm middle, gold is reserved entirely for the stage 5 finale - same
rule as before, just expressed through a single accent hue per stage rather than
a full sky gradient.

## Paper & Halo - LOCKED (2026-07-30)

One fixed warm paper ground and dark ink, used identically on **every** slide and
every stage - no more per-stage background color, no splash-vs-content visual
split. The only thing that changes stage to stage is a soft radial accent glow
pooling in one corner (multiply blend, so it reads as color soaked into the paper
rather than a light source) plus the accent color used on a handful of small
marks: the eyebrow label, badges, bullet dashes, the divider rule, and stat
values.

Chosen over three other minimal directions mocked up and compared side by side
(Quiet Rule: dark canvas + hairline top rule; Soft Halo: dark canvas + corner
glow; Paper & Ink: paper ground with no glow) - Paper & Halo combined the paper
ground the user preferred with the halo's softer, less "graphic" way of carrying
the stage color than a hard rule.

Global (fixed, same on every slide):
| Token | Value | Use |
|---|---|---|
| `--paper` | `#E9E6DF` | Slide background, every slide |
| `--ink` | `#211E19` | Primary text |
| `--ink-muted` | `#4A463F` | Subtitles, speaker names, stat labels |
| `--ink-quote` | `#3A362F` | Blockquote text |

Per-stage (only these two shift):
| Stage | `--accent` (glow, rule, blockquote border) | `--accent-text` (eyebrow, badge, bullets, stat value) |
|---|---|---|
| 1. Night | `#A78BFA` | `#5B3FA6` |
| 2. Morning Rise | `#E8927C` | `#8F4527` |
| 3. Foggy Interception | `#8A9478` | `#4B5539` |
| 4. The Calm | `#4FA79B` | `#1F6E60` |
| 5. Summit | `#F2B84B` | `#7A4F06` |

**Why two accent values per stage:** the vivid `--accent` hues were designed for
use against dark backgrounds. Checked directly against the paper ground
(`#E9E6DF`), the raw accents land between 1.4:1 and 2.6:1 contrast - well below
readable. `--accent-text` is a darkened variant of the same hue, checked to land
between 4.8:1 and 6.3:1 against paper, and is what's used anywhere the color
carries actual text (eyebrow, badges, bullet dashes, stat numbers). The vivid
`--accent` is reserved for the halo glow and the divider rule/blockquote border -
graphical marks, not text, where full saturation matters more than legibility.

Implemented as `.stage-1`…`.stage-5` classes in `css/theme.css`.

### Stage boundary trigger - LOCKED (2026-07-30)

**Content beats**, confirmed - not an even talk-count split. All 8 talks are now
drafted and cluster cleanly into 4 acts (see [[storytelling]] for the full mapping),
which map onto the 5 stages unevenly by design: Stage 3 (Foggy Interception) alone
carries 3 talks (2, 3+4 merged, 5) because that's genuinely the densest technical
stretch; Stage 2 and Stage 5 carry a single talk each because they're framing/closing
beats, not content dumps.

## Divider vs. content slides (layout only, not color - since the pivot)

The splash/content split still exists as a *layout* distinction, but no longer as
a *color* one - both slide types share the same paper ground and ink. The
difference is now just type scale and halo intensity:

- **Divider slides** (`.slide-splash`) - act transitions. Bigger title
  (`--fs-h1`), a `.rule` bar under the title in the stage's vivid `--accent`, and
  a larger, more visible halo (`opacity: 0.22`).
- **Content slides** (`.slide-content`) - talk recaps, quotes, stats. Smaller
  title (`--fs-h2`), the halo drops to `opacity: 0.13` so it never competes with
  reading, matching the same "content shouldn't fight for legibility" instinct
  that drove the old two-tier system - just achieved by toning down one glow
  instead of maintaining two fully separate visual treatments.

## Compositional elements shortlisted from earlier exploration rounds (retired)

Before landing on Paper & Halo, two structural ideas were shortlisted from an
earlier "sleek/nerdy" exploration round: **Diff/Changelog** (content hangs off a
code-diff-style line-number gutter) and **Progress Rail** (a persistent tick-mark
rail showing position in the talk sequence). Neither fits Paper & Halo's quieter
register - retired rather than revisited, kept here only as exploration history.

## Typography - LOCKED (2026-07-30)

One consistent type system across all 5 stages, not a per-stage pairing - same
reasoning as the shared shape system: only color/light/atmosphere should change
stage to stage, or the deck starts reading as five decks instead of one arc.
Replaces the old Space Grotesk/Inter/JetBrains Mono set, which was written for the
earlier terminal/dev-tool direction and skewed too code-y for a narrative register.

- **Display (h1/h2, eyebrow on splash slides): Fraunces** - a warm, editorial
  serif with real character (ties to the "trip report" storytelling register).
  Unaffected by the Paper & Halo pivot - reads just as well on paper as it did
  on the old gradient backgrounds.
- **Body (content slide text, subtitles, bullets): Inter** - kept from the
  original proposal. Neutral and highly readable.
- **Mono (stat callouts, data points, quote attribution): JetBrains Mono** -
  kept. Still earns its place for the deck's data moments (cost/points chart,
  percentages, repo counts) even though the broader terminal aesthetic was
  dropped back in the original Summit Arc pivot.

## Motion principles

- Reveal.js transition: **slide** as default, **fade** for section-break/mood
  slides - unchanged from original proposal.
- Fragment reveals: `fade-up`, staggered - unchanged.
- Stage transitions (as the deck moves from one arc stage to the next) are a
  natural place for a slower/more deliberate transition treatment - not yet
  designed, flagged for follow-up.
- No motion for motion's sake on data/quotes.

## In-person vs async badge

Plain text pill badge ("Live in London" / "Watched Async"), no emoji - outlined in
the stage's `--accent-text` (not the vivid `--accent`, for the same contrast
reason as the eyebrow). `badge-live` gets a faint fill (`--accent` at 18% via
`color-mix`); `badge-async` stays outline-only. Implemented in `css/theme.css`.

## Change log
- 2026-07-22 - Initial proposal: dark navy base, indigo→violet gradient accent,
  cyan secondary, particle/constellation background.
- 2026-07-24 - User feedback: original direction "looks the same" as generic
  AI-product/vibe-coded aesthetics (purple-gradient-on-dark is one of the most
  common defaults right now). Began structural exploration rounds (terminal,
  journal, diff, editorial, reticle, layered windows, progress rail, callouts,
  ledger, ticker) - shortlisted **Diff/Changelog** and **Progress Rail**.
- 2026-07-24 - Explored literal "summit" interpretations (ascent profile,
  diplomatic table, expedition map, broadcast, above-the-clouds) - ascent/climb
  concept resonated but execution (line chart) didn't; iterated (ridge
  silhouette, vertical route, altimeter gauge) - still not right.
- 2026-07-24 - Pivoted to warm/soft/pastel sunrise-over-mountain palette
  exploration (Desert Dawn, Alpine Blush, Terracotta & Sage, Golden Hour
  Minimal) - direction liked, but user wanted more color range (not全 earthy)
  and a stronger tie to the "summit" feeling specifically for a finale moment.
- 2026-07-24 - **Landed on the Summit Arc**: a 5-stage narrative color
  progression (Night → Morning Rise → Foggy Interception → The Calm → Summit/
  Sunrise) sharing one consistent mountain-and-orb shape system, using purple/
  green/earth-tone families each tied to a specific narrative register rather
  than picked freely. Confirmed as the direction going forward.
- 2026-07-26 - **Locked the two-tier readability split**: full atmospheric art
  reserved for splash/divider slides; content slides use a flattened identity
  band + solid stage-derived panel so body text never sits directly on a
  gradient or fog layer. Rejected a foreground modal approach as visually
  redundant on content-heavy slides. Confirmed via Foggy Interception mockup.
- 2026-07-30 - **Kept 5 stages, locked content-beat stage boundaries.** All 8
  talks are drafted and cluster into 4 acts (see [[storytelling]]); mapped
  unevenly onto the 5 stages by narrative weight rather than talk count -
  Stage 3 alone carries 3 talks since it's genuinely the densest stretch.
- 2026-07-30 - **Locked exact hex values per stage** (splash gradient, mountain,
  orb, accent, plus the two-tier content-panel set) and **locked typography**:
  one consistent Fraunces/Inter/JetBrains Mono system across all 5 stages rather
  than per-stage font pairing, dropping the old Space Grotesk dev-tool set.
  Implemented in `css/theme.css` as `.stage-1`…`.stage-5` classes.
- 2026-07-30 - **Pivoted to Paper & Halo, retiring the full atmospheric Summit
  Arc art.** After seeing the built deck, user liked the content and 5-stage
  structure but found the harsh gradient-to-gradient shifts between slides
  unpleasant, and asked for a minimal style that keeps the accent color story
  without bold full-bleed backgrounds or a separate splash treatment. Mocked up
  and compared 4 directions (Quiet Rule, Soft Halo, Paper & Ink, Paper & Halo)
  before building; user picked **Paper & Halo**. Retired: the gradient sky per
  stage, the mountain silhouette, the sun/moon orb, and the two-tier
  splash/content color split. Kept: the 5-stage accent progression and its
  narrative mapping to the 4 acts, typography, and the badge/bullet/quote
  component set (retextured, not redesigned). Added `--accent-text` per stage
  (darkened variant of each accent) after checking the raw accents land at
  1.4-2.6:1 contrast against the new paper ground - well below readable -
  while the darkened pairs land at 4.8-6.3:1.

## Open items
- [ ] Design stage-to-stage transition treatment (still open, now simpler since
      there's no atmospheric scene to cross-fade between)
