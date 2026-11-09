# Failure modes and troubleshooting

Honest limits of the citi assist design. These are design notes, not claims that every runtime automatically recovers.

## Channel and grounding failures

| Failure | What it looks like | What to do |
|---------|--------------------|------------|
| Stale official channel | Seed email or form URL 404s or redirects | Re-open the official page, update `source_url` / `verified_on` / `status`, refuse to submit on stale data |
| Invented regulation cite | Draft cites a bylaw not confirmed in Evidence | Strip the cite; attach only regulations you opened |
| Wrong owning department | Complaint routed to an adjacent but wrong unit | Re-run investigation against the seed graph plus live search; ask the citizen one clarifying question |
| Missing provenance | Fact in the graph with no source | Do not use it in a formal draft until sourced |

## Process and approval failures

| Failure | What it looks like | What to do |
|---------|--------------------|------------|
| Draft sent without approval | Any outbound without citizen yes on exact text | Hard stop; this is a policy breach. Restore approval gate |
| Watchdog noise | Daily pings when nothing is due | Watchdog stays silent unless a FollowUp is due/stalled or a draft needs the citizen |
| Parallel issue confusion | Updates applied to the wrong Issue | Router keeps Issue ids explicit; Workers stay isolated per Issue |
| Emergency misuse | User describes immediate danger | Direct to 911; do not treat the bot as emergency dispatch |

## Graph and entity failures

| Failure | What it looks like | What to do |
|---------|--------------------|------------|
| Duplicate Location / Issue | Same street reported twice as new | Run entity resolution before create; link as related if distinct |
| Context pollution | Long thread dumps unrelated cases into a draft | Pull only the active Issue subgraph |
| Escalation too early | Jump to Mayor or Ombudsperson first | Follow the documented municipal path unless channels require otherwise |

## Verification layer (design)

Formal drafts should cite Evidence nodes or exact public URLs, flag contradictions, and keep channel `status` visible. The weekday watchdog is the recovery loop for stalled FollowUps. Confidence stays low whenever `status=unverified` or sources are older than the re-check window.
