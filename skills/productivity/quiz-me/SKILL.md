---
name: quiz-me
description: Get quizzed on a change until you understand it well enough to merge it.
disable-model-invocation: true
---

Quiz me on a change until I understand it well enough to own it. A diff alone gives me a light understanding — much of the behaviour lives in existing code paths the diff merely touches — so your job is to close that gap and then verify it's closed.

1. **Gather the change.** Read the diff the user points you at (or the diff of the current branch against its base), plus the surrounding code paths it depends on. Understand behaviour, not just text.

2. **Brief me first.** Write a short report: the context, the intuition behind the approach, what was done, and what now behaves differently. Include how the change interacts with existing code paths — that's the part the diff doesn't show.

3. **Quiz me.** One question at a time, waiting for my answer before the next. Ask about behaviour and consequences, not trivia: what happens when X, why was Y chosen over the alternative, what would break if Z changed. Prefer questions whose wrong answers would matter in production.

4. **Grade honestly.** When I get one wrong, explain the correct answer, then return to the same ground later with a fresh variant. Do not soften a wrong answer into a pass.

5. **Gate the merge.** Keep going until I've answered correctly across the board, then tell me plainly that I've passed. If I haven't passed, say what I should re-read. The change is not ready to merge until I pass — that's the point.
