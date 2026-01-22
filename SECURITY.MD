# Security Policy

## 🔐 Overview

The **Travel Industry Booking Analytics Platform** is a portfolio and learning project designed to demonstrate secure, cloud-native data engineering and AI integration practices using AWS services.

Security is treated as a first-class concern across infrastructure, data ingestion, processing, analytics, and AI components.

---

## 📌 Supported Versions

This repository is a **demonstration project** and does not publish versioned production releases.

| Version | Supported |
|--------|-----------|
| Main branch | ✅ Yes |

---

## 🔎 Security Design Principles

The platform follows these core security principles:

- **Least privilege IAM** for all AWS services
- **No secrets stored in code**
- **Schema and input validation at ingestion**
- **Separation of RAW, CURATED, and ANALYTICS data**
- **AI queries restricted to curated datasets only**
- **Infrastructure defined and auditable via Terraform**

---

## 🛡️ Data Security

### Data Handling
- RAW data is stored **immutably** in Amazon S3
- CURATED and ANALYTICS datasets are derived via controlled ETL jobs
- No personally identifiable information (PII) is intentionally included
- Synthetic data is used for testing and demonstration

### Access Control
- IAM roles scoped per service (Lambda, Glue, ECS, Bedrock)
- S3 access restricted by prefix and role
- API Gateway enforces controlled entry points

---

## 🤖 AI Security (AWS Bedrock)

AI capabilities follow strict boundaries:
- Bedrock is invoked via Lambda only
- Prompts are grounded in **curated analytics data**
- RAW event data is never directly exposed to AI
- No model fine-tuning with sensitive data

---

## 🚨 Reporting a Vulnerability

If you discover a potential security issue:

1. **Do not** open a public GitHub issue
2. Contact the repository owner directly:
   - **GitHub:** @audreclemons
3. Provide:
   - Description of the issue
   - Steps to reproduce (if applicable)
   - Potential impact assessment

Reasonable time will be taken to review and address reports.

---

## 🚫 Out of Scope

The following are considered out of scope for vulnerability reporting:
- Issues related to synthetic test data
- AWS service-side vulnerabilities
- Misconfigurations in personal forks or local environments

---

## 📄 Disclaimer

This project is provided **as-is** for educational and portfolio purposes.  
It is not intended for direct production use without additional security hardening, governance, and compliance review.

---

## 🏁 Acknowledgements

Security best practices are informed by:
- AWS Well-Architected Framework (Security Pillar)
- Industry-standard cloud security patterns
- Prior security-focused projects (e.g., ChocoQA)
