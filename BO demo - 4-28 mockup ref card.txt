# Business Observability System (BOS) Factory

## Problem: From System Alerts to Business Impact

When the FICC Gateway went down at 6:08 AM, we experienced our common challenge:

* Platform team got alerts about system availability
* Nobody knew the business impact for 45+ minutes
* No clear ownership of who needed to act
* Multiple teams scrambled trying to piece together meaning
* Business stakeholders kept asking "What does this mean for us?"

This isn't a technology problem—it's a shared responsibility problem.

## Solution: The BOS Factory

The BOS Factory creates structured artifacts with clear ownership that connect system alerts directly to business outcomes.

## Real Artifacts Already Created with Capital Markets

### Mini Reference Card

{panel:title=MINI REFERENCE CARD: RECEIVE POOLING DATA FROM SYSTEM B|borderStyle=solid|borderColor=#ccc|titleBGColor=#f4f5f7|bgColor=#fff}

**WHY THIS MATTERS**  
Ensuring accurate and timely ingestion of loan pool data from System B into System A is critical for enabling compliant trade creation, reducing operational risk, and avoiding downstream delays.

**STEP OVERVIEW**  

| Field | Description |
|-------|-------------|
| Step Name | Step 1.1: Receive Pooling Data from System B |
| Business Process | Stage 1: Trade Creation |
| Step Type | Validation |

**OBSERVABILITY SIGNALS**  

| Type | Signal | Owner |
|------|--------|-------|
| BUSINESS | Percent of pool files ingested within SLA | Product Owner |
| BUSINESS | Total loan records processed | Product Owner |
| PROCESS | Validation pass rate for required fields | Application Developer |
| PROCESS | File completeness check executed | Application Developer |
| SYSTEM | System A ingestion job latency (p95) | Platform SRE |
| SYSTEM | System B delivery job success rate | Platform SRE |
| SYSTEM | Batch file processing error count | Platform SRE |

**RESPONSIBILITY TABLE**  

| Condition | Action | Responsible Role |
|-----------|--------|------------------|
| Pool file SLA breach | Investigate System B delivery logs | Platform SRE |
| Validation failures | Notify App Dev and Business Ops | Application Developer |
| Batch job errors | Retry ingestion or escalate | Platform SRE |
{panel}

### Dashboard Panel

{panel:title=DASHBOARD PANEL — RECEIVE POOLING DATA FROM SYSTEM B|borderStyle=solid|borderColor=#ccc|titleBGColor=#f4f5f7|bgColor=#fff}

**BUSINESS SIGNALS**
- Percent of Pool Files Ingested Within SLA: 98% ✓   (Owner: Product Owner)
- Total Loan Records Processed: 12,340 ✓            (Owner: Product Owner)

**PROCESS SIGNALS**
- Validation Pass Rate (Required Fields): 99% ✓     (Owner: Application Developer)
- File Completeness Check Executed: 100% ✓          (Owner: Application Developer)

**SYSTEM SIGNALS**
- System A Ingestion Job Latency (p95): 1800ms ✓    (Owner: Platform SRE)
- System B Delivery Job Success Rate: 100% ✓        (Owner: Platform SRE)
- Batch File Processing Error Count: 0 ✓            (Owner: Platform SRE)

**RECENT ALERTS**
- [INFO] All files processed within SLA
{panel}

## Three Roles Working Together

{status:title=SHARED RESPONSIBILITY MODEL|color=blue|subtle=false}
This is not just a Platform project. It requires shared responsibility.
{status}

| Role | Contribution | Example |
|------|--------------|---------|
| Product | Defined business context and metrics | "Pool file ingestion is critical to trade creation" |
| Application | Identified key process signals | "Validation pass rate is our key health indicator" |
| Platform | Mapped system metrics | "Gateway response time directly affects this step" |

## Implementation Timeline

{status:title=READY TO IMPLEMENT|color=green|subtle=false}
We've proven this works and are ready to scale.
{status}

| Timeline | Action | Status |
|----------|--------|--------|
| Next 2 weeks | Complete Capital Markets implementation | {status:color=yellow}In progress{status} |
| May 2025 | Apply to next critical business flow | {status:color=red}Needs your input{status} |
| June-July 2025 | Expand to 2 additional flows | {status:color=red}Needs commitment{status} |
| Q4 2025 | Integrate with Start of Day reviews | {status:color=grey}Planning phase{status} |

## What We Need From You

{panel:title=KEY QUESTIONS|borderStyle=solid|borderColor=#ccc|titleBGColor=#f4f5f7|bgColor=#fff}
1. Which critical business flow matters most to you right now?
2. Will you commit resources from all three teams?
3. Will you help establish this as a shared responsibility?
{panel}

---

**Contact:** [Your Name] | [Your Email] | [Team Name]
