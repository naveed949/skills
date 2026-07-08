Quickstart:

```bash
npx skills add mattpocock/skills --skill=blindspot
```

```bash
npx skills update blindspot
```

[Source](https://github.com/mattpocock/skills/tree/main/skills/productivity/blindspot)

## What it does

`blindspot` sweeps the territory you're about to work in — an unfamiliar part of the codebase, a domain you've never touched — and reports back your **unknown unknowns**: the constraints, prior art, failure modes, and better approaches your framing never mentioned, each turned into a question you now know to ask.

It orients you and then stops — it never starts the work itself. The deliverable is a sharpened set of questions and a sense of what "good" looks like in this territory, not code.

## When to reach for it

Type `/blindspot`, say "blindspot pass" or "unknown unknowns", or the agent reaches for it automatically when you admit you're on unfamiliar ground.

Reach for it *before* a grilling session, whenever you can't yet answer an interview's questions — a new auth module, a domain like video color grading, any place where you don't know what you don't know. If you already know the territory and just need the decisions forced into the open, skip straight to [grill-me](https://aihero.dev/skills-grill-me).

## Unknown unknowns

An interview can only surface your **known unknowns** — the questions you know you haven't answered. Unfamiliar territory hides a second class: questions you don't know exist. `blindspot` hunts those directly. It establishes where your experience runs out, sweeps what the work will actually touch (modules, history, ADRs, conventions — or the domain itself for non-code work), and reports the blindspots ordered by how much each would change your plan. The report teaches; it explains each finding for someone new to the territory rather than assuming you can already judge it.

## It's working if

- It asks where your experience runs out before it starts sweeping.
- The findings are things your original framing never mentioned — not confirmations of what you already said.
- Each finding ends in a question you could now put to a grilling session.
- It stops at the report instead of starting the implementation.

## Where it fits

`blindspot` is an on-ramp to the main build chain: it runs *before* the interview, so the interview has better raw material. Its key neighbour is [grilling](https://aihero.dev/skills-grilling) (via [grill-me](https://aihero.dev/skills-grill-me) or [grill-with-docs](https://aihero.dev/skills-grill-with-docs)), which turns the questions `blindspot` surfaced into settled decisions; [research](https://aihero.dev/skills-research) is the deeper standalone dig when one surfaced question deserves a cited report of its own. When you're unsure which flow fits, [ask-matt](https://aihero.dev/skills-ask-matt) routes you.
