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
