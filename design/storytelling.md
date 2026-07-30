---
title: Storytelling Structure
status: living document — will evolve as content comes in
---

# Storytelling Structure

## Format for feeding content (per talk)

For each talk/presentation, you'll provide:
1. **Attendance mode** — in person (London) or async/remote recording
2. **Your summary** — gist of your understanding / key learning
3. **Details** — speaker, talk title, context
4. **Raw excerpts** — quotes/snippets to reinforce ideas on-slide

I'll turn each of these into a mini-sequence of slides (see templates in
[[visual-theme]]) and log it in `design/content-log.md` as we go, so we always have
a running index of what's been covered and what's still pending.

## Narrative arc (draft — to refine once we see how many talks / what themes emerge)

1. **Cold open** — set the scene: AI Coding Summit, London, the trip itself. A hook,
   not a table of contents.
2. **Journey framing** — in-person vs async as a storytelling device (two lenses on
   the same event: the energy of being in the room vs. the flexibility of catching up
   later). Could become a recurring visual motif (the badge system).
3. **Talk sequence** — grouped by theme rather than strictly by attendance order, once
   we see what the talks actually cover (e.g. agentic coding, dev tooling, model
   capabilities, workflow/productivity, industry direction). Group headers act as
   section dividers.
4. **Synthesis** — connective tissue between talks: contradictions, reinforcing ideas,
   surprises. This is where the "co-director" judgment matters most — not just
   recapping each talk, but showing how they talk to each other.
5. **Close** — so what? Your own takeaway / what you're doing differently now / what
   you're watching next in the space.

## Grouping strategy — LOCKED (2026-07-30)

All 8 talks are now drafted. Confirmed thematic clustering over chronological order,
as **4 acts**, each mapped to a Summit Arc stage by content-beat judgment (not an
even talk-count split):

| Stage | Act | Talks | Notes |
|---|---|---|---|
| 1. Night | Cold open | — | The trip itself, no talk content |
| 2. Morning Rise | Act I — The Judgement Thesis | Talk 1 (Kent Dodds) | Sets the frame the rest of the deck plays against |
| 3. Foggy Interception | Act II — The Practical Middle | Talk 5 (Korop, model economics) → Talk 2 (Gechev, skills) → Talks 3+4 merged (Sogl + Waardenburg, guardrails/coherence) | Densest, most technical stretch — matches the stage's "in the weeds" design intent |
| 4. The Calm | Act III — Autonomy at Scale | Talks 6+7 merged (Latsko concept → Leimonis proof-at-scale) | Talk 7 is a case study of Talk 6, not a separate beat |
| 5. Summit | Act IV — Close | Talk 8 (Sumption) + your own takeaway | Bookends back to Talk 1's judgement thesis |

**Act II internal order (confirmed 2026-07-30):** ordered as a pipeline —
*choose your model → equip it with skills → guard its output* — rather than
talk-number order. This also sets up Act III cleanly: loop engineering (6+7) is
what becomes possible once the guardrails from the end of Act II are trusted.

**Merge treatment (confirmed 2026-07-30):** Talks 3+4 and 6+7 each render as one
fully merged sequence — a single flowing argument/case-study, with speaker
attribution inline per point rather than a visible per-talk sub-header. Reason:
these pairs are making the *same point* from two angles (3+4: deterministic
guardrails beat prompted trust; 6+7: loop engineering concept then proof at scale),
so a visible seam would undercut the consolidation.

## Pacing

No slide-count ceiling — user paces live, prune later if needed. Default to *more
granular slides* over cramming (one idea per slide) since reveal.js navigation is cheap
and it keeps live pacing flexible.

## Open items
None currently open — all resolved 2026-07-30 once all 8 talks were drafted (see
"Grouping strategy — LOCKED" above):
- [x] First talk content incoming — all 8 talks now drafted and in-deck.
- [x] Theme clusters — locked as the 4-act structure mapped to the 5 Summit Arc
      stages.
- [x] **Bias toward consolidation, not sprawl** — applied via the fully-merged
      treatment for talks 3+4 and 6+7 (see "Merge treatment" above).
