# Workflow — Meeting Transcript to Follow-up

## Purpose
Turn a raw meeting or call transcript (e.g. Fireflies) into structured account notes and a ready-to-send follow-up email.

## Owner agent
`agents/sales-playbook-agent.md`

## Trigger
A new transcript is available after a discovery call, demo or account meeting.

## Inputs
- Meeting transcript (text).
- Known account context (optional): ICP, current systems, prior notes.

## Steps
1. Categorize content under Positioning & Narrative, GTM Strategy, Sales Process & Playbooks, Compliance & Regulation and Competitive Intelligence.
2. Extract: account context, ICP fit, main pains, likely first use case, objections, decision process and stakeholders.
3. Determine the strongest use case and recommended next step.
4. Draft a concise follow-up email using `templates/sales-follow-up-email.md`.
5. Flag any compliance-sensitive statements for review.

## Output
- Structured discovery/account notes (`templates/discovery-summary.md`).
- Follow-up email draft (`templates/sales-follow-up-email.md`).
- Recommended next commercial action.

## Guardrails
- Do not invent facts not present in the transcript or knowledge base.
- Respect pricing, product and compliance guardrails.
- Always make the next step explicit.
