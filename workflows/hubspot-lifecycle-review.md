# Workflow — HubSpot Lifecycle Review

## Purpose
Review and structure HubSpot lifecycle stages, ICP fit, pipeline and reporting for myFaro's GTM engine.

## Owner agent
`agents/revops-automation-agent.md`

## Trigger
Periodic RevOps review, or when pipeline data looks inconsistent.

## Inputs
- Current HubSpot lifecycle stages, deal stages and properties.
- Definitions from `memory/11_HUBSPOT_AND_REVOPS_OPERATIONS.md` and `03_ICP_AND_GTM_STRATEGY.md`.

## Steps
1. Review lifecycle stages against definitions; flag misused stages.
2. Distinguish lifecycle stage, ICP fit and disqualification reason.
3. Check that key properties are populated and consistent.
4. Review pipeline stages and conversion reporting.
5. Recommend automation (n8n / HubSpot workflows) to reduce manual entry while protecting data quality.

## Output
- Review summary with issues and recommended fixes.
- Prioritized action list for cleanup and automation.

## Guardrails
- Distinguish lifecycle stage vs ICP fit vs disqualification reason.
- Keep recommendations practical for a bootstrapped team.
- Protect data quality; avoid brittle over-automation.
