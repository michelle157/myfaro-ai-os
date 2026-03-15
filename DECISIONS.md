# Architectural Decisions

This document records the key architectural decisions for the MyFaro platform and the MyFaro AI-OS workspace.

The objective is to ensure that both humans and AI systems understand the principles behind the platform design.

---

# Decision 1 — API-First Architecture

MyFaro follows an API-first architecture.

Whenever possible, integrations with external systems should be implemented through APIs.

Reasons:

• interoperability with external systems  
• scalability of integrations  
• reduced manual data entry  
• easier automation  
• improved data consistency  

Examples include integrations with:

• financial data providers  
• CRM systems  
• company information providers  
• insurance institutions

---

# Decision 2 — CRM Agnostic Design

MyFaro is designed to be **CRM agnostic**.

Financial advisors already operate with different CRM systems and MyFaro should integrate with those environments rather than replace them.

Examples of CRM systems used by advisors include:

• BrokerCloud  
• Brio  
• HubSpot  
• other sector-specific CRM systems  

MyFaro therefore supports **API integrations with multiple CRM systems**.

Example:

B-Sure uses HubSpot CRM, which is currently integrated with MyFaro through selected field synchronisation.

However, HubSpot is not considered the default CRM for the platform.

---

# Decision 3 — Separation of Data and Documents

MyFaro separates **structured data storage** from **document storage**.

Structured data is stored in:

MongoDB

Examples:

• client records  
• financial objects  
• advisory calculations  
• product references  

Documents are stored in:

Microsoft SharePoint

Two environments exist:

myfaro-client  
stores documents related to end clients

myfaro-general  
stores internal MyFaro company documentation

This separation improves scalability, document management and compliance.

---

# Decision 4 — Multiple Data Aggregation Methods

Financial data can enter MyFaro through several mechanisms.

1. API integrations  
2. HTML ingestion modules  
3. CSV file ingestion

CSV ingestion is important because not all financial institutions provide APIs.

The CSV import pipeline performs:

• structural validation  
• data consistency checks  
• field mapping  
• database ingestion

This mechanism allows advisors to import portfolio data when direct integrations are unavailable.

---

# Decision 5 — AI Augmented Advisory Model

AI is used to support financial advisors, not replace them.

AI systems assist in:

• analysing financial information  
• structuring advisory data  
• supporting compliance processes  
• automating workflows

Final advice and professional responsibility remain with the human advisor.

---

# Decision 6 — Structured Knowledge Repository

The MyFaro AI-OS repository acts as the **shared knowledge workspace for AI systems and developers**.

All operational knowledge should be stored in structured markdown files.

The repository contains:

• architecture documentation  
• domain knowledge  
• reusable AI skills  
• automation workflows

This allows both humans and AI systems to work from the same knowledge base.

---

# Decision 7 — Modular AI Workflow Architecture

AI workflows are organised using modular components.

These components include:

memory  
long-term knowledge

skills  
reusable reasoning patterns

tools  
interfaces with systems

automation  
workflow orchestration

This structure allows AI agents to dynamically compose workflows.

---

# Decision 8 — Automation Through n8n

Operational automation is implemented using **n8n**.

n8n is used to orchestrate:

• system integrations  
• operational workflows  
• automation tasks  

This approach allows MyFaro to automate processes without tightly coupling automation to the core application code.

---

# Decision 9 — Multi-AI Development Environment

The MyFaro development environment supports multiple AI systems.

Current tools include:

• Claude Code  
• OpenAI Codex / ChatGPT  
• GitHub Copilot  

Each AI system uses its own instruction file but shares the same repository knowledge base.

This approach allows developers to work with the AI system that best suits their workflow.

---

# Decision 10 — Repository as AI Operating System

The MyFaro AI-OS repository acts as the **operational layer for AI-assisted development and workflows**.

The repository provides:

• shared knowledge for AI systems  
• structured documentation  
• reusable workflow components  

It acts as the **single source of truth for AI-assisted operations within MyFaro**.