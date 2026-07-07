Quickstart:

```bash
npx skills add mattpocock/skills --skill=quiz-me
```

```bash
npx skills update quiz-me
```

[Source](https://github.com/mattpocock/skills/tree/main/skills/productivity/quiz-me)

## What it does

`quiz-me` briefs you on a change — the context, the intuition, what now behaves differently — and then quizzes you on it, one question at a time, until you can answer correctly across the board.

It gates the merge on *your* understanding, not the code's correctness: the review checks the code, but nothing else checks that the person merging actually understands what shipped. A wrong answer is never softened into a pass; it gets explained, and the same ground comes back later as a fresh variant.

## When to reach for it

You invoke this by typing `/quiz-me` — the agent won't reach for it on its own.

Reach for it after a long agent session, before you merge — when the diff is bigger than what you watched happen, and much of the behaviour lives in existing code paths the diff merely touches. If what you want checked is the *code* rather than your understanding of it, use [code-review](https://aihero.dev/skills-code-review) instead; the two are complements, not alternatives.

## The comprehension gate

The leading idea is the **comprehension gate**: you only merge after you pass. The questions target behaviour and consequences — what happens when X, why Y over the alternative, what breaks if Z changes — because those are the questions production will eventually ask you. Passing means the change now lives in your head, not just in the branch; you can debug it, defend it in review, and build on it without re-reading the diff.

## It's working if

- You get a briefing before the first question, including how the change interacts with code the diff doesn't show.
- Questions arrive one at a time, about consequences rather than trivia.
- A wrong answer gets corrected *and* revisited later — not waved through.
- The session ends with an explicit pass (or a list of what to re-read), not a shrug.

## Where it fits

`quiz-me` is the closing step of the main build chain — after [implement](https://aihero.dev/skills-implement) and [code-review](https://aihero.dev/skills-code-review) have produced and checked the change, it checks *you* before the merge. Its other neighbour is [teach](https://aihero.dev/skills-teach), which builds understanding over multiple sessions where `quiz-me` verifies it in one. When you're unsure which flow fits, [ask-matt](https://aihero.dev/skills-ask-matt) routes you.
