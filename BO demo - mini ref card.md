# 🧾 Mini Reference Card: Step 1.1 — Receive Pooling Data from System B

## 🧩 Why This Matters
Ensuring the accurate and timely ingestion of loan pool data from System B into System A is critical for enabling compliant trade creation, reducing operational risk, and avoiding downstream delays.  
(⚙️ Operational Efficiency, ⚖️ Legal / Risk / Compliance)

## 🧾 Step Overview
| Field | Description |
|-------|-------------|
| **Step Name** | Step 1.1: Receive Pooling Data from System B |
| **Business Process** | Stage 1: Trade Creation |
| **Step Type** | Validation |
| **Technical Function** | System A receives batch files from System B, parses structured loan pool data, and stores results in internal tables for further processing. |
| **Business Purpose** | Ensures Business Unit A has accurate and timely loan pool data to support trade creation, compliance validation, and operational readiness. |
| **Key Personas** | - Business Unit A analysts <br> - Trade operations team <br> - Compliance officers |

## 🔍 Customer Goal
- Gain early access to complete and accurate loan pool data
- Ensure readiness for trade evaluation and compliance reviews

## 📈 KPIs (Business Outcomes — What Success Should Look Like)
| KPI | Target | Description | Owner |
|-----|--------|-------------|-------|
| Pool File Availability SLA | 100% | System B pool files must be available in System A within 30 minutes of receipt | Product Owner / Data Analyst |

## 📊 Observability Signals (Business, Process, and System Telemetry)

### About the Signals Below

Each signal in the table below reflects a different layer of observability:

- **🟦 Business Signals** reflect value delivery and desired business outcomes.
- **🟨 Process Signals** reflect correct execution of system or business logic.
- **🟧 System Signals** reflect the infrastructure, platform, or service health needed to support the step.

Together, these help answer:  
**“How do we know this step is working as intended — from both a business and technical perspective?”**

| Type | Signal | Owner |
|------|--------|-------|
| 🟦 Business Signal | Percent of pool files ingested within SLA | Product Owner |
| 🟦 Business Signal | Total loan records processed from batch files | Product Owner |
| 🟨 Process Signal | Validation pass rate for required pool data fields (e.g., loan count, timestamps, field format) | Application Developer |
| 🟨 Process Signal | File completeness confirmation logic executed | Application Developer |
| 🟧 System Signal | System A ingestion job latency (p95) | Platform SRE |
| 🟧 System Signal | System B delivery job success/failure ratio | Platform SRE |
| 🟧 System Signal | Batch file processing error count | Platform SRE |

## 🔔 Common Alerts
- ⚠ SLA breach: Pool files not available in System A within 30 minutes
- ⚠ Validation failure: Missing or incorrectly formatted pool fields
- ⚠ Ingestion latency exceeded: Processing time above 2s threshold

## ✅ Responsibility Table: Next Actions
| Condition | Action | Responsible Role |
|-----------|--------|------------------|
| Pool file SLA breach | Investigate System B delivery logs and System A ingestion job status | Platform SRE |
| Validation failures detected | Notify Application Dev and Business Ops to correct source format or schema | Application Developer / Product Owner |
| Batch job ingestion errors | Retry ingestion or escalate to platform support | Platform SRE |
