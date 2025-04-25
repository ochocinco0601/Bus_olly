# Ownership Traceability Table — Step 1.1: Receive Pooling Data from System B

## Purpose
This table documents traceability between dashboard-observed signals, their operational owners, and their original template field definitions.

It ensures:
- ✅ Every signal has a clearly assigned owner
- ✅ Ownership is aligned with BOS Persona Role Guides
- ✅ Business observability artifacts remain auditable, scalable, and evolution-ready

## Scope
- Step: Step 1.1: Receive Pooling Data from System B  
- Business Process: Stage 1: Trade Creation  
- Step Type: Validation

This table reflects the validated ownership state as of April 25, 2025.  
🔄 Last ownership update: May 15, 2025 — System A Ingestion Job Latency ownership transitioned to Data Engineering Team.

If ownership changes occur in the future, they must be recorded in the version history to maintain traceability integrity.

---

| Observed Signal / KPI                     | Owner (Dashboard Context)     | Template Field Owner       | Confirmed in Persona Guide? |
|--------------------------------------------|--------------------------------|-----------------------------|-----------------------------|
| Percent of Pool Files Ingested Within SLA  | Product Owner                  | Product Owner               | ✅ |
| Total Loan Records Processed               | Product Owner                  | Product Owner               | ✅ |
| Validation Pass Rate (Required Fields)     | Application Developer          | Application Developer       | ✅ |
| File Completeness Check Executed           | Application Developer          | Application Developer       | ✅ |
| System A Ingestion Job Latency (p95)        | Data Engineering Team `⚠️ Updated` | Platform SRE               | ⚠️ |
| System B Delivery Job Success Rate         | Platform SRE                   | Platform SRE                | ✅ |
| Batch File Processing Error Count          | Platform SRE                   | Platform SRE                | ✅ |

---

## 📌 Ownership Change Notes

- **System A Ingestion Job Latency (p95):**
  - **Previous Owner:** Platform SRE
  - **New Owner:** Data Engineering Team
  - **Action:** Update relevant documentation (Mini Reference Card, Monitoring Ownership Handbook, Incident Response Runbooks) to reflect new responsibility.
  - **Persona Role Alignment:** ⚠️ Data Engineering Team is not yet formalized in Persona Role Guide — review and update if needed.
