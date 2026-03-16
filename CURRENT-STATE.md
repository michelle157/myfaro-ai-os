**There is a lot of duplication of info here from CONTEXT.md - potentially conflicting as data is corrected in one or the other**

# Current State of the MyFaro Platform

This document describes the current operational and technical state of the MyFaro platform.

The objective is to provide AI systems and developers with an accurate view of how the platform operates today.


---

# Platform Overview

MyFaro is a financial advisory enablement platform that aggregates financial data and supports advisors in delivering structured advice.

The platform connects to multiple external systems and provides a consolidated environment where advisors can work with client financial information.

The system is built to support **AI-assisted advisory workflows**, while maintaining human supervision.

---

# Core Technology Stack

## Backend
Ruby on Rails

## Frontend
React

## Database
MongoDB

MongoDB is the primary application database and stores structured platform data such as:

• client profiles  
• financial objects  
• advisory calculations  
• product references  

---

# Infrastructure

The platform is hosted on:

AWS

Infrastructure supports:

• application hosting  
• API integrations  
• automation workflows  
• database operations  

---

# Automation Layer

Automation workflows are currently implemented using:

n8n

These workflows are used to automate operational processes and system integrations.

Examples include:

• data synchronisation  
• process automation  
• system orchestration

---

# Document Storage

Documents are not stored in MongoDB.

Instead, documents are stored in **Microsoft SharePoint environments**.

Two SharePoint environments are used.

## myfaro-client

Stores documents related to end-clients.

Examples include:

• client documents  
• advisory reports  
• financial documentation  
• uploaded supporting documents  

The document hierarchy mirrors the object structure used in MyFaro.

## myfaro-general

Stores internal MyFaro company documents.

Examples include:

• contracts  
• proposals  
• licensing agreements  
• sales documents  
• internal documentation  

These documents are unrelated to end-client financial data.

---

# Data Aggregation Mechanisms

MyFaro aggregates financial data through multiple mechanisms.

## API Integrations

When possible, data is retrieved through APIs.

Examples include:

• Infront API (financial market data)  
• Creditsafe API (company information)

Additional integrations with insurers and financial institutions may be implemented where APIs are available.

---

## Government Data Sources

Financial data can be retrieved from several government portals.

Examples include:

• MyPension  
• MyMinFin  
• MyCareer  

These integrations currently rely on **HTML ingestion modules** developed internally.

---

## CSV Data Aggregation

Not all financial data sources provide APIs.

To solve this, MyFaro includes a **CSV-based data ingestion mechanism**.

Financial advisors can upload portfolio data files which are processed through a validation pipeline.

The system:

• validates file structure  
• checks data consistency  
• maps fields to the internal data model  
• imports data into MongoDB  

This mechanism is commonly used when importing portfolio data from insurers or legacy systems.

---

# CRM Integration

MyFaro is designed to be **CRM agnostic**.

Financial advisors operate with a variety of CRM systems.

Examples include:

• BrokerCloud  
• Brio  
• HubSpot  
• other sector-specific CRMs  

MyFaro integrates with CRM systems through APIs whenever possible.

Example:

B-Sure uses **HubSpot CRM**, which currently has a push/pull API integration with MyFaro for selected fields.

However, HubSpot is not the default CRM for MyFaro users.

---

# Sales Operations

Sales and go-to-market activities are currently managed through:

HubSpot CRM

HubSpot is used for:

• lead management  
• sales pipeline management  
• marketing campaigns  
• onboarding processes

---

# Customer Success Operations

Customer success activities are coordinated using:

Microsoft Planner

Planner is used to track:

• onboarding tasks  
• implementation steps  
• customer follow-up actions  
• operational workflows

---

# Support Operations

The MyFaro support desk currently operates in:

Zoho

Zoho is used for:

• support ticket management  
• issue tracking  
• customer support communication

Future automation may integrate ticket workflows into AI-assisted processes.

---

# AI Development Workspace

The MyFaro team has created an internal **AI workspace repository** called:

MyFaro AI-OS

This repository provides a structured environment for:

• AI collaboration  
• workflow design  
• knowledge storage  
• automation development

The repository is designed so that both humans and AI systems can operate within the same structured knowledge base.

---

# AI Use Cases Under Development

The first AI-assisted workflows currently under exploration include:

### Support Ticket Analysis

AI agents assist in analysing support tickets and suggesting responses.

### Compliance Assistance

AI helps generate structured compliance suggestions for advisors.

### Workflow Automation

AI systems may trigger automation workflows through the automation layer.

---

# AI Development Tools

The team currently uses multiple AI systems for development.

These include:

• Claude Code  
• OpenAI Codex / ChatGPT  
• GitHub Copilot  

Each AI system reads the same repository structure but uses different instruction files.

---

# Repository Role

The MyFaro AI-OS repository acts as the **shared knowledge and workflow environment** used by both developers and AI systems.

It contains:

• architecture documentation  
• domain knowledge  
• reusable AI skills  
• automation workflows

This repository serves as the foundation for building AI-assisted workflows within MyFaro.
