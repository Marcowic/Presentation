---
talk_id: 02-minko-gechev-skill-design-for-llm-agents
title: Skill Design for LLM Agents
speaker: Minko Gechev
mode: async
status: in-deck # raw | drafted | in-deck
---

# Talk details

- **Title:** Skill Design for LLM Agents
- **Speaker:** Minko Gechev
- **Context:** All about agent Skills
- **Mode:** async

# Your summary

<!-- Gist of your understanding — the 2-3 sentence version, in your own words. -->

- Skills and knowing how to make them is a valuable skill to have in the agentic driven software development to boost productivity. There is a deep rabbithole of skill creation and optimisation but even the most basic of skills provide massive value.

# Key points & excerpts

<!-- Bullet the ideas/claims/arguments worth surfacing, roughly in the order they landed.
     Drop a quote/snippet inline under a bullet where it reinforces that point — attribute if
     not the speaker. Flag anything that might be sensitive/embargoed per the constitution's
     no-sensitive-info rule. -->

- Prefer CLIs over MCPs. They are more perfomant. Uses the auth of the user. No initialisation overhead (CLI is just available while MCPs rely on servers being up). Easier debugging and better context preservation.

- 5 best practices for developing agent skills
  - Procedural instructions
    - Don't treat it as a human.
    - Write deterministic steps.
  - Frontmatter optimization
    - Name the skills properly.
    - Avoid generic names that the agent can confuse with other procedures.
    - Utilise negative triggers for better isolation i.e. angular-testing skill has a negative trigger "Do not use for React or Vue"
  - Progressive disclosure
    - Keep skills.md lean, short line size.
    - This way the model can load/reference more resources it may need.
    - Reference the references.md containing all your references.
  - Repetitive task scripting
    - Create scripts and reference them in the skill
  - Skill composition
    - For more advanced use cases, you can nest and/apply conditional routing of skills within skills.

- Eval and test skills for best performance and prevent regression.
- "Skillgrade" app to create tests and evaluate skills in your environment.
- There is a concept of "Hill-climbing" where a skill goes through a process of automated self and improvement based on evaluation scoring.

# Your take

<!-- Optional but valuable: agreement/disagreement, surprise, how it lands against other
     talks, what you're doing differently because of it. This is co-director fuel. -->

- I think it is essential for all engineers in the agentic software development era to know how to create efficient and effective skills.
