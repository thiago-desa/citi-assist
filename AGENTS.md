# AGENTS.md

Short, high-signal instructions for coding agents working in `citi-assist`.

## What this repo is

Persistent civic advocate Grok Bot: evidence-backed municipal cases, approved submissions, verified channels, and watchdog follow-ups.

This is a sanitized proof-of-work snapshot of a Grok Bot design. Markdown skills and docs are the product. There is no service binary to compile.

## Layout

| Path | Role |
|------|------|
| `agents/` | Sanitized agent definition |
| `skills/` | Extraction, investigation, drafting, writing style, maintenance, watchdog |
| `graphs/` | Civic schema and public seed channels |
| `docs/` | Architecture, workflow, failure modes |
| `evals/` | Golden set of fictional civic cases |
| `examples/` | Fictional end-to-end walkthrough |
| `scripts/check.py` | Hygiene CI entrypoint |

## Commands

```bash
python scripts/check.py
```

There is no application build. Treat markdown skills and the golden set as the executable contract.

## Hard boundaries

- Never commit secrets, tokens, or `.env` files.
- Never add real citizen cases, addresses, businesses, reference numbers, or personal contacts.
- Official channel values belong only in `graphs/seed-*.json` when taken from public pages, with `source_url` and `verified_on`.
- Never claim the bot sends mail or files forms without an explicit approval gate.
- No em dashes or en dashes in prose.
- Do not invent bylaws, ticket IDs, or phone numbers.

## Definition of done

- Touched skills/docs match `agents/citi-assist.md`.
- New behaviors have at least one golden-set case in `evals/`.
- `python scripts/check.py` passes.
- README Key files table lists new paths.
- Import link in README remains intact.

## Ownership

Maintained by Thiago De Sa. Irreversible git/GitHub actions (new public repo, first push, force-push, delete, visibility change) need the owner's explicit approval even when an agent stages the work.
