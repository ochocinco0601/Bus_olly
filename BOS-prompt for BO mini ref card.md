# Prompt: Draft Business Impact Playbook

You are generating a Business Impact Playbook for a specific step in a business process using an already validated Business Observability Template.

This card is a concise reference artifact. It summarizes **why the step matters**, who uses it, what success looks like (KPIs), how it's monitored (signals), and what to do when things go wrong (alerts and actions).

---

## Instructions

- Use the completed Business Observability Template as input.
- Classify and structure content into the following sections:
  - **Business Outcomes**
  - **Business Impact Summary Template**
  - **Step Overview**
  - **KPIs (with targets and ownership)**
  - **Signals (grouped by type and with owners)**
  - **Common Alerts**
  - **Responsibility Table (actions tied to thresholds/conditions)**

- If not already given, infer the `Step Type` (e.g., *Validation*, *Execution*, *Fulfillment*) based on:
  - Business Function / Purpose
  - Technical Function
  - KPI themes (e.g., data accuracy vs. transaction success)

Use that `Step Type` to inform:
- Signal emphasis
- Alert phrasing
- Suggested actions

---

### Step Type Examples

Use the `Step Type` to shape the tone and focus of the Business Impact Playbook.

- **Validation Step**
  - Emphasize: correctness, completeness, data quality, compliance.
  - Signals: pass/fail checks, schema conformity, validation rates.
  - Alerts: failed validations, missing fields, integrity errors.
  - Example phrase: "Ensure all required loan fields are present and accurate before trade creation."

- **Execution Step**
  - Emphasize: transaction success, speed, volume, business throughput.
  - Signals: success rates, latency, transaction count, efficiency.
  - Alerts: failures, delays, missed thresholds.
  - Example phrase: "Monitor trade submissions for completion and execution rate."

- **Fulfillment Step**
  - Emphasize: completion, delivery, confirmation, downstream handoff.
  - Signals: fulfillment rate, delivery status, closure confirmation.
  - Alerts: stuck queues, missing handoffs, incomplete chains.
  - Example phrase: "Confirm that downstream systems have received and acknowledged delivery."

---

## Formatting Rules

- Return result in markdown format using these sections:

```markdown
# 🧾 Business Impact Playbook: [Step Name]

## 📌 Business Outcomes
[Summarize business value or risk reduction. Include business tags.]

## 📊 Business Impact Summary Template
When this step is degraded or failing, summarize impact as:

| Impact Category | Assessment | Example | 
|-----------------|------------|---------|
| **Customer/Process** | [Template descriptor] | [Example format] |
| **Financial** | [Template descriptor] | [Example format] |
| **Compliance** | [Template descriptor] | [Example format] |
| **Downstream** | [Template descriptor] | [Example format] |

Owner: [Responsible Role]

## 🧾 Step Overview
| Field | Description |
|-------|-------------|
| **Step Name** | [Name] |
| **Business Process** | [Process or Stage] |
| **Step Type** | [Validation / Execution / Fulfillment] |
| **Technical Function** | [Short summary of logic or integration] |
| **Business Purpose** | [Why this matters — value to business or users] |
| **Key Personas** | - [Persona 1] <br> - [Persona 2] |

## 🔍 Customer Goal
- [What are users trying to get done?]
- [Any implicit business requirements]

## 📈 KPIs (Business Outcomes — What Success Should Look Like)
| KPI | Target | Description | Owner |
|-----|--------|-------------|-------|
| [Name] | [Target] | [Description] | [Owner] |

## 📊 Observability Signals (Business, Process, and System Telemetry)

### About the Signals Below

Each signal in the table below reflects a different layer of observability:

- **🟦 Business Signals** reflect value delivery and desired business outcomes.
- **🟨 Process Signals** reflect correct execution of system or business logic.
- **🟧 System Signals** reflect the infrastructure, platform, or service health needed to support the step.

Together, these help answer:  
**"How do we know this step is working as intended — from both a business and technical perspective?"**

| Type | Signal | Owner |
|------|--------|-------|
| 🟦 Business Signal | [Name] | [Owner] |
| 🟨 Process Signal | [Name] | [Owner] |
| 🟧 System Signal | [Name] | [Owner] |

## 🔔 Common Alerts
- ⚠ [Condition or threshold breach]
- ⚠ [Validation or ingestion failure]
- ⚠ [Latency or availability warning]

## ✅ Responsibility Table: Next Actions
| Condition | Action | Responsible Role |
|-----------|--------|------------------|
| [If condition] | [Do this] | [Who] |
```
