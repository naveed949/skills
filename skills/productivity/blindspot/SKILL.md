---
name: blindspot
description: Surface the user's unknown unknowns before work begins. Use when the user says "blindspot pass" or "unknown unknowns", is entering unfamiliar territory (a part of the codebase or a domain they don't know), or admits they don't know what questions to ask.
---

The user is about to work in territory they don't know well. Your job is to find their **unknown unknowns** — the questions they don't know to ask — and hand them back as questions they now can ask. You are orienting, not implementing: do not start the work.

1. **Establish the starting point.** From the conversation so far, work out what they're trying to do, what they already know, and where their experience runs out. If any of that is unclear, ask — one question at a time.

2. **Sweep the territory.** Explore whatever the work will actually touch: the relevant modules, their history (commits, PRs, ADRs, `CONTEXT.md`), the conventions and prior art around them. For a non-code domain, research the domain itself. Look specifically for what the user's framing never mentions — constraints, existing solutions, failure modes others hit, and signs the problem should be solved a different way altogether.

3. **Report the blindspots.** A short list, ordered by how much each would change the user's plan. For each: what it is, why it matters to *this* task, and the question the user should now be asking. Explain them for someone new to this territory — the report is teaching material, not a task list. Also say what "good" looks like here if the user has no way to judge that yet.

4. **Hand off, don't proceed.** Close by pointing at the next step — usually a `/grilling` session now that the user knows what to ask, and answer any follow-up questions they have about the territory first.
