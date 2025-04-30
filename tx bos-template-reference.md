# BOS Template Reference

## Purpose
This template standardizes how we capture business observability requirements across all business processes. It ensures:

- ✅ Every business step has a clear purpose and defined signals
- ✅ Ownership is clearly assigned across Product, App Dev, and Platform teams
- ✅ Business, process, and system signals are comprehensively defined

## Template Structure

| Field Phase | Owner | Purpose |
|:------------|:------|:--------|
| **Business Process** | Product Owner | Defines which broader business process this step supports |
| **Step Name** | Product Owner / SME | Names the system step or function being observed |
| **Description of Technical Function** | Application Developer | Explains what this system technically does (logic, inputs/outputs) |
| **Business Function / Purpose** | Product Owner | Describes why this step matters and what business outcome it enables |
| **Customers / Internal Users** | Product Owner | Lists who depends on or is affected by this step |
| **What Are Users Trying to Accomplish?** | Product Owner / UX | Captures what goal or task the user is trying to complete |
| **Target Outcomes (KPI)** | Product Owner | Defines what success looks like when this step works correctly |
| **Definition or Formula (KPI)** | Developer / Data Analyst | Provides formula or logic used to calculate the KPI |
| **Business Signals** | Product Owner | Identifies business value indicators that reflect success or failure |
| **Process Signals** | Developer / QA | Defines process-level checks that confirm correct execution |
| **System Signals** | Platform SRE | Specifies system-level telemetry reflecting infrastructure health |

## How the Factory Uses This Template

1. **DEFINE phase**: Product Owner completes the business context fields
2. **POPULATE phase**: All three teams fill in their respective signal sections
3. **VALIDATE phase**: Cross-functional review ensures all signals have clear owners
4. **BUILD phase**: Template outputs feed into dashboard requirements
5. **MONITOR phase**: Template becomes the reference for continuous improvement

## Example (Partially Completed)

| Field | Value |
|:------|:------|
| **Business Process** | Stage 1: Trade Creation |
| **Step Name** | Step 1.1: Receive Pooling Data from System B |
| **Technical Function** | System A receives batch files from System B, parses structured loan pool data, and stores results in internal tables for further processing. |
| **Business Purpose** | Ensures Business Unit A has accurate and timely loan pool data to support trade creation, compliance validation, and operational readiness. |
| **Business Signals** | `Suggested:` *Percent of pool files ingested within SLA* <br> `Suggested:` *Total loan records processed* <br> `Owner:` Product Owner |
| **Process Signals** | `Suggested:` *Validation pass rate for required pool data fields* <br> `Suggested:` *File completeness confirmation logic executed* <br> `Owner:` Application Developer |
| **System Signals** | `Suggested:` *System A file ingestion latency* <br> `Suggested:` *System B queue interface uptime* <br> `Suggested:` *Batch file processing success rate* <br> `Owner:` Platform SRE |
