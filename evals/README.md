# Evals

Golden-set cases in `golden-set.md` encode the behaviors this bot must keep: grounded channels, approval gates, writing style, emergency redirect, and entity resolution.

How to use:

1. For each case, run the agent (or a dry-room roleplay) with the Input.
2. Score with the Must / Must not rubric (pass/fail). Prefer deterministic checks where possible.
3. Add every new production failure as a fictionalized case.
4. Re-run the set after skill or instruction changes.

These are regression sensors, not a live municipal integration test.
