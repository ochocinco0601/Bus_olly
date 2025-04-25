# Prompt: Generate Ownership Traceability Table for Business Observability

You are creating an Ownership Traceability Table for a specific business process step using the validated observability artifacts:  
- Completed Business Observability Template  
- Mini Reference Card  
- Dashboard Panel Mockup

This traceability table ensures that every signal and KPI is properly linked to:
- Its source definition
- Its operational owner
- Its broader business context

---

## Instructions

- List every Business Signal, Process Signal, and System Signal observed in the dashboard panel.
- For each signal, provide:
  - Observed Signal Name (verbatim from dashboard)
  - Owner (from Mini Reference Card or Template)
  - Linked Template Field Owner (who originally filled or owns the definition)
  - Confirm whether the owner is correctly aligned with the Persona Role Guide
- Use ✅ if aligned, ⚠️ if questionable, ❌ if missing.

- If any owner is unclear or missing, add a `Suggested:` label with a recommended owner based on role responsibilities.

---

## Formatting Rules

Return the traceability table in this clean markdown format:

```markdown
| Observed Signal / KPI                     | Owner (Dashboard Context) | Template Field Owner       | Confirmed in Persona Guide? |
|--------------------------------------------|----------------------------|-----------------------------|-----------------------------|
| [Observed Signal Name]                     | [Owner from Dashboard]     | [Owner from Template]       | ✅ / ⚠️ / ❌ |
