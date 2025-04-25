# Prompt: Draft Business Observability Dashboard Panel Mockup

You are generating a text-based dashboard **panel** mockup for a specific business process step using a fully validated and signal-enriched Business Observability Template.

This panel represents the observability view for **one step** of a larger business flow.  
In full dashboards, multiple step panels will be composed together based on business stages, user roles, or operational needs.

---

## Instructions

- Use the completed Mini Reference Card and Signal Matrix as input.
- Create a clean, structured dashboard **panel** layout that includes:
  - **Panel Title** (Step Name)
  - **Purpose Summary** (Always listed first — anchors operational relevance)
  - **Audience / User Groups** (Who depends on or consumes this panel)
  - **Metrics grouped by Signal Type**:
    - Business Signals first
    - Then Process Signals
    - Then System Signals
  - **Recent Alerts Section**
  - **Next Steps / Monitoring Actions Section**

- Embed **ownership inline** for each metric.
- Label each signal clearly by type.
- Apply **Step Type awareness** to guide what success looks like:
  - *Validation step*: Focus on correctness, completeness, data integrity.
  - *Execution step*: Focus on transaction success, speed, throughput.
  - *Fulfillment step*: Focus on delivery, closure, and handoff completion.

---

## Formatting Rules

Return the panel in a clean text-box layout:

```markdown
┌────────────────────────────────────────────────────────────────────────────┐
│      DASHBOARD PANEL — [Step Name]                                          │
├────────────────────────────────────────────────────────────────────────────┤
│                                                                            │
│  🧭 Purpose: [Short statement explaining operational goal for this step]   │
│                                                                            │
│  📌 Used by: [Audience: Personas, Teams]                                    │
│                                                                            │
│  📈 BUSINESS SIGNALS                                                       │
│  - [Metric Name]: [Current Value] ✓ (`Owner:` [Role])                      │
│  - [Metric Name]: [Current Value] ✓ (`Owner:` [Role])                      │
│                                                                            │
│  ⚙ PERFORMANCE RELIABILITY SIGNALS                                         │
│  🟨 Process Signals                                                        │
│  - [Metric Name]: [Current Value] ✓ (`Owner:` [Role])                      │
│                                                                            │
│  🟧 System Signals                                                         │
│  - [Metric Name]: [Current Value] ✓ (`Owner:` [Role])                      │
│                                                                            │
│  🚨 RECENT ALERTS                                                          │
│  - [Example: Alert for validation failure, SLA breach, or latency spike]    │
│                                                                            │
│  🔍 NEXT STEPS                                                             │
│  • [Instruction 1: Action based on signal or threshold]                   │
│  • [Instruction 2: Escalation or monitoring guidance]                     │
└────────────────────────────────────────────────────────────────────────────┘
