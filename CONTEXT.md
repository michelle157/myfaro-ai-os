# MyFaro AI Context

This file provides global context for AI systems interacting with the MyFaro AI-OS repository.

The goal is to ensure that AI assistants understand the domain, architecture and intended use of the workspace.

---

# Company Context

MyFaro is a financial advisory enablement platform designed for:

• financial advisors  
• insurance brokers  
• wealth planners  
• accountants  
• legal advisors  

The platform supports professionals operating in **multi-supplier financial environments** where client data is fragmented across institutions.

The platform focuses on:

• financial planning  
• pension optimisation  
• compliance support  
• client advisory workflows  
• aggregation of financial data across financial institutions  

MyFaro is positioned as a **data aggregation and advisory enablement layer**.

The system is designed to **augment human advisors with AI tools**, not replace them.

Human advisors remain responsible for professional judgement and final client advice.

---

# Core Technology Stack

## Backend
Ruby on Rails

## Frontend
React

## Database
MongoDB (primary application database)

MongoDB stores structured data such as:

• client data  
• advisory objects  
• financial positions  
• product references  

## Product Data - this is also included in the database

MyFaro maintains an internal **funds and product database** containing:

• fund metadata  
• KIDs  
• PRIIPs  
• product documentation  
• financial product information used in advisory workflows  

## Infrastructure
AWS

## Automation
n8n

## AI Development Tools

The development team uses several AI systems:

• Claude Code  
• OpenAI Codex / ChatGPT  
• GitHub Copilot  

All AI systems interact with the same repository structure.

---

# Document Storage Architecture

MyFaro separates **structured data storage** from **document/file/blob storage**.

## Structured Data

Structured financial and advisory data is stored in:

MongoDB

Examples include:

• client profiles  
• financial objects  
• advisory calculations  
• product references  

## Document Storage

The meta-data for docucuments, as well as the security model are embedded in the myFaro application and database.
The files/blobs and basic metadata are stored in **Microsoft SharePoint** environments.

Two main SharePoint environments exist.

### myfaro-client

This SharePoint environment stores **documents related to end clients**.

Documents follow a structured hierarchy that mirrors MyFaro objects.

Examples:

• client documents  
• advisory reports  
• uploaded financial documentation  
• supporting documents for financial objects  

AI systems retrieving or analysing client documents must respect this structure.

### myfaro-general

This SharePoint environment stores **internal MyFaro company documents**.

Examples:

• sales documentation  
• licensing agreements  
• proposals and contracts  
• marketing materials  
• internal documentation  

These documents are not related to end-client financial data.

---

# CRM Philosophy

MyFaro is **CRM agnostic**.

Financial advisors typically operate with their own CRM systems and MyFaro is designed to integrate with these systems rather than replace them.

Examples of CRM systems used by advisors include:

• BrokerCloud  
• Brio  
• HubSpot  
• other sector-specific CRM systems  

MyFaro aims to support **API-based integrations with these CRM systems** whenever possible.

This allows client data to flow between advisory workflows and CRM environments without duplication.

Example:

B-Sure uses **HubSpot CRM**, which is connected to MyFaro through a push/pull API integration on selected fields.

However, HubSpot is **not the default CRM for MyFaro users**.

---

# External Data Sources

MyFaro integrates with several external data providers and systems.

These integrations reduce manual data entry and improve data completeness.

## Financial Market Data

Infront API

Provides:

• financial market data  
• fund information  
• financial product data  

This data is complementented with some basic scraping of third-party sites.

## Company Data

Creditsafe API & CompanyWeb API

Provides:

• company registry data  
• credit data  
• due diligence information  

Used in compliance and advisory workflows.

## Government Data Sources

MyFaro retrieves financial information from several government portals.

Examples:

• MyPension  
• MyMinFin  
• MyCareer  

These integrations currently use **HTML/PDF ingestion modules** built internally.

---

# Portfolio Data Aggregation

Not all financial data can be retrieved directly through APIs.

To address this, MyFaro includes an **internal data aggregation mechanism**.

Financial advisors can upload portfolio data using **CSV/XML/PDF files**.

These files are processed through a validation pipeline that:

• validates file structure  
• checks data consistency  
• maps fields to the MyFaro data model  
• imports the data into MongoDB  

This mechanism allows advisors to import financial data when:

• insurers do not provide API access  
• portfolio data is exported from other systems  
• historical data needs to be migrated  

The CSV ingestion system is an important fallback mechanism for data aggregation.

---

# Platform Philosophy

MyFaro follows several architectural principles.

### API-First Architecture

The platform is designed to integrate with the systems used by financial advisors.

Examples include:

• CRM systems  
• insurance providers  
• financial data providers  

The objective is to create a **connected advisory ecosystem**.

### AI Assisted, Human Supervised

AI systems assist advisors in:

• analysing information  
• structuring data  
• automating workflows  

Human advisors remain responsible for decisions.

### Structured Knowledge

Knowledge is stored in **structured markdown files** so that both humans and AI systems can interpret it.

### Modular Workflows

Capabilities are separated into modular components:

• memory  
• skills  
• tools  
• automation  

This allows AI agents to compose workflows dynamically.

---

# AI-OS Purpose

This repository provides the internal AI workspace used to design and operate AI-assisted workflows.

The workspace allows:

• humans  
• AI agents  
• automation systems  

to collaborate on advisory processes.

Examples include:

• compliance analysis  
• workflow automation  
• support ticket analysis  
• document interpretation  
• advisory assistance

---

# AI System Entry Points

Different AI systems use different instruction files.

| AI System | Instruction File |
|-----------|------------------|
| Claude Code | CLAUDE.md |
| OpenAI Codex / ChatGPT | AGENTS.md |
| GitHub Copilot | .github/copilot-instructions.md |

All systems share the same repository structure.

---

# Key Repository Areas

### memory/

Long-term domain knowledge.

Examples:

• regulatory knowledge  
• architecture  
• business logic  

### skills/

Reusable AI capabilities.

Examples:

• analyse a support ticket  
• generate compliance advice  
• build automation workflows  

### tools/

Interfaces with external systems.

Examples:

• APIs  
• automation scripts  
• integrations  

### n8n/

Automation workflows for operational processes.

### docs/

Architecture decisions and operational runbooks.

---

# Behaviour Expectations for AI Systems

When AI interacts with this repository it should:

1. Prefer structured knowledge from `/memory`
2. Use `/skills` as reusable reasoning patterns
3. Use `/tools` to interface with systems
4. Avoid inventing undocumented business logic
5. Document newly created workflows

---

# Operating Principle

One repository  
One knowledge base  
Multiple AI systems

The repository acts as the **single source of truth for AI-assisted operations within MyFaro.**
