# Prompt: Business Observability Template Validation
Use this prompt when a Business Observability Template is partially completed or unclear. This prompt helps unblock progress by suggesting missing field values using structured reasoning tied to signal types and business step context.
---
## Instructions
- For each **blank field**, add a line starting with `Suggested:` (in inline code style), followed by your proposed value in *italics*.
- For fields with vague content, retain the original and add a second line with `Suggested:` to improve clarity.
- If a field contains **multiple distinct values** (e.g., user roles, signals, steps), return each as a separate bullet (`-`) on its own line, within the same row. Use *italics* for each bullet item.
- **If `Step Type` is not already defined, use business function, technical logic, or user intent to infer and suggest the appropriate classification** (e.g., *Execution*, *Validation*, *Fulfillment*).
- Apply role expectations using the Persona Role Guide.
- Use signal-type + step-type reasoning based on the Prompt Matrix.
- Avoid introducing fictitious values unless explicitly requested; draft plausible placeholders using business or technical context.
---
### Output Guidelines
- Return the **entire Business Observability Template** as a markdown table using the `Field | Value` format shown below.
- This table must reflect the **complete system-of-record version** for the step — fully validated, enriched, and ready for signal generation.
- Do not summarize, separate, or extract fields. Output should be a single consolidated table representing the final state of the step template.
---
## Formatting Conventions
- Use `inline code` for structural labels like `Suggested:`, `Owner:`, `KPI:`
- Use *italics* for all AI-generated or recommended content
- Use bulleted lists (`-`) for multiple items in the same field
- Use indented code blocks for formulas, queries, or logic mappings
---
## Input Required
- A partially completed Business Observability Template
- (Optional) Known `Step Type` (e.g., Execution, Validation, Compliance)
- (Optional) Any domain-specific context about the system or business process
---
## Prompt Matrix Reference (for reasoning)
| Signal Type        | Step Type     | Prompt Guidance                                                                 |
|--------------------|---------------|----------------------------------------------------------------------------------|
| `Business Signal`  | Execution     | What business outcome should be achieved if this step is successful? What KPI reflects it? |
| `Process Signal`   | Validation    | What field, rule, or logic must be satisfied? How do we confirm it executed correctly? |
| `System Signal`    | Execution     | What platform or system supports this step? What telemetry reflects its health? |
---
## Example Application
**Field: Customers / Internal Users**
Original:  
(blank)
`Suggested:`  
- *Business Unit A analysts*  
- *Trade operations*  
- *Compliance auditors*
---
**Field: System Signal**
Original:  
(blank)
`Suggested:`  
- *System A file ingestion latency*  
- *System B queue interface uptime*  
- *Batch file processing success rate*
