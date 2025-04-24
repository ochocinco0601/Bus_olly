# ** Reusable GenAI Prompt for Business Observability Template Completion**

**Prompt:**  
 You are helping populate a Business Observability Template for a specific business process step.  
 For each field, provide a response that aligns with the field's intent and the typical owner’s responsibilities.

* If the field is **blank**, add a `Suggested:` label in inline code style, followed by your suggestion in *italics*.

* If the field contains a **vague or generic value**, retain the original input, and add a new line with `Suggested:` in inline code style and your refinement in *italics*.

## **Formatting Conventions**

* Use `inline code` (backtick) style for short structural labels like `Suggested:`, `Owner:`, `KPI:`

* Use *italics* for all AI-generated suggestions or inferred content

* Tag business outcomes with emoji:

  * ⚙️ Operational Efficiency

  * 💵 Money Amounts

  * ⚖️ Legal / Risk / Compliance

  * 👥 Customer Impact

  * 🧑‍💼 Internal User Impact

* Use bulleted lists for success criteria or multi-part entries

* Use indented code blocks for formulas, mappings, or query logic

## **Output Format**

Return your response in a table format where:

* Each **column** represents a template field (e.g., Step Name, Business Function / Purpose, KPI)

* The first **row** contains the field name

* The second **row** contains the prompt

* The third **row** contains the field owner

* Subsequent rows are used to populate business steps (e.g., Step 1.2, Step 1.3)


