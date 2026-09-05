Markdown

# Runbook: Edge-Case & Ambiguous Prompt Escalation

## 1. Purpose
This runbook defines the operational protocol for handling edge cases, ambiguous prompt instructions, and rubric gaps encountered by human evaluators during AI quality assessment workflows.

## 2. Operational Escalation Workflow

[Evaluator Identifies Ambiguity]
│
▼
[Log Ticket with #EdgeCase Tag]
│
▼
[Product Ops Triage & Analysis]
│
▼
[Update Rubric & Notify Evaluators]


### Detailed Steps:
1. **Identification:** An evaluator flags a prompt where existing guidelines do not provide a clear pass/fail directive (e.g., model provides a correct answer using non-standard formatting).
2. **Ticket Submission:** The evaluator submits the Task ID, model output, and description of the ambiguity to the Product Ops queue tagged `#EdgeCase_RubricGap`.
3. **Triage & Review:** Product Operations reviews the ticket, determines whether the issue is an isolated prompt anomaly or a systemic rubric gap, and defines the policy decision.
4. **Resolution & Guideline Update:** Product Ops updates the central evaluation rubric, posts a release note to the evaluator pool, and closes the ticket.

## 3. Service Level Agreement (SLA) Targets

| Impact Level | Criteria | Resolution SLA |
| :--- | :--- | :--- |
| **Critical / Blocker** | Issue impacts >10% of active evaluation batch or halts pipeline progress. | < 30 Minutes |
| **Standard** | Isolated prompt ambiguity; evaluators can pivot to secondary tasks. | < 2 Hours |
| **Low / Informational** | Minor clarification; no immediate impact on throughput metrics. | < 8 Hours |
