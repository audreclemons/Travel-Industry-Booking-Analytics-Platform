# Travel Industry Booking Analytics Platform

![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)



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

## 🛠️ Tech Stack

- **Languages**: Python, SQL
- **Cloud**: AWS
- **Services**:
  - Lambda
  - S3
  - Glue
  - Athena
  - API Gateway
  - ECS (Airflow)
  - DynamoDB
  - Bedrock
- **Infrastructure**: Terraform
- **CI/CD**: CodeBuild

---


## ✅ Project Completion Status


### ✅ Sprint 1: Foundation & Infrastructure
- Terraform infrastructure deployed (state files present)
- Core AWS resources operational
- Data lake foundation established

**Status:** Complete

---

### ✅ Sprint 2: Data Ingestion Layer
- Lambda ingestion function created and packaged (`lambda_ingest.zip`)
- API Gateway configured and integrated
- Ingestion and landing-zone validation scripts implemented

**Status:** Complete

---

### ✅ Sprint 3: ETL & Data Transformation
- Raw → Curated Glue ETL job implemented (`booking_etl.py`)
- Curated → Analytics ETL job implemented (`analytics_etl.py`)
- Schema documentation created

**Status:** Complete

---

### ✅ Sprint 4: Orchestration & Automation
- Airflow DAG completed and deployed
- Dockerized Airflow environment configured
- Deployment scripts and CodeBuild CI/CD configuration in place

**Status:** Complete

---

### ✅ Sprint 5: Analytics & AI Integration
- Athena SQL analytics queries created
- All three AI chatbot implementations present
- AWS Bedrock infrastructure deployed

**Status:** Complete

---

### ✅ Sprint 6: Monitoring, Testing & Documentation
- KPI and pipeline monitoring configurations created
- Synthetic data generator implemented
- Test suite and validation framework completed
- Full documentation set delivered

**Status:** Complete

---

## 🚀 Overall Project Status

**100% Complete — Production Ready**

All deliverables across all six sprints are present in the codebase, with infrastructure successfully deployed and verified via Terraform state files. The platform is fully operational, end-to-end, from ingestion through analytics and AI-powered insights.

---

## 🔮 Future Enhancements

- Multi-currency FX normalization
- Bedrock Knowledge Base integration
- Row-level security by advisor
- Streaming ingestion (Kinesis)
- Advanced AI recommendations

---

## 📄 License

This project is licensed under the **MIT License**.

The MIT License was chosen to:
- Clearly define how the code can be used
- Allow review, reuse, and modification with attribution
- Make the project safe to share publicly as a portfolio example
- Align with common open-source and industry practices




