# citi assist

Persistent civic advocate Grok Bot for Burnaby, Metro Vancouver, BC, and Canada: turns a citizen-reported issue into an evidence-backed case, drafts formal submissions for approval, tracks follow-ups, and escalates through verified official channels until resolution.

## Problem it solves

Municipal and higher-level complaints stall when people do not know the right department, the right contact method, or how to follow up. citi assist keeps a civic knowledge graph of issues, locations, departments, channels, evidence, actions, and follow-ups so each report is investigated, written up carefully, approved by the citizen before anything is sent, and watched until it closes.

## How to use with Grok Bot

1. Create a new Grok Bot (suggested name: `citi assist`).
2. Paste the contents of `agents/citi-assist.md` (the **Description / system instructions** section) into the bot description / instructions.
3. Optionally attach or point the bot at `graphs/schema.md` and `graphs/seed-departments-channels.json` as its starting civic knowledge store layout.
4. Add a weekday morning routine that runs the watchdog pass described in `skills/watchdog-followups.md` (around 09:00 America/Vancouver works well).
5. Tell the bot to initialize from the public seed, confirm channels, and wait for the first issue.
6. When it drafts a letter, email, or form submission, approve the exact text before anything goes out.

Skills in `skills/` are narrow prompts you can keep alongside the bot or paste into standing instructions.

## Key files

| Path | What it is |
|------|------------|
| `agents/citi-assist.md` | Full sanitized agent definition |
| `graphs/schema.md` | Entity types, relationships, mermaid diagram |
| `graphs/seed-departments-channels.json` | Public seed of departments and verified channels |
| `skills/` | Extraction, investigation, drafting, writing style, maintenance, watchdog |
| `skills/writing-style.md` | Communication and Negotiation Graph for drafts and follow-ups |
| `docs/architecture.md` | Super-agent and graph design |
| `docs/workflow.md` | Intake through escalation and approval gates |
| `examples/fictional-pothole-case.md` | Fully fictional end-to-end walkthrough |
| `ATTRIBUTION.md` | Design influences and official source notes |
| `LICENSE` | MIT |

## Proof-of-work notes

This repository is a cleaned public snapshot of a working Grok Bot design:

- Typed civic ontology with escalation paths
- Verified-channel rules (`source_url`, `verified_on`, `status`)
- Router/worker operating model and weekday watchdog cadence
- Approval gates before any send-on-behalf step
- Communication and Negotiation Graph applied to formal drafts and follow-ups
- Example case that is labeled fictional (no real citizen case data)

Contact values in the seed file are taken from public official pages and were checked on 2026-11-09 (America/Vancouver). Re-verify before real use. See `ATTRIBUTION.md`.

## License and attribution

MIT License. Copyright (c) 2026 Thiago De Sa.

Design influences and official channel sources are listed in `ATTRIBUTION.md`.
