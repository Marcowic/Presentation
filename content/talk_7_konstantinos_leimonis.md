---
talk_id: 07-konstantinos-leimonis-ai-agent-fleet-migrations
title: "From One Repo to Hundreds: Building an AI Agent Fleet for Large-Scale Code Migrations"
speaker: Konstantinos Leimonis
mode: in-person # in-person | async
status: in-deck # raw | drafted | in-deck
---

# Talk details

- **Title:** From One Repo to Hundreds: Building an AI Agent Fleet for Large-Scale Code Migrations
- **Speaker:** Konstantinos Leimonis
- **Context:** (track/session, time, anything about the setting)
- **Mode:** in-person

# Your summary

<!-- Gist of your understanding — the 2-3 sentence version, in your own words. -->

- A practical flavour of loop engineering with stateless agents pulling and pushing tasks from an orchestration layer. Extremely interesting use of agents.

# Key points & excerpts

<!-- Bullet the ideas/claims/arguments worth surfacing, roughly in the order they landed.
     Drop a quote/snippet inline under a bullet where it reinforces that point — attribute if
     not the speaker. Flag anything that might be sensitive/embargoed per the constitution's
     no-sensitive-info rule. -->

- Throwing an army of LLMs to migrate repos to a new node version.
- 527 repos (micro frontends), 87% migrated without any human in the loop.
- Why not do it manually? Scale.
- Started with 1 repo 1 agent and a baseline of 5 steps to migration and refining them to produce good results.
- Two paths to progress. Deterministic (scripts) and non-deterministic (requires judgement).
- The most valuable asset/resource for autonomous migration are the tests. The test are the eyesight or signal of success which enforces the agents to the correct path.
- The fleet of agents and their approach explained. The agents are all stateless. Agents read from a board, writes the result on the board, and then they stop. They have to adhere to a contract which is deterministic to keep track of their status/completeness and next steps.
- Utilises loop engineering to resolve PR conflicts and failures (pipeline, linting, etc).

# Your take

<!-- Optional but valuable: agreement/disagreement, surprise, how it lands against other
     talks, what you're doing differently because of it. This is co-director fuel. -->

- Verification is more important than autonomy. Loop engineering take on an extremely tedious task.
