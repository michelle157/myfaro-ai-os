# MyFaro Data Flows

This document describes how data flows through the MyFaro platform.

Understanding these flows is important for developers and AI systems interacting with the MyFaro architecture.

MyFaro acts as a **data aggregation and advisory enablement platform** that orchestrates data between multiple systems and enriches advisory workflows.

---

# High-Level Data Flow

At a high level, MyFaro acts as the central orchestration platform between:

- advisors  
- external data providers  
- CRM systems  
- document storage  
- automation workflows  
- AI enrichment services  

```
External Systems
        ↓
   MyFaro APIs
        ↓
      MongoDB
        ↓
   MyFaro Workflows
        ↓
 Advisor Interface
```

MyFaro remains the **central system where advisory workflows take place**.

---

# CRM Data Flow

Financial advisors typically operate with their own CRM systems.

MyFaro is designed to integrate with these systems rather than replace them.

Examples of CRM systems include:

- BrokerCloud  
- Brio  
- HubSpot  

Example flow:

```
CRM System
     ↓
CRM API Integration
     ↓
MyFaro Backend
     ↓
MongoDB
     ↓
Advisor Workflows
```

CRM systems remain the system of record for relationship management, while MyFaro supports advisory workflows.

---

# External API Data Flow

MyFaro retrieves financial and company information from multiple external APIs.

Examples include:

- Infront (financial market data)  
- Creditsafe (company information)  
- CompanyWeb (company registry information)

Example flow:

```
External API
     ↓
Integration Layer
     ↓
MyFaro Backend
     ↓
MongoDB
     ↓
Advisor Interface
```

The architecture supports additional API integrations over time.

MyFaro is designed to be **API-first**, allowing integration with additional external systems used by financial advisors.

---

# Government Data Flow

Some financial data is retrieved from government portals.

Examples include:

- MyPension  
- MyMinFin  
- MyCareer  

These integrations rely on HTML ingestion modules developed within MyFaro.

Example flow:

```
Government Portal
       ↓
HTML Extraction Module
       ↓
MyFaro Backend
       ↓
MongoDB
       ↓
Advisor Interface
```

---

# CSV Portfolio Import Flow

Not all financial institutions provide APIs.

MyFaro therefore supports CSV-based portfolio ingestion.

Advisors can upload structured CSV files exported from external systems.

Example flow:

```
CSV Upload
     ↓
Validation Pipeline
     ↓
Field Mapping
     ↓
MongoDB
     ↓
Advisor Interface
```

The validation pipeline performs:

- file structure validation  
- data consistency checks  
- mapping to the MyFaro data model  

This allows advisors to import portfolio data even when no direct API integration exists.

---

# Document Storage Flow

Documents are stored in SharePoint rather than inside MongoDB.

Example flow:

```
Advisor Upload
      ↓
MyFaro Backend
      ↓
SharePoint
      ↓
Document Reference stored in MongoDB
```

SharePoint environments used by MyFaro:

- **myfaro-client**  
  Client and portfolio related documents.

- **myfaro-general**  
  Internal MyFaro documents such as contracts, sales documents and operational files.

MongoDB stores references to these documents rather than the documents themselves.

---

# AI Enrichment Flow

AI services analyse MyFaro data and generate structured suggestions that are reintroduced into the MyFaro platform.

AI therefore acts as an **enrichment layer within the MyFaro ecosystem**, not as a standalone advisory system.

Example flow:

```
MyFaro Data
     ↓
AI Analysis
     ↓
AI Generated Suggestions
     ↓
MyFaro Workflow Engine
     ↓
Advisor Review
```

AI suggestions may include:

- compliance observations  
- advisory insights  
- portfolio suggestions  
- workflow assistance  

These suggestions become visible inside MyFaro where advisors can review them.

Final decisions always remain with the human advisor.

---

# Compliance Workflow Flow

One important use case for AI enrichment is compliance support.

Example flow:

```
Client Data
Portfolio Data
Product Data
      ↓
AI Compliance Analysis
      ↓
Compliance Suggestions
      ↓
MyFaro Compliance Workflow
      ↓
Advisor Validation
```

This allows AI to assist advisors while keeping the advisor responsible for final compliance decisions.

---

# Automation Data Flow

Automation workflows are orchestrated using **n8n**.

Example flow:

```
System Event
      ↓
n8n Workflow
      ↓
External API / Database
      ↓
Process Completion
```

Automation workflows can:

- synchronise data  
- trigger operational workflows  
- update systems  

Automation remains loosely coupled from the core application.

---

# Summary

MyFaro acts as a **central orchestration platform for advisory workflows**.

Data enters the platform through:

- APIs  
- CSV ingestion  
- HTML extraction modules  

Data is stored in:

- MongoDB (structured application data)  
- SharePoint (documents)

AI services analyse MyFaro data and generate **structured advisory suggestions that are fed back into MyFaro workflows**.

Advisors remain responsible for reviewing these suggestions and making final decisions.