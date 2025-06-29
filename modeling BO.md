Modeling Business Observability
business observability reference model
Business Outcomes
└── Business Processes / Customer Journeys
└── Stages
└── Steps
└── Signals (metrics for Steps)
└── Observability Data
Explanation of Each Layer:
Business Outcomes


High-level strategic goals or measurable impacts the organization seeks to achieve (e.g., revenue growth, customer retention, compliance).
Strategic goals or measurable impacts the organization aims to achieve.
Business Processes / Customer Journeys


Practical activities or tasks customers or internal users perform to achieve those outcomes.
Specific workflows, interactions, or user activities that directly support or lead to achieving the stated business outcomes.
Series of workflows or user interactions essential to achieving these outcomes (e.g., mortgage origination, online payments).
Specific workflows or user interactions directly tied to achieving business outcomes.
Stages


Logical segments within a business process representing key phases or milestones (e.g., application submission, underwriting, approval).
Explicitly communicate technical performance in business-friendly terms.
Steps


Individual tasks or specific user/system actions within each stage (e.g., address validation, credit check API call, payment transaction completion).
specific activities or tasks within each stage of a business process.
Signals


Clearly defined metrics representing health, reliability, or performance of a step (e.g., "Login success rate," "Checkout transaction latency").
Observability Data 
Raw data collected from systems providing deeper context and diagnostic capability.
??Service Level Indicators used to measure the performance or health of those applications or services, such as latency, availability, throughput, or error rates.
??Observability data points or telemetry (metrics, logs, traces, events) that indicate the health, performance, or errors at the step level (e.g., API latency, transaction success rate, error logs).


Why This Structure Matters:
Useful for Executives and Business Leaders.
Focusing explicitly on business outcomes and linking them to underlying technical processes through observability helps organizations (executive leaders?):
Prioritize engineering efforts
Allocate resources effectively
Clearly communicate the impact of tech investments to executive leadership and business stakeholders

Useful for tech and business teams.
Clearly defining these relationships helps teams:
Quickly pinpoint the business impact of technical issues.
Effectively communicate technical health in terms of business outcomes.
Prioritize technical investments aligned with organizational goals.

Why This Integration Matters:
This integrated model clearly links technical components directly to business outcomes, providing:
Precision: Understanding exactly which services affect each step.
Visibility: Direct linkage of performance metrics to customer or business impact.
Efficiency: Faster diagnosis and prioritization of issues by aligning observability with business priorities.

# Next layer: Business Processes / Customer Journeys

Below business outcomes, the next level is typically business processes or customer journeys. This level represents the specific workflows, interactions, or user activities that directly support or lead to achieving the stated business outcomes.

## Explanation

Business outcomes reflect high-level strategic goals and measurable results that matter most to the business, while business processes or customer journeys represent the practical activities or tasks customers or internal users perform to achieve those outcomes.

A Business Observability Solution, such as New Relic Pathpoint, traces these business processes, measuring their health and performance to reveal how effectively technical performance supports or hinders them.

## Examples of Business Outcomes and their Associated Processes

**Business Outcome: Improved Loan Origination Volume**

- **Process:** Mortgage application submission and approval workflow.
- **Metrics/Insight Examples:**
  - Application form load times.
  - Success rate of online submissions.
  - Average transaction latency.

**Business Outcome: Higher Customer Retention**

- **Business Process:** Online account management or payments.
- **Insight Examples:**
  - Number of failed transactions due to application errors.
  - Frequency of outages impacting customer access.
  - Average resolution time for payment issues.

**Business Outcome: Operational Cost Reduction**

- **Business Process:** Automated backend processing or batch jobs.
- **Insight Examples:**
  - Batch job completion rates.
  - Percentage of automated vs. manual interventions.

**Business Outcome: Compliance and Risk Mitigation**

- **Business Process:** Data processing pipelines for regulatory reporting.
- **Insight Examples:**
  - Error rates or delays in compliance-critical jobs.
  - Monitoring for breaches of defined thresholds (e.g., data freshness).

Why This Matters
Focusing explicitly on business outcomes and linking them to underlying technical processes through observability helps organizations prioritize engineering efforts, 
allocate resources effectively, and clearly communicate the impact of technology investments to executive leadership and business stakeholders.

BO MODEL IMAGE here...

# The Business Observability Model

The Business Observability Model shown in the diagram illustrates a hierarchical structure with five distinct levels that relate to each other in a top-down flow. Below is an explanation of the relationships between these levels.

## Business Outcomes → Business Processes

- **Business outcomes** represent the high-level goals an organization wants to achieve (e.g., improved loan origination, higher customer retention).
- Each business outcome is supported by specific **business processes** that work toward achieving that outcome.
- The relationship can be **one-to-one** or **one-to-many**—a single business outcome might require multiple business processes.

## Business Processes → Stages

- **Business processes** are composed of distinct **operational stages** that represent major phases of work.
- Each business process breaks down into one or more stages that must be completed to fulfill the process.
- For example, the “Mortgage Application Submission and Approval” process includes stages such as “Application Submission” and “Application Validation.”

## Stages → Steps

- **Stages** are further divided into specific **steps** that represent discrete actions or activities.
- Each stage contains one or more steps that must be completed to advance through that stage.
- For instance, the “Account Access” stage includes the “Customer Login” step.

## Steps → Signals

- **Steps** are measured and monitored through specific **signals** or metrics.
- Each step is associated with multiple signals that provide quantitative measurements of performance.
- These signals are the data points used to determine how well each step is performing.

## Overall Flow

- The diagram shows a clear cascade from **strategic business outcomes** down to **tactical, measurable signals**.
- This structure creates a **traceability framework**, allowing any measured signal to be traced upward to the business outcome it supports.
- Conversely, business leaders can see which specific metrics they should monitor to gauge progress toward their desired outcomes.
- This **five-level hierarchy** enables organizations to align day-to-day operational metrics with strategic business goals, creating a comprehensive observability framework that connects technical measurements to business value.



