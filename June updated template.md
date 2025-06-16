# 📋 Business Process & Step Function Mapping

> 💡 **How to Think with This Template**
>
> This template helps you link **who is involved**, **what they’re trying to do**, and **how you know if it's working.**
>
> * Start with the **process** and describe the specific **step** you're analyzing.
> * Identify **roles or systems** involved and their goals.
> * Define **KPIs** that measure success and **signals** that provide real-time evidence.
> * Ensure everything aligns — if a role has a goal, then a signal or KPI should prove whether that goal is being met.
>
> 🎯 **KPI Tip:**
> KPIs reflect whether outcomes are happening **consistently at scale**.
>
> * Start from a user or business goal
> * Define a measurable, outcome-focused target
> * Use KPIs to track *patterns of success or failure*, not isolated events

---

## 🔹 Business Process Overview

| **Field**        | **Description**                                                                                                                                                                              |
| ---------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Process Name** | Loan Fulfillment                                                                                                                                                                             |
| **Description**  | *Deliver approved loan funds to qualified applicants in a timely, compliant, and efficient manner. Supports revenue generation and customer trust while managing risk and operational cost.* |

---

## 🔸 Step 1.2 – Validate Income

| **Field**   | **Value**                                                                                                        |
| ----------- | ---------------------------------------------------------------------------------------------------------------- |
| Step Name   | Validate Income                                                                                                  |
| Description | Ensure borrower income is accurate and meets policy requirements, reducing risk of default or misrepresentation. |

---

## 🔸 Role-to-Signal Relationship Mapping

| **Role Type**          | **Example**                      | **Goal / Intent**                                 | **Mapped KPI(s)**                   | **Mapped Business Signal(s)**                  |
| ---------------------- | -------------------------------- | ------------------------------------------------- | ----------------------------------- | ---------------------------------------------- |
| Customer (Human)       | Home loan applicant              | Receive a quick decision and clear communication  | Income Verification Pass Rate       | Verification Outcome                           |
| Internal User (System) | Document ingestion microservice  | Parse and extract income data from uploaded files | Document Completeness Score         | Income Documentation Flag                      |
| Business (Automated)   | Compliance dept via rules engine | Enforce income-related risk policy                | (Implied via signal logic, not KPI) | Risk Threshold Triggered, Verification Outcome |

---

## 🔸 Business Outcome & Signal Definitions

| **Signal Type** | **Name**                      | **Target or Threshold**                  | **Formula or Description**                                      |
| --------------- | ----------------------------- | ---------------------------------------- | --------------------------------------------------------------- |
| Business KPI    | Income Verification Pass Rate | ≥ 95%                                    | (Passed Verifications / Total Verifications) × 100              |
| Business KPI    | Document Completeness Score   | ≥ 90%                                    | (Complete Documents / Total Documents Submitted) × 100          |
| Business Signal | Verification Outcome          | N/A                                      | Pass/fail result of income verification service                 |
| Business Signal | Income Documentation Flag     | N/A                                      | Indicates supporting income documents are incomplete or invalid |
| Business Signal | Risk Threshold Triggered      | Threshold defined in risk scoring policy | Boolean flag if income falls below minimum policy requirement   |

---


---

## 🔸 Technical Implementation: Step 1.2

> 💡 **How to Think with This Template**
>
> 🔧 **Technical Thinking Tip:**  
> This section describes how the system performs this step behind the scenes — what it does, how it connects, and what data flows through.
>
> - List involved systems  
> - Show direction of flow  
> - Include interface type and data format where helpful
>
> **Examples:**
>
> | Use Case                | Example Technical Flow                                              |
> |------------------------|---------------------------------------------------------------------|
> | REST API → Rule Engine  | Web App → (POST: JSON) → Rules API                                  |
> | Document Upload to OCR  | UI → (POST: PDF) → OCR Service → (JSON) → Risk Engine               |
> | Batch System → Database | Legacy Batch → (SFTP: CSV) → Processing Container → (JDBC) → Oracle |
> | Streaming Microservices | App A → (Kafka: topicX) → App B → (Kafka: topicY) → Event Consumer  |



| **Field**           | **Value**                                                                                                   |
|---------------------|-------------------------------------------------------------------------------------------------------------|
| Technical Function  | Parse uploaded income documents using OCR, extract structured income data, and forward to rule engine.     |
| Technical Flow      | Web App → (POST: PDF) → OCR Service → (Kafka: Parsed JSON) → Rules Engine                                   |


---

> 💡 **How to Think with This Template**
>
> ⚙️ **Process Signal Tip:**  
> These signals confirm that the **internal logic** and **control flow** executed as expected — even if the business outcome or KPI hasn't yet been affected.
>
> - Did validation or transformation steps occur as designed?
> - Was input data usable and complete?
> - Did workflow branching happen at the correct decision point?
>
> 🧠 Think like a developer or automation SME checking for *correct execution*, not just final outcomes.
>
> ** Process Signal Examples:**
>
> | Use Case                     | Process Signal             | What It Verifies                                      |
> |-----------------------------|----------------------------|--------------------------------------------------------|
> | Document parsed             | `Income Parsed`            | OCR successfully extracted structured income           |
> | Rule engine triggered       | `Validation Rule Fired`    | At least one rule executed on income data              |
> | Input data check failed     | `Missing Income Flag`      | No income data was found or extracted                  |
> | Eligibility calculation ran | `Eligibility Flow Complete`| All eligibility logic paths completed without error    |

---

> 💡 **How to Think with This Template**
>
> 🖥️ **System Signal Tip:**  
> These signals tell you whether the *underlying systems, infrastructure, or platforms* are operating reliably enough to support the business process.
>
> - Is the service or container running?
> - Are APIs, queues, or databases available?
> - Are latency or error rates within acceptable bounds?
>
> 🧠 Think like an SRE or platform engineer watching the foundation.  
> If a system fails — even if logic is correct — the process still breaks.
>
> **System Signal Examples**
> 
| **Use Case**                | **System Signal**               | **What It Indicates**                                         |
|----------------------------|----------------------------------|---------------------------------------------------------------|
| API availability           | Rules API 5xx Rate               | Backend service is returning errors                          |
| Container uptime           | OCR Container Liveness           | OCR microservice is running and responsive                   |
| Queue processing health    | Kafka Consumer Lag               | Downstream service is falling behind in message consumption  |
| Database connectivity      | Oracle Connection Errors         | Application cannot reliably connect to the database          |
| Latency threshold exceeded | Income Verification Latency      | The step is too slow even if it completes successfully       |

## 🔸 System Signal Definitions: Step 1.2 – Validate Income

| **Signal Name**               | **System Component**       | **Condition or Trigger**                   | **Purpose / Interpretation**                                      |
|-------------------------------|----------------------------|---------------------------------------------|-------------------------------------------------------------------|
| OCR Container Liveness        | Document Parsing Service   | Container healthcheck fails                | OCR service is down or unresponsive                              |
| Kafka Consumer Lag – Income   | Event Messaging Platform   | Lag exceeds 100 messages                   | Rule engine can't keep up with incoming income documents         |
| Rules API 5xx Rate            | Income Verification API    | ≥ 5% error rate over 5 minutes             | Indicates backend policy engine is failing or overloaded         |
| Income Verification Latency   | Entire Step Path           | > 3 seconds average                        | Detects slowdowns even if results are eventually successful      |


