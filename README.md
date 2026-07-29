# ZeroCarbon | Enterprise GHG Accounting & Automated BRSR Platform

<div align="center">

  <img src="https://raw.githubusercontent.com/zerocarbon-org/.github/main/assets/banner.png" alt="ZeroCarbon - Automated Carbon Accounting & BRSR Compliance Platform" width="100%" style="border-radius: 10px;" />

  <br /><br />

  [![License: MIT](https://img.shields.io/badge/License-MIT-000000.svg?style=for-the-badge&logo=opensourceinitiative&logoColor=white)](https://opensource.org/licenses/MIT)
  [![Build Status](https://img.shields.io/badge/Build-Passing-1E293B?style=for-the-badge&logo=githubactions&logoColor=white)](https://github.com/zerocarbon-org/zerocarbon/actions)
  [![Security Audit](https://img.shields.io/badge/Security-SOC2_Type_II-0F172A?style=for-the-badge&logo=shield&logoColor=white)](#-security--privacy)
  [![BRSR Core](https://img.shields.io/badge/BRSR-SEBI_Compliant-047857?style=for-the-badge&logo=leaf&logoColor=white)](#-brsr-automation)
  [![PRs Welcome](https://img.shields.io/badge/PRs-Welcome-0F172A?style=for-the-badge&logo=github&logoColor=white)](#-contribution-guide)

  <br />

  ### **Autonomous GHG Protocol Accounting, Scope 3 Supply Chain Intelligence & Regulatory ESG Reporting**

  *An enterprise-grade, open-core software platform designed to automate Scope 1, Scope 2, and Scope 3 greenhouse gas calculations, streamline mandatory SEBI BRSR Core disclosures, and optimize supply chain decarbonization.*

  <br />

  <a href="https://zerocarbon.org.in"><strong>Platform Overview »</strong></a> ·
  <a href="https://docs.zerocarbon.org.in"><strong>Documentation »</strong></a> ·
  <a href="https://zerocarbon.org.in/demo"><strong>Schedule Enterprise Demo »</strong></a>

  <br /><br />

  ```bash
  # Quick Launch ZeroCarbon Core via Docker
  docker run -d -p 8080:8080 --name zerocarbon-core zerocarbon/engine:latest
  ```

</div>

---

## 🎯 Platform Overview

ZeroCarbon is an autonomous corporate carbon accounting and regulatory ESG reporting platform built for enterprise supply chains, sustainability officers, and compliance leads. Designed to eliminate manual data entry and fragmented spreadsheets, ZeroCarbon integrates directly with enterprise ERP systems (SAP, Oracle, NetSuite), smart utility meters, and vendor logistics channels to generate real-time, audit-grade carbon inventories.

Engineered with complete alignment to GHG Protocol, SEBI BRSR Core, GRI, CSRD, and ISO 14064 frameworks, ZeroCarbon enables organizations to measure, track, and report Scope 1, 2, and 3 emissions with continuous mathematical precision.

---

## 🚀 Quick Start & Deployment

Launch the production stack via Docker Compose:

```yaml
version: '3.8'

services:
  zerocarbon-core:
    image: zerocarbon/core:latest
    ports:
      - "3000:3000"
    environment:
      - NODE_ENV=production
      - DATABASE_URL=postgresql://zerocarbon:secret@db:5432/zerocarbon_db
      - REDIS_URL=redis://cache:6379
    depends_on:
      - db
      - cache

  zerocarbon-ai:
    image: zerocarbon/ai-engine:latest
    ports:
      - "8000:8000"
    environment:
      - EMBEDDING_MODEL=text-embedding-3-small
      - VECTOR_DB_HOST=qdrant

  db:
    image: postgres:16-alpine
    environment:
      POSTGRES_USER: zerocarbon
      POSTGRES_PASSWORD: secret
      POSTGRES_DB: zerocarbon_db
    volumes:
      - pgdata:/var/lib/postgresql/data

  cache:
    image: redis:7-alpine

volumes:
  pgdata:
```

```bash
docker-compose up -d
```

---

## 📈 Mission & Vision

- **Mission:** Deliver seamless, audit-ready carbon intelligence software that enables enterprises to quantify, track, and lower their global carbon footprint automatically.
- **Vision:** Serve as the core software infrastructure powering net-zero transformation and regulatory ESG compliance across global supply chains.

---

## 🌱 Enterprise Benchmarking

| Feature / Metric              | Legacy Manual Spreadsheets      | Generic ESG Dashboards          | ZeroCarbon Engine                                      |
|-------------------------------|---------------------------------|---------------------------------|--------------------------------------------------------|
| Data Ingestion                | Manual CSV & batch entry        | Static file uploads             | Real-time REST APIs & ERP Connectors                   |
| Scope 3 Decarbonization       | Spend-based rough estimates     | Basic static surveys            | AI Factor Mapping & Multi-Tier Vendor Portals          |
| Audit Compliance              | High risk of human error        | Black-box calculations          | Auditable calculation ledger & SOC2 governance         |
| Regulatory Frameworks         | Disconnected manual templates   | Rigid annual templates          | Dynamic BRSR Core, GRI, TCFD, & XBRL reporting         |
| Architecture                  | Proprietary static files        | Proprietary lock-in             | Open-core, self-hostable microservice ecosystem        |

---

## 📊 Platform Impact

<div align="center">

| ⚡ 99.8%                          | 🍃 12M+ tCO₂e                     | 🏢 100+                           | 🔒 100%                           |
|----------------------------------|-----------------------------------|-----------------------------------|-----------------------------------|
| Automated Factor Matching Accuracy | Enterprise Carbon Quantified    | Connected Supply Chains           | SOC2 & Audit Compliant            |

</div>

---

## 🤖 Core Platform Features

### 1. ♻️ Comprehensive GHG Accounting (Scope 1, 2, & 3)

- **Scope 1 (Direct Emissions):** Fleet tracking, stationary fuel combustion, process emissions, and fugitive refrigerant monitoring.
- **Scope 2 (Indirect Energy Emissions):** Dual-reporting calculation engine supporting location-based and market-based power grid metrics (including CEA India grid intensity factors).
- **Scope 3 (Value Chain Emissions):** Full coverage across Purchased Goods & Services, Freight & Logistics, Waste Management, Business Travel, and Employee Commute.

### 2. 📄 Automated SEBI BRSR & Regulatory ESG Reporting

- **SEBI BRSR Core:** Pre-configured calculation pipelines mapped directly to mandatory Indian market regulatory guidelines.
- **Global Standard Cross-Walk:** Automatically maps environmental metrics across GRI, TCFD, CDP, and EU CSRD reporting frameworks.
- **One-Click Audit Exports:** Instantly generate verified PDF calculation sheets, structured Excel ledgers, and digital XBRL reporting outputs.

### 3. 🤖 AI-Powered Invoice Parsing & Emission Factor Lookup

- **Automated Document Parsing:** Advanced OCR parses vendor invoices, utility receipts, and freight bills to extract energy and activity data (kWh, liters, metric tons).
- **Dynamic Factor Matching:** Machine learning engine maps unstructured line items to validated global emission factor databases (DEFRA, IPCC, US EPA, CEA).
- **Anomaly & Leakage Detection:** Automated monitoring alerts sustainability managers to missing receipts, data input spikes, and potential accounting gaps.

---

## 🏗 Enterprise Architecture

```mermaid
graph TD
    classDef data fill:#1E293B,stroke:#475569,stroke-width:1px,color:#F8FAFC;
    classDef core fill:#0F172A,stroke:#334155,stroke-width:1.5px,color:#F8FAFC;
    classDef output fill:#047857,stroke:#10B981,stroke-width:1px,color:#FFFFFF;

    subgraph Ingestion ["Data Integration Layer"]
        A[ERP Systems: SAP / Oracle / NetSuite] ::: data
        B[IoT Utility Meters & Gateways] ::: data
        C[Vendor Invoices, Bills & Logistics PDFs] ::: data
    end

    subgraph CoreEngine ["ZeroCarbon Calculation Core"]
        D[API Gateway & Auth Service] ::: core
        E[Data Parser & Pipeline Manager] ::: core
        F[AI Emission Factor Matcher] ::: core
        G[Scope 1, 2, 3 Calculation Engine] ::: core
        H[Auditable Ledger Database] ::: core
    end

    subgraph Outputs ["Regulatory & Enterprise Outputs"]
        I[SEBI BRSR Core PDF/XBRL Reports] ::: output
        J[Executive Carbon Analytics Dashboard] ::: output
        K[Third-Party Audit Export Logs] ::: output
    end

    A --> D
    B --> D
    C --> D
    D --> E
    E --> F
    F --> G
    G --> H
    H --> I
    H --> J
    H --> K
```

---

## 📦 Repository Architecture

- **zerocarbon-core** — Main application server, calculation engine, user authentication, and Postgres schema.
- **zerocarbon-ai** — OCR invoice extraction service, emission factor vector search, and anomaly detection services.
- **zerocarbon-docs** — Enterprise documentation site, API integration guides, and developer tutorials.

---

## 🛠 Technology Stack

| Layer                  | Technologies                                      |
|------------------------|---------------------------------------------------|
| Frontend               | Next.js (TypeScript), TailwindCSS, Shadcn UI, Recharts |
| Backend Services       | Node.js / Express, Python (FastAPI Engine)        |
| Database & Storage     | PostgreSQL (Prisma ORM), Redis, Qdrant Vector Search |
| AI & Machine Learning  | PyTorch, OCR Vision Pipeline, LangChain           |
| Infrastructure & CI/CD | Docker, Kubernetes, Helm, GitHub Actions          |

---

## 🔒 Security & Data Privacy

- **Multi-Tenant Data Isolation:** Logical and schema-level data segregation ensures tenant isolation.
- **Enterprise Encryption:** AES-256 encryption at rest and TLS 1.3 data transfer protocols.
- **Role-Based Access Control (RBAC):** Configurable permissions across data entry operators, sustainability managers, executive leadership, and independent third-party auditors.
- **Compliance Standards:** Built to align with SOC2 Type II security principles and ISO 27001 data governance practices.

---

## 🗺 Platform Roadmap

- [x] **Core GHG Engine:** Scope 1 & Scope 2 calculation engine setup with regional grid emission factor libraries.
- [x] **BRSR Compliance:** Pre-built SEBI BRSR Core regulatory reporting templates and export tools.
- [ ] **AI Ingestion:** Invoice OCR parsing pipeline & multi-tenant Scope 3 vendor engagement portal.
- [ ] **IoT & Carbon Offset Ledger:** Real-time IoT meter connectors and carbon offset verification ledger.

---

## 🤝 Contribution Guide

We welcome contributions from software developers, climate tech researchers, and environmental engineers!

1. Fork the Repository
2. Create a Feature Branch: `git checkout -b feature/cea-grid-factors`
3. Commit Your Changes: `git commit -m 'feat: Update CEA grid emission factors'`
4. Push to the Branch: `git push origin feature/cea-grid-factors`
5. Open a Pull Request: Submit your PR against the `main` branch with detailed implementation notes.

---

## 📫 Contact & Resources

<div align="center">

**[Website](https://zerocarbon.org.in)** · **[LinkedIn](https://linkedin.com)** · **[Email Us](mailto:hello@zerocarbon.org.in)**

<br />

*Automating global enterprise decarbonization & compliance.*

<br />

© 2026 ZeroCarbon Tech. All rights reserved.

