# Evaluation Rubric: Mathematical & Logic Validation

## 1. Overview & Purpose
This rubric establishes standardized criteria for human evaluators assessing multi-step logic, data extraction, and numerical reasoning outputs from frontier LLMs. The goal is to eliminate evaluator subjectivity and enforce deterministic verification.

## 2. Core Scoring Framework
Tasks are scored on a binary scale (**Pass / Fail**) supported by dimensional ratings:

* **Pass (1):** The response is 100% mathematically accurate, explicitly demonstrates its step-by-step reasoning, adheres to formatting constraints, and uses no unverified assumptions.
* **Fail (0):** The response contains arithmetic errors, variable drift, hallucinated values, skipped steps, or formatting non-compliance.

## 3. Dimensional Evaluation Matrix

| Dimension | Pass Requirements | Fail Triggers |
| :--- | :--- | :--- |
| **Data Integrity** | All numerical values match raw prompt inputs exactly. | Model alters raw numbers, omits data points, or introduces external values. |
| **Logic & Calculation** | Multi-step calculations execute sequentially; intermediate sums match final output. | Model leaps to a final calculation that contradicts preceding step logic. |
| **Instruction Following** | Output strictly adheres to requested schemas (tables, bullet points, JSON). | Model includes conversational preamble, filler text, or ignores structural rules. |
| **Constraint Adherence** | Respects hard boundary conditions (e.g., "calculate using only data provided"). | Model uses external knowledge baselines when explicitly instructed not to. |

## 4. Mandatory Verification Protocol
1. Evaluators must independently calculate all mathematical outputs using an external verification tool (e.g., Python environment or manual verification script).
2. Evaluators must log the exact step where calculation or reasoning drift occurred if marking a task as **Fail**.
