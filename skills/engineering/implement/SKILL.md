---
name: implement
description: "Implement a piece of work based on a PRD or set of issues."
disable-model-invocation: true
---

Implement the work described by the user in the PRD or issues.

Use /tdd where possible, at pre-agreed seams.

Before starting, check whether `implementation-notes.md` already exists at the repo root — it's a leftover from an interrupted prior `/implement` session (possibly for a different issue) and must not be appended to. Delete it and start fresh.

Keep a temporary `implementation-notes.md` at the repo root. Whenever reality forces you off the plan — an edge case the PRD didn't anticipate, an assumption that turns out wrong, a missing seam — pick the conservative option, log it under a `## Deviations` heading (what you found, what you did instead, why), and keep going. Do not stop to ask about each deviation; the log is how the user learns about them.

Run typechecking regularly, single test files regularly, and the full test suite once at the end.

Once done, use /code-review to review the work. Give the review the deviations log so the Spec axis can judge each deviation against the PRD, and surface the deviations to the user in your final summary. Delete `implementation-notes.md` before committing — it is a working file, not part of the change.

Commit your work to the current branch.
