Quickstart:

```bash
npx skills add mattpocock/skills --skill=implement
```

```bash
npx skills update implement
```

[Source](https://github.com/mattpocock/skills/tree/main/skills/engineering/implement)

## What it does

`implement` builds the work described in a PRD or a set of issues — driving it through test-driven development, typechecking, and the full test suite, then committing to the current branch and handing off to a review pass.

It does **not** decide what to build. The spec is already settled and the seams are already agreed; `implement` executes that plan rather than reopening it. It is the hands, not the head — the thinking happened upstream.

## When to reach for it

You invoke this by typing `/implement` — the agent won't reach for it on its own.

Reach for it once the work is written down as a PRD or split into issues and you're ready to turn that into code. If the spec doesn't exist yet, write it first — for that, use [to-prd](https://aihero.dev/skills-to-prd), or [to-issues](https://aihero.dev/skills-to-issues) to break a PRD into tickets. If you just want to build something test-first without a full spec, drop to [tdd](https://aihero.dev/skills-tdd) directly.

## Pre-agreed seams

The idea `implement` runs on is the **seam** — the stable interface a feature is tested at, chosen before any code is written. It doesn't invent seams mid-build; it uses the ones already picked (during [to-prd](https://aihero.dev/skills-to-prd)) and writes tests against them via [tdd](https://aihero.dev/skills-tdd). Working at pre-agreed seams is what keeps the implementation honest: the tests target something durable, so the code underneath can move without the tests moving.

Around that core it keeps the loop tight — typecheck often, run single test files as it goes, run the whole suite once at the end — then commits to the current branch and closes out with a review pass over what it just committed.

## The deviations log

No plan survives contact with the codebase, so `implement` keeps a temporary `.claude/implementation-notes.md` while it works — namespaced under `.claude/` so it can never clobber a file the repo tracks. When an edge case or a wrong assumption forces it off the plan, it picks the conservative option, logs the **deviation** — what it found, what it did instead, why — and keeps going instead of stopping to ask. It then commits the work with the deviations recorded in the commit message, and hands the log to the [code-review](https://aihero.dev/skills-code-review) Spec pass, where each deviation is judged against the PRD (and judged even when no spec is found); the deviations are also surfaced to you in the final summary. The log file itself is deleted afterwards; the record of what changed lives in the commit message, the review, and the summary — which is also how it survives into a later [quiz-me](https://aihero.dev/skills-quiz-me). Because [to-issues](https://aihero.dev/skills-to-issues) work runs one `/implement` session per issue on the same branch, each session first checks for a leftover log from an interrupted prior run and surfaces it to you rather than appending to it or discarding it unread, so deviations never mix across issues and never ship undisclosed.

## Where it fits

`implement` is the build step near the end of the main chain, just before the review:

```txt
grill-with-docs → to-prd → to-issues → implement → code-review
```

Reach for it after the work has been specced and sequenced, not before. Its key neighbours are [to-issues](https://aihero.dev/skills-to-issues), which produces the independently-grabbable tickets it works through, and [tdd](https://aihero.dev/skills-tdd), which it drives internally to write the tests at each seam before committing and running its own [code-review](https://aihero.dev/skills-code-review) pass. When you're unsure which skill or flow fits, [ask-matt](https://aihero.dev/skills-ask-matt) routes you.
