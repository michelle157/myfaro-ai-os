# MyFaro AI-OS

MyFaro AI-OS is the internal workspace used to design, test and document AI-assisted workflows for the MyFaro platform.

The goal of this repository is to provide a **structured environment where humans and AI agents collaborate** to design and operate financial advisory workflows.

This workspace is compatible with:

- Claude Code
- OpenAI Codex / ChatGPT
- GitHub Copilot

The repository acts as the **single source of truth for AI-assisted operations within MyFaro.**

---

# Core Principle

One repository  
One knowledge base  
Multiple AI entry points  

AI systems read the same repository structure but use different instruction files.

| AI System | Instruction File |
|----------|------------------|
| Claude Code | CLAUDE.md |
| OpenAI Codex / ChatGPT | AGENTS.md |
| GitHub Copilot | .github/copilot-instructions.md |

---

# Repository Structure

```text
myfaro-ai-os
├── README.md
├── CONTEXT.md
├── CURRENT-STATE.md
├── DECISIONS.md
├── AI.md
├── CLAUDE.md
├── AGENTS.md
├── .gitignore
│
├── .agents
│   └── skills
│
├── .github
│   └── copilot-instructions.md
│
├── agents
│   ├── compliance-agent.md
│   ├── advisory-agent.md
│   └── support-agent.md
│
├── docs
│   ├── adr
│   ├── runbooks
│   ├── WORKFLOW-PATTERNS.md
│   └── DATA-FLOWS.md
│
├── memory
│   ├── Architecture.md
│   ├── ComplianceRules_FSMA.md
│   ├── DataContracts.md
│   └── SupportPlaybook.md
│
├── n8n
│   ├── exports
│   └── templates
│       └── README.md
│
├── skills
│   ├── analyze_ticket.md
│   ├── build_n8n_workflow.md
│   └── generate_compliance_advice.md
│
├── tests
│
├── tools
│   └── tool_registry.yaml
│
└── python
    ├── scripts
    ├── tools
    ├── ai-guides
    ├── automation-scripts
    └── prompting-library
        └── claude_prompt_structure.md
```

# Technology Stack


## Agents

The `agents` folder contains higher-level AI roles.

These agents orchestrate skills, memory files and workflows for specific business use cases.

Examples:

- `compliance-agent.md` → compliance reasoning and advisory support
- `advisory-agent.md` → financial advisory workflow support
- `support-agent.md` → ticket analysis and support automation

## Skills

The `skills` folder contains reusable AI task descriptions.

Skills are smaller capabilities that can be used by different agents.
---

# Technology Stack

## Application

Backend  
Ruby on Rails

Frontend  
React

Database  
MongoDB

Infrastructure  
AWS

Automation  
n8n

---

## AI Tooling

The repository supports collaboration between different AI systems.

Primary orchestrator  
Claude Code

Development assistant  
OpenAI Codex / ChatGPT

Editor assistant  
GitHub Copilot

---

# Data and Integrations

MyFaro follows an **API-first architecture**.

The platform integrates with the systems used by financial advisors in order to reduce duplicate data entry and support end-to-end advisory workflows.

Data sources include:

Internal
- MongoDB (application data)
- Funds database (product information)

External APIs
- Infront API
- Creditsafe API
- CRM APIs
- insurer APIs

HTML imports
- MyPension
- MyMinFin
- MyCareer

---

# Document Storage

Documents are stored in Microsoft 365 SharePoint.

Two environments exist.

Client environment  
myfaro-client

Used for:

- client documentation
- advisory documents
- object related files

Company environment  
myfaro-general

Used for:

- internal documents
- sales documents
- marketing materials
- contracts and licensing agreements

MongoDB stores structured advisory data while SharePoint stores documents.

---

# Operational Systems

Some operational workflows rely on external tools.

HubSpot  
Used by MyFaro for CRM and go-to-market activities.

Zoho  
Used for support ticket management.

These systems are part of the operational ecosystem but are not core components of the MyFaro application.

---

# Purpose of this Repository

The AI-OS repository allows:

- structured AI collaboration
- reusable workflows
- documented advisory processes
- automation design
- knowledge reuse

The objective is to **augment financial advisors with AI tools while keeping humans in control of decisions.**