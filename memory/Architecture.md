# MyFaro Platform Architecture

This document describes the high-level architecture of the MyFaro platform and the surrounding ecosystem.

It provides technical context for developers and AI systems interacting with the MyFaro AI-OS workspace.

---

# Platform Overview

MyFaro is a financial advisory enablement platform that aggregates financial data from multiple sources and provides advisors with tools to support structured financial advice.

The platform combines:

• internal data models  
• external data integrations  
• document storage  
• automation workflows  
• AI-assisted processes  

The goal is to create a connected advisory ecosystem.

---

# Core Application Architecture

The MyFaro application consists of three primary layers.

## Frontend

Technology:
React

Responsibilities:

• user interface  
• advisor workflows  
• data visualisation  
• client dashboards  
• data entry interfaces  

The frontend communicates with the backend through application APIs.

---

## Backend

Technology:
Ruby on Rails

Responsibilities:

• business logic  
• API endpoints  
• data orchestration  
• integration with external systems  
• workflow coordination  

The backend acts as the central orchestration layer of the platform.

---

## Database Layer

Technology:
MongoDB

MongoDB stores structured application data.

Examples include:

• client profiles  
• financial objects  
• portfolio data  
• advisory calculations  
• product references  

MongoDB acts as the primary structured data layer of the platform.

---

# Document Architecture

Documents are not stored inside MongoDB.

Instead, documents are stored in Microsoft SharePoint environments.

This separation improves scalability and document management.

## SharePoint Environment: myfaro-client

Stores documents related to end-clients.

Examples:

• advisory reports  
• financial documents  
• uploaded client documentation  
• supporting files for advisory objects  

The folder hierarchy mirrors MyFaro object structures.

---

## SharePoint Environment: myfaro-general

Stores internal MyFaro documents.

Examples:

• proposals  
• contracts  
• licensing agreements  
• marketing materials  
• internal documentation  

These documents are not related to client financial data.

---

# External Data Ecosystem

MyFaro integrates with multiple external systems through APIs.

The platform is designed to remain flexible and integrate with additional data providers when useful.

These integrations reduce manual data entry and enrich advisory workflows.

Examples of currently used or planned integrations include:

## Financial Market Data

Infront API

Provides:

• financial market data  
• fund information  
• financial product data  

This data feeds the internal product database used in advisory workflows.

---

## Company Information

Creditsafe API

Provides:

• company registry data  
• credit information  
• due diligence data  

Used for compliance and advisory processes.

---

CompanyWeb API

Provides:

• company registry information  
• shareholder structures  
• company financial data  

This information may be used in due diligence and advisory workflows.

---

## Government Data Sources

Financial information may be retrieved from government portals.

Examples include:

• MyPension  
• MyMinFin  
• MyCareer  

These integrations currently rely on HTML ingestion modules built internally.

---

## Additional API Integrations

MyFaro is designed to connect to additional APIs where relevant.

Examples may include:

• insurance company APIs  
• CRM systems  
• financial data providers  
• portfolio data providers  

The platform architecture allows new integrations to be added without disrupting the core system.

---

# CRM Integration Architecture

MyFaro is designed to be CRM agnostic.

Financial advisors use a variety of CRM systems.

Examples include:

• BrokerCloud  
• Brio  
• HubSpot  

MyFaro integrates with CRM systems through APIs.

Example:

B-Sure currently uses HubSpot CRM which exchanges selected fields with MyFaro.

CRM systems are not replaced by MyFaro but connected to it.

---

# Portfolio Data Aggregation

Not all data providers offer APIs.

MyFaro therefore supports CSV-based portfolio ingestion.

Advisors can upload structured CSV files containing portfolio information.

The ingestion pipeline performs:

• structural validation  
• data mapping  
• consistency checks  
• database ingestion

This mechanism allows portfolio data to be imported when direct integrations are unavailable.

---

# Automation Architecture

Automation workflows are implemented using:

n8n

n8n orchestrates:

• system integrations  
• workflow automation  
• operational processes  

Examples include:

• data synchronisation  
• process automation  
• system triggers

Automation workflows remain loosely coupled from the core application.

---

# Operational Systems

Several operational systems support the platform.

## Support Desk

Zoho

Used for:

• support ticket management  
• issue tracking  
• customer support workflows

---

## Sales Operations

HubSpot CRM

Used for:

• lead management  
• pipeline management  
• marketing campaigns

---

## Customer Success

Microsoft Planner

Used to coordinate:

• onboarding processes  
• implementation tasks  
• customer follow-ups

---

# AI Architecture

MyFaro is building an AI-assisted advisory environment.

AI systems support workflows but do not replace human advisors.

Examples of AI-assisted use cases include:

• support ticket analysis  
• compliance assistance  
• advisory workflow support  
• document interpretation

---

# AI Workspace (MyFaro AI-OS)

The MyFaro AI-OS repository provides a structured workspace for AI collaboration.

The repository contains:

• domain knowledge  
• reusable AI skills  
• automation workflows  
• architecture documentation  

This environment allows both humans and AI systems to work within the same structured knowledge base.

---

# High-Level Architecture Summary

MyFaro architecture consists of the following layers.

Client Interface  
React frontend

Application Logic  
Ruby on Rails backend

Data Storage  
MongoDB

Document Storage  
SharePoint

External Data Ecosystem  
multiple APIs and government data sources

Automation Layer  
n8n workflows

Operational Systems  
CRM, support desk and planning tools

AI Collaboration Layer  
MyFaro AI-OS repository