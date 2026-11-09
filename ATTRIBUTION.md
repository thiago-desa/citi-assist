# Attribution

This proof-of-work repository documents a Grok Bot civic advocacy design by Thiago De Sa (2026).

## Design influences (ideas, not code)

The agent architecture described in `docs/architecture.md` and `agents/citi-assist.md` draws on publicly discussed patterns:

- Graph engineering / GraphRAG style knowledge graphs for retrieval and grounding (commonly associated with work discussed by practitioners at Microsoft, Stanford, MIT, and related GraphRAG literature).
- Andrew Ng's AI Engineering skills framing: grounding, agentic systems, evaluation-driven development, and production operations.
- Super-agent harness ideas often summarized as continuous, productive, proactive, and persistent agents, with router/worker separation, event-driven triggers, inline-and-spill context, chain of recall, and watchdog maintenance (DeepSeek harness style discussions in the public agent community).

None of the above are copied as proprietary text or code. Names are credited here because the original design note referenced them as conceptual sources.

## Official channel seed data

`graphs/seed-departments-channels.json` contains publicly published contact methods for municipal, regional, provincial, and federal bodies (for example City of Burnaby, BC Ombudsperson, Metro Vancouver, TransLink, BC Hydro, Service BC, and Service Canada). Values were verified against official pages on 2026-11-09 (America/Vancouver). Always re-check the live official site before using a phone number, email, or form URL in a real submission.

Primary verification sources are listed under `meta.seed_verification.sources` in the seed file.


## Writing and negotiation influences (ideas, not verbatim text)

`skills/writing-style.md` synthesizes classic public negotiation and influence ideas into a graph-shaped drafting checklist for civic messages:

- Dale Carnegie, *How to Win Friends and Influence People* (sincere appreciation, avoid habitual criticism, talk in terms of others' interests).
- Chris Voss, *Never Split the Difference* (tactical empathy, labeling, mirroring, accusation audits, calibrated questions).
- Robin Dreeke, *Sizing People Up* (vesting, longevity, reliability, language, stability).
- Fisher, Ury, and Patton, *Getting to Yes*, and related interest-based bargaining ideas including BATNA and separating people from the problem (including themes discussed in hard-bargaining literature such as *Bargaining with the Devil*).

These are credited as conceptual sources. The skill text is an original civic-bot adaptation, not a reproduction of any book.

## License

MIT License. Copyright (c) 2026 Thiago De Sa. See `LICENSE`.
