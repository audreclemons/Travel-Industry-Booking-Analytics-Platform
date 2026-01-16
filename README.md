# Travel Industry Booking Analytics Platform

An end-to-end, event-driven data engineering platform that ingests travel booking events, curates analytics-ready datasets, enforces data quality, and delivers AI-powered insights using AWS Bedrock.

This project demonstrates **production-grade data engineering**, **cloud-native architecture**, and **responsible AI integration** applied to a realistic travel industry use case.

---

## 🚀 Overview

The Travel Industry Booking Analytics Platform simulates a modern travel booking ecosystem where booking data arrives from multiple sources (web forms, advisor tools, partner systems, synthetic generators).  
Data is processed through a **RAW → CURATED → ANALYTICS** pipeline and made accessible through dashboards and a **natural language AI chatbot**.

The platform is designed to emphasize:
- Data lineage and traceability
- Analytics-ready transformations
- Data quality enforcement
- AI grounded on curated data (not raw events)

---

## 🏗️ Architecture (High Level)

**Data Flow**

INGEST → CURATE → VALIDATE → ANALYZE
↓ ↓ ↓ ↓
Lambda Glue Python Athena / AI
↓ ↓ ↓ ↓
Raw Data → Curated → Quality → Insight



**Core Components**
- **Ingestion**: API Gateway + Lambda
- **Storage**: S3 Data Lake (raw / curated)
- **Processing**: AWS Glue ETL
- **Orchestration**: Apache Airflow (ECS)
- **Analytics**: Athena SQL
- **AI**: AWS Bedrock (Lambda-based chatbot)
- **Infrastructure**: Terraform (IaC)
- **CI/CD**: AWS CodeBuild

---

## 📥 Data Ingestion

### Supported Sources
- Web forms (client travel requests)
- Advisor tools (status updates, pricing)
- Partner systems (simulated APIs/files)
- Synthetic data generator (testing & scale)

Each ingestion event:
- Is schema-tolerant
- Includes `source_system`
- Is stored unchanged in the **RAW landing zone**

---

## 🧱 Data Layers

### RAW Layer
- Stores events exactly as received
- Minimal validation
- Preserves source-of-truth
- Optimized for traceability and replay

### CURATED Layer
- Standardized timestamps and data types
- Normalized booking statuses
- Enriched fields (country, traveler segment)
- Derived metrics (trip duration, cost per traveler)
- Data quality flags (`is_valid_record`, `dq_issue`)

### ANALYTICS Layer
- KPI-ready datasets
- Funnel analysis
- Revenue and conversion metrics
- Optimized for dashboards and AI queries

---

## 🧠 AI Chat (AWS Bedrock)

The platform includes a **Travel Advisor AI Chatbot** built with AWS Bedrock and Lambda.

### Key Principles
- AI queries **only curated data**
- No hallucination from raw events
- Business logic enforced before AI reasoning

### Example Questions
- “Show UK bookings for couples under $2,500”
- “Which destinations convert best this month?”
- “Compare Ghana vs South Africa average booking value”
- “Summarize low-cost options and recommend next steps”

---

## 🧪 Data Quality & Validation

Validation is treated as a first-class concern:
- Landing zone validation scripts
- Schema checks for required fields
- Source system enforcement
- Record-level quality flags
- Pipeline-level metrics

---

## ⚙️ Repository Structure

travel-industry-booking-analytics/
├── ingestion/ # Lambda ingestion + validation
├── glue/ # ETL transformations
├── sql/ # Athena analytics queries
├── ai_chat/ # Bedrock chatbot logic
├── airflow/ # DAGs & orchestration
├── data/ # Synthetic data generation
├── dashboards/ # KPI & monitoring configs
├── infrastructure/ # Terraform IaC
├── tests/ # Validation & tests
├── buildspec.yml # CI/CD
└── README.md
