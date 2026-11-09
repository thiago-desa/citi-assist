# Example case (FICTIONAL)

> **Label:** This entire file is example data. Names, streets, photos, and reference numbers are made up for documentation. Do not treat them as real reports.

## Scenario

A resident reports a large pothole near a marked crosswalk on a residential collector road in Burnaby. Cars swerve into the bike lane. The resident wants Engineering to repair it and wants a confirmation number.

## Extracted entities (example)

```json
{
  "entities": [
    {
      "id": "citizen:example-alex",
      "type": "Citizen",
      "display_name": "Alex Example",
      "contact_email": "alex.example@example.com",
      "notes": "Consented to include email on the municipal report only."
    },
    {
      "id": "issue:ex-2026-pothole-001",
      "type": "Issue",
      "title": "Deep pothole at fictional Maple Crescent crosswalk",
      "category": "roads",
      "severity": "medium",
      "description": "Pothole roughly 40 cm wide and several cm deep in the westbound lane at the painted crosswalk on Maple Crescent near the park entrance. Drivers swerve toward the bike lane.",
      "status": "open",
      "opened_on": "2026-11-03"
    },
    {
      "id": "loc:ex-maple-crescent-crosswalk",
      "type": "Location",
      "name": "Maple Crescent at Park Entrance crosswalk (FICTIONAL)",
      "municipality": "Burnaby",
      "province": "BC",
      "country": "Canada"
    },
    {
      "id": "evidence:ex-photo-1",
      "type": "Evidence",
      "kind": "photo",
      "summary": "Daytime photo showing pothole adjacent to crosswalk paint (FICTIONAL artifact).",
      "captured_on": "2026-11-03"
    },
    {
      "id": "evidence:ex-map-note",
      "type": "Evidence",
      "kind": "note",
      "summary": "Citizen states the hole has been present for about two weeks and has widened after rain."
    }
  ],
  "relationships": [
    {"type": "REPORTED_BY", "from": "issue:ex-2026-pothole-001", "to": "citizen:example-alex"},
    {"type": "LOCATED_AT", "from": "issue:ex-2026-pothole-001", "to": "loc:ex-maple-crescent-crosswalk"},
    {"type": "ASSIGNED_TO", "from": "issue:ex-2026-pothole-001", "to": "dept:burnaby-engineering"},
    {"type": "HAS_EVIDENCE", "from": "issue:ex-2026-pothole-001", "to": "evidence:ex-photo-1"},
    {"type": "HAS_EVIDENCE", "from": "issue:ex-2026-pothole-001", "to": "evidence:ex-map-note"},
    {"type": "IN_JURISDICTION", "from": "loc:ex-maple-crescent-crosswalk", "to": "dept:burnaby-engineering"}
  ]
}
```

## Channel choice

Graph lookup points to Burnaby Engineering for road defects, with Burnaby Customer Service / BurnabyConnect as the common intake path for non-emergency reports. Engineering Dispatch is reserved for immediate hazards. This example uses BurnabyConnect-style intake via Customer Service because the hazard is serious but not an after-hours emergency.

## Draft for approval (example)

**To:** Burnaby Customer Service (via approved channel)  
**Subject:** Road defect report - pothole at Maple Crescent crosswalk (FICTIONAL)

Hello,

I am reporting a deep pothole in the westbound lane of Maple Crescent at the painted crosswalk near the park entrance in Burnaby. The hole is roughly 40 cm across and has been present for about two weeks. Drivers are swerving toward the bike lane to avoid it.

Attached is a photo taken on 2026-11-03 (example).

Request: Please inspect and repair the surface, and share a service reference number so I can follow up.

Thank you,  
Alex Example  
alex.example@example.com

## After citizen approval (example timeline)

| When | Action | Graph update |
|------|--------|--------------|
| Day 0 | Citizen approves draft; submitted via BurnabyConnect | `Action` created; fictional reference `BY-EX-104422` recorded; `FollowUp` due in 7 business days |
| Day 7 | Watchdog surfaces due FollowUp; polite status check drafted | Status inquiry Action linked |
| Day 9 | City marks repaired; citizen confirms | `Resolution` created; Issue closed |

## Escalation (not used in this happy path)

If there were no meaningful response after the FollowUp window, the next drafts would target Customer Service escalation, then Legislative Services for Mayor and Council correspondence, and only later the BC Ombudsperson after local processes were exhausted.

## What this example shows

- Schema entities and relationships in practice
- Evidence-backed drafting
- Approval before send
- Reference tracking and FollowUp cadence
- Clean closure without inventing facts
