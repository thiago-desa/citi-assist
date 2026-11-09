# Skill: Extraction

Extract structured civic entities from a citizen message.

## Job

From the citizen message, extract:

- Issue entities (title, category, description, severity)
- Location entities
- Any mentioned Departments, prior reports, or evidence

## Output

Strict JSON triples. Every relationship must include an exact supporting quote from the message. Do not invent fields or facts that are not present.
