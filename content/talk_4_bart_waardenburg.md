---
talk_id: 04-bart-waardenburg-fast-code-generation-safe-system-change
title: Fast Code Generation Is Easy. Safe System-level Change Is Not.
speaker: Bart Waardenburg
mode: async
status: in-deck # raw | drafted | in-deck
---

# Talk details

- **Title:** Fast Code Generation Is Easy. Safe System-level Change Is Not.
- **Speaker:** Bart Waardenburg
- **Context:** (track/session, time, anything about the setting)
- **Mode:** async

# Your summary

<!-- Gist of your understanding — the 2-3 sentence version, in your own words. -->

- A different avenue of concern when it comes to AI generated code and some good practices to keeping the system/codebase coherent and consistent.

# Key points & excerpts

<!-- Bullet the ideas/claims/arguments worth surfacing, roughly in the order they landed.
     Drop a quote/snippet inline under a bullet where it reinforces that point — attribute if
     not the speaker. Flag anything that might be sensitive/embargoed per the constitution's
     no-sensitive-info rule. -->

- Today the issue is not the speed of writing code, now the issue is trying to keep the codebase coherent.
- The agentic flow: the developer describes intent, the agent changes the code, the local toolchain catches quality drift, and the human reviews.
- When the user writes the prompt and provides the intent, the quality system should catch problems during the agent lopp automatically. Deterministic tooling works best as agent will take the shortest path to working behaviour.
- Where should you put these quality checks or deterministic guards? Not the rules file (i.e. CLAUDE.md) as they only provide a blanket context which the agent can and will deviate from if things get exciting. The rules file is delivered as a user message and there is no guarantee for strict compliance.
- Prefer agent hooks for processes that need to run at specific lifecycle points.
- Then the talk proceeds to a promo on Bart's product, Fallow. A quality gate/auditor for agent generated code to guard overall project coherence and consistency.

# Your take

<!-- Optional but valuable: agreement/disagreement, surprise, how it lands against other
     talks, what you're doing differently because of it. This is co-director fuel. -->

- Use deterministic processes/gates which agents can not bypass to maintain codebase coherence and consistency.
