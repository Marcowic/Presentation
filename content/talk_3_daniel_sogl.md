---
talk_id: 03-daniel-sogl-ai-reviews-ai
title: AI Reviews AI – Closing the Loop in Agentic Development
speaker: Daniel Sogl
mode: in-person
status: drafted # raw | drafted | in-deck
---

# Talk details

- **Title:** AI Reviews AI – Closing the Loop in Agentic Development
- **Speaker:** Daniel Sogl
- **Context:** (track/session, time, anything about the setting)
- **Mode:** in-person

# Your summary

<!-- Gist of your understanding — the 2-3 sentence version, in your own words. -->

- Agentic code reviews and good practices when generating code. Useful wisdom on getting better more reliable performance from agents through deterministic processes and understanding agent biases.

# Key points & excerpts

<!-- Bullet the ideas/claims/arguments worth surfacing, roughly in the order they landed.
     Drop a quote/snippet inline under a bullet where it reinforces that point — attribute if
     not the speaker. Flag anything that might be sensitive/embargoed per the constitution's
     no-sensitive-info rule. -->

- More and more code is written by AI. According to sonar 42% of new code is written by AI, but realistically is is over 90%.
- We are shipping more code faster. Now, review is the bottleneck.
- Some stats from Faros AI (2026) 22,000 developers: +441% time in PR review, +210% tasks involving code, +31% more PRs merged unreviewed, +243% incidents per PR.
- Plausible code. If the pipeline is green, linter is green, code looks right, then why should we review the code.
- Layers of defence against code churn: Deterministic defense and probabilistic.
- Hooks, deterministic. Checks that agents can not skip. i.e. claude hook to do something when using a tool
- Tests are the spec. With TDD/BDD you own the spec and the agent owns the implementation. People still fall into the trap of enforcing bugs by telling the AI to write tests based on the code.
- People are now more like product developers than software developers.
- Agent in the loop. Agents can be used to review but often adds more noise.
- Who reviews the reviewer. There were studies about the concept of rubber ducking. Same model reviewing the same model outputs display a level of bias. The bias is at a family level. GPT favours GPT, Claude favours Claude. Always set a different model to review the output.
- There were also studies experimenting what if you use two different cheaper models to review each other. The output quality almost matches the more expensive model. (Economical token spending)

# Your take

<!-- Optional but valuable: agreement/disagreement, surprise, how it lands against other
     talks, what you're doing differently because of it. This is co-director fuel. -->

- Golden insight on family level bias and leveraging AI the best for reviewing code and aleviating code review bottleneck.
