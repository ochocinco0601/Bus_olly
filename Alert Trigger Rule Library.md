
# Alert Trigger Rule Library (v1.0)

**Version:** 1.0  
**Release Date:** 2025-03-28  
**Maintainer:** Observability Governance Lead  
**Status:** Locked baseline for implementation and reference

> This is the baseline version of the Alert Trigger Rule Library. All future changes will be tracked as incremental versions. Use this version for training, tool alignment, governance reporting, and implementation planning.

---

## Supported Trigger Actions

Only the following standardized trigger actions are permitted to ensure clarity, scalability, and governance alignment:

1. **xMatters** – For paging/on-call escalation  
2. **ServiceNow Incident** – For structured incident management  
3. **Dashboard alert/visualization** – For contextual and passive alerting  
4. **Event suppression or enrichment** – For noise control and correlation logic  
5. **Email** – Discouraged; legacy use only under strict review  
6. **Audit trail / Governance queue** – For compliance, tuning, and quality improvement workflows

> All rules below conform to this trigger action model.

---

## Implementation Guidance

To operationalize this rule library across teams and platforms:

### 1. Ownership & Roles
- Assign each alert rule to a responsible **system owner or SRE team**.
- Designate a **rule steward** to review triggers quarterly.

### 2. Tool Alignment
- Map trigger actions to implementation in tools:  
  - `xMatters` integration in alert platform  
  - `ServiceNow` incident connector for auto-ticketing  
  - Dashboards configured in Splunk, Grafana, or ITSI  
  - Suppression/enrichment in BigPanda, ITSI, or custom logic pipelines

### 3. Governance Workflow
- Integrate alert lifecycle with change management:  
  - New alerts must be proposed via template  
  - Decommissioned alerts must be logged with rationale  
- Use the **Governance Queue** trigger for non-compliant alerts

### 4. Testing & Validation
- All alerts must include:  
  - Trigger simulation or historical proof  
  - Clear success/failure criteria  
  - Target service mapping and routing validation

### 5. Continuous Improvement
- Conduct quarterly reviews:  
  - High-frequency alert analysis  
  - Unused alert pruning  
  - Correlation rule effectiveness  
- Use **CI rules** (e.g., CI-002, CI-008) as feedback signals

### 6. Communication
- Maintain visibility:  
  - Share rule library and trigger summaries with teams  
  - Document alert behavior in playbooks and dashboards  
  - Integrate with observability onboarding/training

---

## Alert Trigger Rule Set

### Metric-Based Alert Patterns

#### Rule ID: GC-001
- **Name:** Single GC Threshold Breach  
- **Condition:** GC time exceeds threshold once  
- **Trigger Action:** dashboard_only  
- **Severity:** warning  
- **Tier Applicability:** all  
- **Rationale:** One-time GC spikes are usually self-recovering and do not require immediate attention. Avoids unnecessary incident volume.

#### Rule ID: GC-002
- **Name:** Sustained GC Warning  
- **Condition:** GC warning persisted for >15 minutes  
- **Trigger Action:** ServiceNow incident (low priority)  
- **Severity:** warning  
- **Tier Applicability:** Tier 1, Tier 2  
- **Rationale:** Sustained GC load may indicate early signs of memory pressure; early action may prevent incident escalation.

#### Rule ID: GC-003
- **Name:** GC + Memory Saturation  
- **Condition:** GC warning occurs with high memory usage  
- **Trigger Action:** ServiceNow incident (medium priority)  
- **Severity:** warning/exception  
- **Tier Applicability:** Tier 1, Tier 2  
- **Rationale:** Combined conditions raise risk of degraded performance or crash, warranting investigation.

---

### Transaction Latency Alert Patterns

#### Rule ID: TX-001
- **Name:** High Latency, No Failures  
- **Condition:** Transaction latency exceeds threshold without error rate increase  
- **Trigger Action:** ServiceNow incident (low priority)  
- **Severity:** warning  
- **Tier Applicability:** Tier 2, Tier 3  
- **Rationale:** May indicate slow downstream dependency; warrants analysis but not immediate paging.

#### Rule ID: TX-002
- **Name:** High Latency + Error Rate Spike  
- **Condition:** Transaction latency and error rate exceed thresholds  
- **Trigger Action:** xMatters + ServiceNow incident  
- **Severity:** exception  
- **Tier Applicability:** Tier 1  
- **Rationale:** Indicates degraded user experience or possible outage; immediate intervention required.

#### Rule ID: TX-003
- **Name:** Persistent Latency Across Multiple Endpoints  
- **Condition:** Latency threshold exceeded on 3+ endpoints for >10 minutes  
- **Trigger Action:** ServiceNow incident (medium priority)  
- **Severity:** warning/exception  
- **Tier Applicability:** Tier 1, Tier 2  
- **Rationale:** Suggests systemic issue, not isolated blip; requires visibility and triage.

---

### Composite Alert Patterns

#### Rule ID: CP-001
- **Name:** GC + High Latency + Transaction Errors  
- **Condition:** GC threshold breach + transaction latency spike + elevated error rate  
- **Trigger Action:** xMatters + ServiceNow incident (high priority)  
- **Severity:** exception  
- **Tier Applicability:** Tier 1  
- **Rationale:** Strong correlation of symptoms pointing to degraded service; requires immediate on-call response.

#### Rule ID: CP-002
- **Name:** CPU Saturation + Memory Pressure + Latency  
- **Condition:** CPU usage > 90% + memory usage high + latency increase  
- **Trigger Action:** ServiceNow incident (medium priority)  
- **Severity:** warning/exception  
- **Tier Applicability:** Tier 1, Tier 2  
- **Rationale:** Indicates potential for cascading system failure if not addressed.

#### Rule ID: CP-003
- **Name:** Drop in Business Flow + Backend Dependency Failures  
- **Condition:** Flow completion rate drops + API/dependency errors increase  
- **Trigger Action:** ServiceNow incident + escalation to product owner  
- **Severity:** exception  
- **Tier Applicability:** Tier 1  
- **Rationale:** Suggests business impact due to underlying technical fault; cross-team awareness needed.

---

### Suppression Patterns

#### Rule ID: SP-001
- **Name:** Known Noisy Endpoint (Suppression)  
- **Condition:** Alerts from endpoint with known low-impact behavior (tagged `suppress_alert=true`)  
- **Trigger Action:** Suppressed  
- **Severity:** warning/informational  
- **Tier Applicability:** all  
- **Rationale:** Prevent unnecessary escalation from low-risk, known-noisy sources.

#### Rule ID: SP-002
- **Name:** Flapping Alert Condition  
- **Condition:** Alerting on/off toggles >3x in 30 minutes  
- **Trigger Action:** Suppress repeat alerts, trigger incident only after threshold  
- **Severity:** warning  
- **Tier Applicability:** all  
- **Rationale:** Reduces noise and alert fatigue caused by unstable but non-critical metrics.

#### Rule ID: SP-003
- **Name:** Low-Tier System, Informational Event  
- **Condition:** Informational alert from Tier 3/non-prod system  
- **Trigger Action:** Suppressed or dashboard only  
- **Severity:** informational  
- **Tier Applicability:** Tier 3  
- **Rationale:** Visibility is maintained via dashboards, but no operational disruption expected.

---

### Business Observability Alert Patterns

#### Rule ID: BO-001
- **Name:** Customer Flow Drop-off Detected  
- **Condition:** Business flow reaches step A but does not progress to step B within threshold time  
- **Trigger Action:** ServiceNow incident (medium priority)  
- **Severity:** exception  
- **Tier Applicability:** Tier 1  
- **Rationale:** Indicates a disruption in the customer journey (e.g., application not completed); critical for business impact visibility.

#### Rule ID: BO-002
- **Name:** Missing Informational Milestone Event  
- **Condition:** Expected informational event (e.g., `loan_submitted`) not received within defined timeframe  
- **Trigger Action:** ServiceNow incident or dashboard alert  
- **Severity:** warning  
- **Tier Applicability:** Tier 1, Tier 2  
- **Rationale:** Absence of a known event may signify stalled process, system lag, or business flow interruption.

#### Rule ID: BO-003
- **Name:** Business KPI Anomaly Detected  
- **Condition:** Business metric (e.g., conversion rate, doc uploads) deviates from historical baseline  
- **Trigger Action:** ServiceNow incident (medium priority)  
- **Severity:** warning/exception  
- **Tier Applicability:** Tier 1  
- **Rationale:** Business KPIs reflect user success and financial impact; anomalies must be triaged.

---

### Continuous Improvement Alert Patterns

#### Rule ID: CI-001
- **Name:** High-Frequency Alert Source  
- **Condition:** Same alert source triggers > X times/day  
- **Trigger Action:** Dashboard + alert tuning review  
- **Severity:** warning  
- **Tier Applicability:** all  
- **Rationale:** Indicates poor alert threshold, missing suppression, or noise pattern.

#### Rule ID: CI-002
- **Name:** Alerts Closed Without Action  
- **Condition:** > Y% of alerts closed with no action in past 30 days  
- **Trigger Action:** Governance review ticket  
- **Severity:** informational  
- **Tier Applicability:** all  
- **Rationale:** Helps identify non-actionable alerts that contribute to fatigue.

---

### Advanced Prediction Alert Patterns

#### Rule ID: AP-001
- **Name:** Forecasted SLO Breach  
- **Condition:** SLO projected to breach within next 6 hours  
- **Trigger Action:** ServiceNow incident + team notification  
- **Severity:** warning  
- **Tier Applicability:** Tier 1  
- **Rationale:** Enables proactive remediation to protect customer commitments.

#### Rule ID: AP-002
- **Name:** Predicted CPU Saturation  
- **Condition:** CPU usage trend predicts >90% usage within 2 hours  
- **Trigger Action:** Dashboard alert + capacity planning task  
- **Severity:** warning  
- **Tier Applicability:** all  
- **Rationale:** Early intervention can avoid cascading resource issues.

---

## More rule modules will be added over time for real-time decision automation and platform-based prediction tuning.
