# BOS-prompt for BO template signals.md

This prompt enriches a fully validated Business Observability Template with structured signal definitions. It embeds Business, Process, and System signals — with owner attribution — directly into the template fields using the same table format as other observability prompts.

The output is a complete, structured template ready for downstream use (mini reference cards, dashboards, traceability, and alerting).

---

## Input Required

- A validated Business Observability Template with completed context fields (business purpose, users, outcomes, technical function, KPIs)
- (Optional) Step type (Execution, Validation, Fulfillment, etc.)

---

## Instructions

- For each signal type, generate 1–3 relevant signals using the business and technical context.
- Use the following formatting in the value column:
  - Bullet list of signals (one per line)
  - Inline `Suggested:` and *italics* for inferred values
  - Inline `Owner:` with role titles based on the Persona Role Guide
- Return the full observability template using a two-column markdown table: `Field | Value`
- Do not output only signals — the entire enriched template should be returned

---

## Output Format

Return a full Business Observability Template table like this:

```markdown
| **Field**                          | **Value**                                                                                         |
|-----------------------------------|----------------------------------------------------------------------------------------------------|
| Step Name                         | [Step title]                                                                                      |
| Business Process                  | [Name of business process or stage]                                                               |
| Description of Technical Function | [Description of technical execution, logic, inputs, or systems involved]                         |
| Business Function / Purpose       | [Why this step matters to business or customer outcomes]                                          |
| Customers / Internal Users        | - [User group 1] <br> - [User group 2]                                                            |
| What Are Users Trying to Accomplish? | - [Intent 1] <br> - [Intent 2]                                                                  |
| Target Outcomes (KPI)             | - [Business KPI or operational goal]                                                              |
| Definition or Formula (KPI)       | ```[Calculation formula or rule]```                                                               |
| Business Signals                  | - `Suggested:` *[Signal 1]* <br> - `Suggested:` *[Signal 2]* <br> `Owner:` Product Owner          |
| Process Signal                    | - `Suggested:` *[Signal 1]* <br> - `Suggested:` *[Signal 2]* <br> `Owner:` Application Developer  |
| System Signal                     | - `Suggested:` *[Signal 1]* <br> - `Suggested:` *[Signal 2]* <br> - `Suggested:` *[Signal 3]* <br> `Owner:` Platform SRE |
