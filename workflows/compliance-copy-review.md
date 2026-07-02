# Workflow — Compliance Copy Review

## Purpose
Review any sales, marketing or content copy for regulatory risk and rewrite it with compliance-safe language.

## Owner agent
`agents/compliance-agent.md`

## Trigger
Any external-facing copy before publishing or sending.

## Inputs
- Draft copy (email, post, one-pager, proposal, website text).
- Context: audience and channel.

## Steps
1. Scan for absolute legal claims ("FSMA-proof", "guaranteed compliance", "fully compliant").
2. Check claims against `memory/05_COMPLIANCE_AND_REGULATION.md` and `memory/ComplianceRules_FSMA.md`.
3. Rewrite risky phrases using supports / structures / documents / embeds / audit-ready language.
4. Flag statements that need human expert or legal validation.
5. Produce a compliance note using `templates/compliance-note.md`.

## Output
- Revised copy with tracked changes/notes.
- Compliance note (`templates/compliance-note.md`) listing risks and recommendations.

## Guardrails
- Never approve guarantees of compliance.
- Do not invent regulatory requirements.
- Recommend expert validation where interpretation is needed.
