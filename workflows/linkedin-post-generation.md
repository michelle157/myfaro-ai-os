# Workflow — LinkedIn Post Generation

## Purpose
Generate a LinkedIn post in Michelle's voice, anchored in a real advisor insight and the operating-layer narrative.

## Owner agent
`agents/content-agent.md`

## Trigger
A topic, insight, event or transcript worth turning into content.

## Inputs
- Topic or insight.
- Target ICP / audience.
- Optional source material (transcript, article, market observation).

## Steps
1. Identify the core insight and the audience (ICP).
2. Choose the content pillar from `memory/09_CONTENT_LINKEDIN_AND_THOUGHT_LEADERSHIP.md`.
3. Draft the post using `templates/linkedin-post.md` in Michelle's senior, vision-driven tone.
4. Remove AI filler, hype, excessive bullets and repeated negation.
5. Run compliance-sensitive language check.

## Output
- Finished LinkedIn post (`templates/linkedin-post.md`).
- Optional variations (hook alternatives).

## Guardrails
- Avoid generic AI language and exaggerated SaaS claims.
- Anchor in a concrete market insight.
- Keep positioning consistent (operating layer / ERP layer).
- No absolute legal claims.
