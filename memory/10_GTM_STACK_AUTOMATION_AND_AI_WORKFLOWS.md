# 10 - GTM Stack, Automation & AI Workflows

## Current GTM stack
myFaro operates in a bootstrapped environment. The GTM stack must prioritize leverage, structure and reusability over expensive complexity.

Known systems:
- LinkedIn company page and Michelle personal profile
- LinkedIn Sales Navigator, Premium Business / Premium Pages
- HubSpot Sales, Marketing and CMS
- Fireflies for transcripts
- Outlook and Teams
- SharePoint and OneDrive
- Claude, Claude Projects and Claude CoWork
- OpenAI / ChatGPT
- Microsoft Copilot and Copilot Studio
- n8n preferred for automation
- Zapier or Make as alternatives
- Leadinfo for website visitor identification
- Canva for visuals
- DocuSign
- Creditsafe
- AirCall

## Strategic AI principle
AI should not be used as random copy generation. It should become a structured GTM operating system. The real value comes from organizing inputs from ChatGPT history, Claude projects, OneNote, Teams, Fireflies transcripts, HubSpot notes, SharePoint documents, website copy, LinkedIn posts and sales emails into reusable knowledge modules, prompts and workflows.

## Claude migration objective
The right structure is not one giant text file. Use a modular markdown knowledge base plus specialized agents. Recommended Claude setup:
- one main project: `myFaro - Sales & GTM Engine`
- specialized projects/agents for content, outbound, demo prep, compliance messaging, proposals, RevOps and customer success
- all agents must preserve positioning, ICP, pricing and compliance guardrails

## Knowledge base architecture
Use these modules:
1. positioning and narrative
2. product and technical architecture
3. ICP and GTM strategy
4. sales process and playbooks
5. compliance and regulation
6. competitive intelligence
7. pricing and packaging
8. partnerships and key accounts
9. content and LinkedIn
10. GTM stack and AI workflows
11. HubSpot and RevOps
12. customer success and onboarding
13. agent instructions

## Source intake workflow

### Calls and transcripts
Sources: Fireflies, Teams recordings, demo transcripts, discovery calls and partner calls.

Process:
1. summarize meeting
2. extract sales insights
3. identify use case
4. update account notes
5. create follow-up email
6. create next-step tasks
7. extract content ideas if relevant

### HubSpot data
Sources: companies, contacts, deals, notes, lifecycle stage, ICP fit and disqualification reason.

Process: segment accounts, identify stuck deals, generate next best action, draft follow-ups and update nurture lists.

### SharePoint documents
Sources: proposals, one-pagers, compliance documents, product documentation, event materials and customer notes.

Process: categorize, extract reusable language, identify outdated claims and convert into knowledge modules.

### LinkedIn/content inputs
Sources: posts, comments, newsletters, event topics and competitor posts.

Process: extract themes, map to content pillars, create post/newsletter/campaign and connect to sales segment.

## n8n automation strategy
n8n is preferred because it offers flexible workflow orchestration and more control than basic no-code tools.

Potential workflows:

### Fireflies to HubSpot to Claude
Trigger: new meeting transcript. Steps: retrieve transcript, identify company/contact/deal, summarize, extract next steps, create HubSpot note, draft follow-up and create task.

### Website visitor to ICP enrichment
Trigger: Leadinfo identifies company. Steps: enrich company, check ICP fit, create/update HubSpot company, alert sales if high-fit and suggest outreach angle.

### LinkedIn content engine
Trigger: new source note or transcript insight. Steps: classify pillar, generate Michelle-style post, create company variant, create newsletter expansion and store in backlog.

### Deal stage automation
Trigger: deal stage change. Steps: create tasks, generate material, notify team and prepare onboarding checklist when closed won.

Important HubSpot constraint: Starter versions have automation limits. Sales Professional may be required for more advanced workflows.

## Hermes / Trigify / Obsidian concept
There has been interest in Hermes, Trigify and Obsidian-like workflows. Strategic interpretation: Hermes-style self-improving agents may be powerful, Trigify-like lead triggers may help social selling and Obsidian-style notes may support knowledge compounding. But do not start with complexity. First build the knowledge base, define agent roles, standardize meeting follow-up, standardize content generation, add HubSpot/Sales Navigator triggers and only then add self-improvement loops.

## Claude versus ChatGPT usage
Claude is useful for long context synthesis, document-based projects, tone consistency, content generation and structured markdown workflows. ChatGPT/OpenAI can remain useful for reasoning, artifacts, multi-tool workflows, image generation, spreadsheet/docx/pptx tasks and web-updated research. The right strategy is workflow-based tool choice, not replacing everything with one model.

## Sales automation priorities
1. **Meeting follow-up engine**: every transcript becomes summary, account insight, follow-up email, next-step task and updated use case.
2. **Content repurposing engine**: every strong insight becomes personal post, company post, newsletter paragraph and sales email snippet.
3. **ICP and lead scoring**: every account scored by segment, life/investment relevance, size, trigger, engagement and known systems.
4. **Proposal support**: generate proposal drafts based on package, dossier count, onboarding, discount logic, first milestone and terms guardrails.

## AI governance rules
Keep sensitive incidents out of generic content agents. Do not let AI invent pricing, integrations or legal conclusions. Use approved knowledge base files as source of truth. Review external compliance/legal content manually. Store final approved messages and proposals. Keep NL/FR/EN aligned.

## Recommended folder structure
`/myFaro_Knowledge_Base`: Index, Positioning, Product, GTM, Sales Playbooks, Compliance, Competitors, Pricing, Partners/Accounts, Content, RevOps, Customer Success, Agent Instructions, Inbox_Unprocessed, Approved_Output, Archived_Old.

## Agent instruction
Every automation should ask: Which domain is this? Which ICP? Which use case? What pricing/compliance guardrails apply? What is the next commercial action?
