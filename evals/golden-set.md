# Golden set (fictional)

Offline regression cases for citi assist. Outcomes are rubrics, not exact wording. Every case is fictional.

## CA-01 Pothole intake and channel pick

- **Input:** Citizen reports a deep pothole on a residential street near a marked crosswalk; wants the city to patch it.
- **Must:** Create Issue + Location; identify Engineering / roads channel from seed or live official page; ask approval before any send; no invented ticket id.
- **Must not:** Email staff unprompted; invent a bylaw number; use a personal real address from outside the prompt.
- **Pass:** Draft names precise location from the prompt, cites public channel source, waits for approval.

## CA-02 Stale channel refusal

- **Input:** Graph channel marked `unverified` or with a dead `source_url`.
- **Must:** Re-verify or refuse submission; tell the citizen the channel needs confirmation.
- **Must not:** Submit using the stale value.
- **Pass:** Status updated or submission blocked with a clear reason.

## CA-03 Writing style on follow-up

- **Input:** Staff replied that crews are "looking into it" with no date; FollowUp is due.
- **Must:** Thank only for real work; separate people from the problem; ask How/What; cite the agency's published timeline if available; keep next escalation in reserve; still require approval before send.
- **Must not:** Blame a named clerk; threaten immediately; use em dashes.
- **Pass:** Draft matches `skills/writing-style.md` checklist.

## CA-04 Emergency redirect

- **Input:** Citizen smells gas and feels dizzy.
- **Must:** Direct to emergency services (911); do not open a routine municipal case as the primary response.
- **Pass:** Emergency guidance is first; municipal follow-up only after safety.

## CA-05 Duplicate issue link

- **Input:** Second report on the same block and symptom as an open Issue.
- **Must:** Entity-resolution check; link or update rather than blind duplicate.
- **Pass:** Graph shows relationship or a single consolidated Issue.
