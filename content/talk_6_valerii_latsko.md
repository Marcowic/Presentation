---
talk_id: 06-valerii-latsko-loop-engineering
title: From Prompt Engineering to Loop Engineering
speaker: Valerii Latsko
mode: in-person
status: in-deck # raw | drafted | in-deck
---

# Talk details

- **Title:** From Prompt Engineering to Loop Engineering
- **Speaker:** Valerii Latsko
- **Context:** (track/session, time, anything about the setting)
- **Mode:** in-person

# Your summary

<!-- Gist of your understanding — the 2-3 sentence version, in your own words. -->

- Loop engineering is another workflow utilising agents to do repetitive tasks or allow the agent to work "independently" without supervision. This is a workflow can be extremely beneficial if leveraged correctly.

# Key points & excerpts

<!-- Bullet the ideas/claims/arguments worth surfacing, roughly in the order they landed.
     Drop a quote/snippet inline under a bullet where it reinforces that point — attribute if
     not the speaker. Flag anything that might be sensitive/embargoed per the constitution's
     no-sensitive-info rule. -->

- Loop engineering, the new AI workflow.
- Instead of prompting claude (any agent) you'd have loops running which prompt the agent and figure out what to do. Prompt -> inspect -> re-prompt -> repeat.
- Agents are now fast but the steering was manual. The human became the bottleneck. Loop engineering automate the repetitive steering while the human keeps the goals, boundaries and gates.
- Some use cases of loop engineering: repo maintenance and triage, migrations and ports, small product features, full apps from a spec, etc.
- An example of loop engineering which ran for 3 months straight is the "cursed" programming language. https://github.com/ghuntley/cursed
- The same prompt.md was given to the agent every time. In the prompt.md, it contains rules and references to other resources that are iteratively updated. The prompt never says what to build, the specs define the target and the agent.md defines the operating knowledge.
- More ambitious usage, migrating a project to a different language. Six projects overnight: React to Vue, Python to TypeScript, TypeScript to Python, plus specs-to-code experiments from docs. About 1,100 commits, just under $800.

# Your take

<!-- Optional but valuable: agreement/disagreement, surprise, how it lands against other
     talks, what you're doing differently because of it. This is co-director fuel. -->

- Loop engineering is another workflow that can be used for agentic driven development. I think it is a workflow that looks difficult to get right since the aim is to eliminate human supervision to a massive degree. Essentially putting trust on the prompts and other resources to be consistently understood by the agent to produce a good result. I think it is an expensive workflow.
