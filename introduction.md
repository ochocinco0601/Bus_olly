Observability at a Glance — Briefing

Executive Summary: Business Observability Initiative
Introduction
 Business observability represents a transformative approach that connects technical performance directly to business outcomes. Where traditional monitoring can focus on system health in isolation, business observability creates a structured framework mapping technical components to business processes and business outcomes.

Core Concept
The framework follows a hierarchical structure:
Business Outcomes: Measurable goals (e.g., increased loan origination volume)


Business Processes: Key workflows that support outcomes


Stages: Major phases within each process


Steps: Specific activities within each stage


Signals: Business KPIs and technical metrics indicating health at each level


This model provides clarity into how system health impacts business functions and customer experience.

Design Progress
We are in the early design phase, focused on:
Defining a common framework to map business processes to technical components


Identifying and prioritizing 3–5 critical business flows


Documenting stages and steps in these flows


Determining relevant signals (technical + business)


Exploring visualization strategies that highlight business impact



Implementation Strategy
Our implementation strategy includes:
Starting with a single critical process (e.g., loan origination)


Partnering with business stakeholders for accurate process mapping


Using existing observability tools to avoid unnecessary complexity


Building process-oriented dashboards aligned to business workflows


Testing/refining before expanding



Value Proposition
Key benefits include:
Faster identification of business-impacting issues


Clear alignment between engineering priorities and business objectives


Business-context-driven decisions


Enhanced cross-functional collaboration


Improved visibility for strategic IT investments


Elevating IT from a cost center to a business enabler



Collaboration Opportunities for Central SRE
We see potential for strong partnership with your team in:
Developing shared taxonomies for event classification


Creating reusable mapping frameworks


Defining consistent alerting patterns based on business impact


Co-developing dashboards built around business flows


Establishing metrics bridging business and technical domains



Current Ecosystem (Supporting Context)
Tooling in Place:
Logs: Splunk, Elastic


APM & Tracing: AppDynamics, Splunk Observability


Dashboards: Grafana, Splunk


Event Correlation: BigPanda


Synthetic Monitoring: ThousandEyes


Alert Routing:
Central alert event pipeline into BigPanda


Many alerts still rely on email-only delivery (legacy behavior)



Challenges & Opportunities
Observability remains reactive, lacking business context


Inconsistent SLI/SLO usage


Multiple tools, but maturity varies


Teams vary in observability skill levels



