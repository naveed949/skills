---
name: implement
description: "Implement a piece of work based on a spec or set of tickets."
disable-model-invocation: true
---

Implement the work described by the user in the spec or tickets.

Use /tdd where possible, at pre-agreed seams.

Before starting, check whether `.claude/implementation-notes.md` already exists — it's a leftover deviations log from an interrupted prior `/implement` session (possibly for a different issue), and it records deviations that were never disclosed. Do not silently discard it and do not append to it: surface its contents to the user first, then start a fresh log.

Keep a temporary deviations log at `.claude/implementation-notes.md` (namespaced under `.claude/` so it can never clobber a file the repo tracks). Whenever reality forces you off the plan — an edge case the PRD didn't anticipate, an assumption that turns out wrong, a missing seam — pick the conservative option, log it under a `## Deviations` heading (what you found, what you did instead, why), and keep going. Do not stop to ask about each deviation; the log is how the user learns about them.

Run typechecking regularly, single test files regularly, and the full test suite once at the end.

Once the work is built and the suite is green, commit it to the current branch — record the `## Deviations` summary in the commit message body so the record survives into the review and into anything that later reads the history (e.g. `/quiz-me`). Keep `.claude/implementation-notes.md` itself out of the commit; it is a working file, not part of the change.

Then use /code-review to review the work against the point you branched from. Because the work is now committed, the review has a non-empty diff to judge; hand it the path to `.claude/implementation-notes.md` so the Spec axis can judge each deviation against the PRD. Surface the deviations to the user in your final summary, then delete `.claude/implementation-notes.md` — the record now lives in the commit message, the review, and the summary.
