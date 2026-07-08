---
"mattpocock-skills": minor
---

Adopt the "finding your unknowns" techniques from Thariq's Fable field guide across the skill set:

- **New `blindspot` skill** (productivity, model-invoked) — sweeps unfamiliar territory to surface your **unknown unknowns** before work begins, turning them into questions a grilling session can then settle. Routed in `ask-matt` as an on-ramp ahead of the main flow.
- **New `quiz-me` skill** (productivity, user-invoked) — briefs you on a change and quizzes you one question at a time until you can pass; the **comprehension gate** before you merge. Routed in `ask-matt` as the closing branch of the main flow.
- **`implement`** now keeps a temporary `.claude/implementation-notes.md` (namespaced so it can't clobber a tracked file) and logs every deviation from the plan under a `## Deviations` heading — conservative option, keep going. It commits the work with the deviations recorded in the commit message, then feeds the log into `code-review`'s Spec pass — which now judges deviations even when no spec is found — and surfaces them in the final summary. A leftover log from an interrupted session is surfaced to you, never silently discarded, and the commit-message record is how deviations survive into a later `/quiz-me`.
- **`to-prd`** now orders Implementation Decisions volatile-first: data models, then interfaces and contracts, then user-facing choices, with mechanical refactoring last.
- **`grilling`** now asks early for a **reference** — existing code, a vendored library, or a product that already does it the way you want — and reads it to settle whole branches of the design tree at once.

Also brings the indexes back in sync with the repo's own rules: `implement` and `resolving-merge-conflicts` are now listed in the top-level and Engineering READMEs (and `resolving-merge-conflicts` in `plugin.json` and `ask-matt`'s Standalone section), and docs pages for the changed skills are re-synced.
