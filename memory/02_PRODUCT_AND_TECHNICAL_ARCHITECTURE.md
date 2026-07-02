# 02 - Product & Technical Architecture

## Product scope
myFaro is a CRM-agnostic operating layer supporting advisory workflows across life insurance, investment insurance, Tak 23, pensions, IPT, POZ, VAPZ, second pillar, financial planning, estate planning, banking assets, private equity, real estate, companies, maatschappen, compliance workflows and consolidated reporting.

The product should be explained as a structured operating environment rather than a loose set of modules.

## Core product principle
The advisor should never be confronted with unnecessary complexity. The workflow should trigger the right questions, data fields, documents and checks only when they are relevant. Context determines the workflow. The workflow determines required data. Data determines documents, calculations and reporting. Actions create an audit trail.

## Architecture in business terms
myFaro sits between four worlds:

1. advisor relationship systems such as CRM, email, meeting notes and client communication
2. supplier environments such as insurer portals, bank systems, contracts and product data
3. external data sources such as market data, company data and public pension/tax data
4. client-facing reports, documents and portal output

myFaro connects these worlds through structured workflows.

## Main data domains

### Client data
Identity, contact details, family composition, marital status, professional status, company relationships, household structures, UBO information where relevant, client segmentation, financial situation, investment objectives, knowledge and experience, risk profile and preferences.

### Contract and policy data
Supplier, policy number, product category, premium, contribution logic, value, beneficiaries, underlying funds, wrapper, tax regime, start date, maturity date, guarantees and linked documents.

### Portfolio data
Consolidated market value, holdings, asset allocation, performance, product wrapper, bank or insurer source, liquidity profile, risk classification, private markets allocation, pension allocation and cash/banking positions.

### Pension data
Remuneration, company data, legal pension parameters, IPT, VAPZ, POZ, 80%-rule inputs, fiscal capacity, contribution history, pension projection and pension contract overview.

### Compliance data
Identification status, KYC, AML risk, risk profile, knowledge and experience, suitability or appropriateness evidence, product rationale, generated documents, signed versions, timestamps, workflow steps and audit trail events.

### Reporting data
Consolidated asset overview, portfolio by supplier, product type, return data, pension overview, financial plan, client-facing report, advisor commentary and PDF output.

## Main functional areas

### Client overview
Gives the advisor a structured view of the client, household, companies, contracts, wealth, missing data, compliance status and next actions.

### Contract and portfolio overview
Centralizes life, investment and pension contract data across suppliers. This creates visibility over active/passive dossiers, values, suppliers and reporting opportunities.

### Compliance workflow
Embeds KYC, AML, risk profile, knowledge and experience, product matrix logic, document generation and audit evidence in the advisory process.

### Pension and 80%-rule workflow
Supports pension advice and fiscal optimization by centralizing company data, remuneration inputs, pension contracts, 80%-rule calculations and supporting documents.

### Reporting and route plan
Produces consolidated, advisor-branded reporting and planning output. Known strategic point: the existing route plan / financial planning report builder is considered outdated and may need modernization through embedded analytics or a stronger reporting layer.

### Digital vault
Document storage is SharePoint-based, which supports document governance and reduces vendor lock-in. This is strategically important when prospects ask about data portability or termination.

### Client portal / advisor environment
The client should interact through the advisor’s own environment rather than being pushed into the insurer’s portal. This protects advisor ownership of the client relationship.

## Integrations and data sources
Known or relevant sources and systems include:

- **Infront** for NAV and market value data
- **Creditsafe** for company/KYC-related information
- **myMinfin / myPension** as relevant public-data sources or roadmap context
- **DocuSign** for digital signing and possible JSON-style exchange packages
- **SharePoint / OneDrive** for the vault/document architecture
- **HubSpot** internally for GTM, not as a product dependency
- **Brio / Brokercloud / other CRMs** as customer-side relationship or BOAR systems next to which myFaro can sit
- **insurer/bank systems** through API, document exchange, data import/export or portal fallback depending on availability

Never promise a specific live integration unless confirmed. Use cautious language: “the exact integration depends on the source system and available access.”

## Workflow example
1. Select or create client.
2. Complete profile, household and company data.
3. Identify advisory need: pension, investment, estate planning, reporting, onboarding, compliance update.
4. Trigger relevant data fields and documents.
5. Run calculations/checks where applicable.
6. Generate advice or reporting output.
7. Capture signatures or approvals.
8. Store evidence and documents.
9. Log actions in audit trail.
10. Create next action or review moment.

## Audit trail logic
The audit trail supports evidence of who did what, when, using which data, which document, which version and which workflow step. Use language such as “supports auditability”, “helps reproduce the advisory process” and “helps document required steps”. Avoid saying myFaro guarantees compliance.

## Reporting architecture
Reporting is a major use case. myFaro must support consolidated views across suppliers, contracts, wrappers, asset classes, pensions and wealth structures. Large clients may want PowerBI-style reporting across myFaro, Microsoft, Brio or other data. This creates a potential plugin/analytics opportunity.

## Luzmo / embedded analytics opportunity
Luzmo or a similar layer could potentially modernize the route plan/report builder, improve dashboards, add embedded analytics and support larger clients that need cross-system reporting. This is a strategic extension, not a confirmed promise unless validated.

## Product sales angles
- **Portfolio overview first**: create a full overview of life/investment contracts so reporting and follow-up become possible.
- **Compliance first**: embed required steps into the workflow with evidence and less manual document work.
- **Pension first**: centralize 80%-rule and pension workflows instead of relying on insurer portals.
- **Reporting first**: deliver consolidated client reporting across banks, insurers and investment wrappers.
- **Group scalability first**: standardize workflows across entities while leaving local CRMs in place where useful.

## Implementation approach
Start with one first milestone. Map systems and data sources. Configure workflows and users. Train core users. Run first client cases. Review adoption. Expand after the first workflow is operational.

## Roadmap guardrails
Treat insurer APIs, bank APIs, Luzmo, PowerBI plugins, Microsoft data integration, Brio/TM integration, improved route plan builder and AI-driven workflows as roadmap or exploration topics unless the user confirms availability.
