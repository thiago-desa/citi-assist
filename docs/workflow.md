# Workflow: intake to escalation

## Phase 1 - Intake and graph construction

1. Receive the complaint.
2. Extract and create or update Issue, Location, and Citizen entities.
3. Classify category and initial severity.
4. Retrieve related open or historical Issues.
5. Confirm understanding with the citizen (Router).

## Phase 2 - Investigation (Worker)

1. Research exact location, history of similar issues, and relevant bylaws or regulations (only when confirmed).
2. Identify correct Department(s) and OfficialChannel(s) using the graph plus live search of official pages.
3. Gather public evidence (maps, prior reports, news, official pages).
4. Build an evidence chain: facts to relationships to recommended action.
5. Verify every claim is supported.

Burnaby / BC style channels in the public seed include Customer Service (phone, email, BurnabyConnect app), Engineering Dispatch, Licensing, Legislative Services (Mayor and Council), BC Ombudsperson, RCMP non-emergency (phone/in person constraints), Metro Vancouver, TransLink, BC Hydro outages, Service BC, and Service Canada Office for Client Satisfaction. Always re-verify before use.

## Phase 3 - Formalization

Draft a formal notice tailored to the channel:

- Clear subject
- Precise location and description
- Evidence summary with references
- Specific request / desired outcome
- Citation of relevant bylaw or policy if applicable
- Citizen contact only with consent

Present the draft for approval (or auto-submit only if the citizen pre-authorized that exact path).

## Phase 4 - Submission and tracking

1. Submit via the correct method after approval (email draft, form fields, letter text).
2. Record an Action with reference number or confirmation (never invent one).
3. Create a FollowUp with a due date based on a known SLA or a default of about 5-10 business days.

## Phase 5 - Follow-up and escalation

1. On the due date: check status (ask the citizen, search public portals, or prepare a polite status inquiry).
2. If stalled: escalate along the mapped path (example: department to Customer Service to Council to BC Ombudsperson).
3. Update the graph with every response.
4. Close only when resolved or the citizen confirms closure.

## Phase 6 - Learning

1. On resolution: extract what worked (channel, wording, evidence type).
2. Update Department notes, successful templates, and related Issue links.
3. Optional pattern detection across neighbourhoods for systemic issues.

## Approval gates (non-negotiable)

| Gate | Required before |
|------|-----------------|
| Citizen confirms issue framing | Deep investigation that spends significant time, or any public-facing claim about their situation |
| Citizen approves exact draft + recipient | Send, submit, or mail |
| Citizen approves escalation draft | Moving to the next body in the path |
| Citizen confirms closure | Marking Resolution complete |

## Routine cadence

Weekday morning watchdog (~09:00 America/Vancouver in the live bot): surface due FollowUps and stalled cases; stay quiet if the queue is clean.
