# Architecture

citi assist is a persistent civic issue resolution bot for Burnaby / Metro Vancouver / BC / Canada. The design combines a typed knowledge graph, a router/worker super-agent pattern, and narrow verifiable skills.

## Goals

Whenever a citizen reports an issue, the bot:

1. Investigates in detail
2. Builds a formal, evidence-backed case
3. Elevates it through correct official channels (after approval)
4. Follows up until resolution

## Super-agent characteristics

- **Continuous** - one persistent agent identity across interactions
- **Productive** - multiple Issues in parallel
- **Proactive** - monitors, follows up, spots patterns
- **Persistent** - recovers from interruptions; keeps graph state

## Two-level design

### Router (long-lived, global)

- Receives every citizen message
- Maintains the open-Issue picture
- Classifies: new Issue, update, status check, general question
- Dispatches Workers or answers simple queries
- Owns all citizen-facing replies
- Uses chain-of-recall for older Issues

### Worker (isolated, task-specific)

- One Worker per Issue (or tight cluster)
- Research, draft formal notices, prepare submissions, analyze evidence
- Reports status and conclusions back to the Router
- Does not talk directly to the citizen as a separate voice

## Event-driven triggers

Citizen messages, scheduled follow-ups, and external updates are Triggers.

- **Fast path:** obvious status checks, known channel routing
- **Slow path:** novel issues, multi-hop reasoning, drafting

## Context management

- **Inline and spill:** keep current Issue id, key facts, and a subgraph summary in context; spill long evidence lists and retrieve on demand
- **Chain of recall:** Issue to related Actions to prior similar Issues to Regulations

## Watchdog

Periodic routine (weekday morning in the live setup):

- Scan open Issues for stalled FollowUps
- Flag low-confidence or contradictory evidence
- Suggest escalations
- Optional entity-resolution cleanup pass

## Tools and grounding

- Web search / browse of official sites (for example burnaby.ca, bcombudsperson.ca, canada.ca)
- Filesystem for evidence and generated letters (local to the bot)
- Memory / JSON graph persistence
- Optional email or calendar connectors only if the citizen connects them

Production rules:

- Log every Action and evidence path
- Never invent reference numbers
- Confirm submissions with the citizen before sending on their behalf
- Minimize personal data

## Jurisdiction focus

Configurable. Seeded for City of Burnaby, Metro Vancouver, British Columbia, and Canada. Extend by verifying new Departments and OfficialChannels against official sources.

## What this repo is

A public-ready snapshot of the agent definition, ontology, skills, workflow docs, and a fictional end-to-end example. It is not a live case database.
