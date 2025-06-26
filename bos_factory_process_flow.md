## BOS Factory Process Flow – Stage 2 Execution

### 🟧 System-Level Process Flow: BOS Factory Template Step Lifecycle

| Step | Step Name                        | Description                                                                                           | Actor                  | System         | Business Entity               | Trigger / Condition                        | Outcome                                             |
|------|----------------------------------|-------------------------------------------------------------------------------------------------------|------------------------|----------------|-------------------------------|--------------------------------------------|------------------------------------------------------|
| 1    | Define Process Flow              | Break down the system or business logic into discrete, observable steps                              | Product Owner          | BOS Factory Engine | Business Observability Step   | Product initiative identified              | Entity-centric process flow defined                 |
| 2    | Generate Template Draft          | Create a structured Business Observability Template using GenAI prompt + role hints                  | Product Owner          | BOS Generator  | Business Observability Step   | Process step identified                     | Drafted BOS Template with fields populated          |
| 3    | Collaborate to Complete Fields   | Fill missing context: business purpose, users, KPIs, technical function                              | Product Owner, Dev, SRE| BOS UI         | Business Observability Step   | Draft template available                    | All template fields completed                       |
| 4    | Enrich with Observability Signals| Define Business, Process, and System signals for the step, using context + prompt matrix             | Developer, SRE         | BOS Signal Engine | Business Observability Step   | Template validated                          | Signals embedded in template                        |
| 5    | Assign Ownership Metadata        | Assign named owners for each signal and field, validating against role guide                         | Product Owner          | BOS Governance Layer | Business Observability Step   | Signals defined                              | Ownership traceability established                  |
| 6    | Generate Mini Reference Card     | Create a compact summary for downstream use in dashboards, alerts, and onboarding docs               | Product Owner          | BOS Formatter   | Business Observability Step   | Ownership confirmed                         | Reference card published                            |
| 7    | Create Dashboard Panel Mockup    | Use structured template + signals to generate a dashboard panel representation                       | Platform SRE           | BOS Visualizer  | Business Observability Step   | Mini card available                         | Dashboard mockup generated                          |
| 8    | Final Review & Archive           | Ensure validation checklists are passed and archive the template for reuse and auditability          | Product Owner          | BOS Archive     | Business Observability Step   | Dashboard and traceability confirmed       | Step marked complete and BOS-record ready           |

---

### 🟦 User Journey: Creating a New BOS Template Step

| Step | Step Name                         | Goal or Task                                             | User Role     | Tool or Interface | Decision or Friction Point                             | Outcome                            |
|------|-----------------------------------|----------------------------------------------------------|---------------|-------------------|--------------------------------------------------------|-------------------------------------|
| 1    | Identify Monitoring Gap           | Recognize a business flow or outcome is not observable   | Product Owner | Stand-up call, Notion | Is this a real issue or just a curiosity?             | Initiates BOS step creation        |
| 2    | Frame the Problem                 | Structure the “why it matters” using the CIDO model      | Product Owner | BOS Factory Prompt | Framing feels fuzzy or solution-biased                | CIDO statement saved               |
| 3    | Describe the Step                 | Write what the system does and why this step matters     | Product Owner | BOS UI Template    | Does the description make sense to devs and ops?      | Step field complete                |
| 4    | Invite Collaboration              | Bring in Dev and SRE to fill in tech and signal context  | Product Owner | Slack, Template    | Developer doesn’t know what “business signal” means   | All context fields filled in       |
| 5    | Review the Draft                  | Review template in working session                       | Product Owner, Dev, SRE | BOS Factory    | Is anything still unclear or unowned?                 | Template validated                 |
| 6    | Submit for Signal Generation      | Trigger GenAI prompts for observability signals          | Product Owner | BOS Factory Prompt | Which signals are worth keeping?                      | Signals generated and assigned     |
| 7    | Share Reference Card              | Summarize for team in stand-up or doc                    | Product Owner | Mini Card          | Does this help the SRE? The business? Anyone?         | Card shared, feedback collected    |
| 8    | Move to Dashboard Design          | Forward signals to SRE for dashboard panel integration   | Product Owner → SRE | Dashboard Builder | Are signals well labeled and owned?                   | Panel mockup created               |
| 9    | Archive Step                      | Store finalized artifacts and link to incident/ops docs  | Product Owner | Confluence, GitHub | Can others reuse this?                               | Step is reusable + BOS-compliant   |

