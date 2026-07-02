# 11 - HubSpot & RevOps Operations

## HubSpot role
HubSpot is myFaro’s internal GTM and CRM engine. It is used for sales, marketing, website/CMS, lifecycle stages, deal tracking, contacts, companies, lists and automation where subscription allows. Important distinction: HubSpot is part of myFaro’s internal GTM stack. myFaro as a product remains CRM-agnostic for customers.

## Current context
Known points:
- HubSpot CMS custom theme is used for the website.
- Website has NL, FR and EN pages.
- Fonts: Montserrat / Helvetica.
- Discovery CTA link is active.
- Marketing Hub Starter used by Marieke.
- Sales Starter automation limitations were encountered.
- Sales Professional upgrade was discussed for workflow automation.
- Marketing Starter alone does not solve Sales Pro automation needs.

## Lifecycle stages
Known lifecycle stages:
- Marketing Qualified Lead (MQL)
- Sales Qualified Lead (SQL)
- Opportunity
- Customer
- Evangelist
- Other

Lifecycle stage says where someone is in the funnel. It should not be used to express fit.

## ICP Fit property
ICP Fit should be a separate property, ideally at company level.

Suggested values:
- Strong ICP
- Medium ICP
- Weak ICP
- Not in ICP
- Unknown

Reason: fit belongs to the account. A company can be a strong ICP even if a current deal is lost due to timing. A company can be not in ICP even if it once engaged with content.

## Disqualification Reason
Disqualification Reason explains a sales decision at a moment in time. It can exist at company level for global account status and at deal level for opportunity-specific loss.

Recommended values:
- Not in ICP
- No life/investment/pension activity
- No budget
- No urgency
- Timing not right
- Wrong use case
- Custom development requirement
- Existing vendor lock-in
- Duplicate / irrelevant
- Other

Why include Not in ICP as a disqualification reason if ICP Fit exists? Because the two fields answer different questions. ICP Fit is stable segmentation. Disqualification Reason explains why sales is not pursuing now.

## Deal stages
Recommended stages:
1. New / identified
2. Discovery planned
3. Discovery completed
4. Demo planned
5. Demo completed
6. Proposal sent
7. Negotiation / legal
8. POC / validation
9. Closed won
10. Closed lost
11. Nurture / revisit later

## Pipeline automation use case
Original desired automation: when a deal enters closed won and a certain property changes, automatically send a customer email with a meeting link for the customer success manager.

Issue: Sales Starter automation limitations can block this. Sales Hub Professional may be required.

Alternatives depending subscription:
- create manual task when deal closes
- use templates/snippets
- use sequences if available
- use n8n, Zapier or Make via HubSpot API
- upgrade to Sales Professional for workflow automation

## Sales Professional seat consideration
If upgrading, identify which users actually need Professional features. Users who need advanced automation, sequences or sales tools may require paid seats. Users who only need basic visibility may not. Because HubSpot packaging changes, always confirm current seat rules before purchasing.

## Lists and consent
Starter limitations may require manual updates. Forms should capture or infer language. Hidden language fields are useful for NL/FR/EN. Default NL-BE can be set through workflow when available.

Newsletter segmentation:
- **Faro Focus**: prospects, customers, partners, subscribers, high-fit engaged leads.
- **Faro Updates**: customers, active users, implementation contacts and customer success stakeholders.

## Leadinfo workflow
When Leadinfo identifies a website visitor:
1. identify company
2. check ICP fit
3. add/update HubSpot company if relevant
4. create task for outreach if high fit
5. personalize outreach based on page visited

## Data hygiene rules
- every company should have ICP Fit
- every disqualified lead should have reason
- every opportunity should have a clear next step
- meeting notes should attach to company and deal
- demo angle/use case should be captured
- closed lost should include reason and revisit date if relevant
- customers should have onboarding status

## Recommended properties

### Company properties
ICP Fit, segment, country/language, main CRM/system, life/investment activity, estimated active dossiers, partner source, lead source, strategic priority and disqualification reason.

### Deal properties
Use case, package proposed, dossier count, onboarding fee, discount applied, first milestone, decision date, next step, closed lost reason and revisit date.

### Contact properties
Language, role/persona, buying role, newsletter subscription and event attendance.

## Reporting dashboards
Useful dashboards:
- deals by stage
- deals by ICP fit
- demos by source
- discovery-to-demo conversion
- demo-to-proposal conversion
- closed lost reasons
- pipeline by segment
- BZB campaign performance
- newsletter engagement by ICP
- website visitor to meeting conversion

## HubSpot agent instruction
When creating HubSpot or RevOps advice: distinguish lifecycle from fit, prefer company-level fit properties, use deal-level fields for opportunity context, respect subscription limitations, do not assume workflows exist in Starter and keep the setup practical for a small bootstrapped team.
