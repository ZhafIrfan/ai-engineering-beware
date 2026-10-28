# Architecture Decision Record (ADR)

### Decision 1: Include Document Retrieval (RAG Knowledge Access Component)
* **Requirement / Constraint:** FR3 / RAI4 (Answers must be grounded in official Shopee documents with exact citations).
* **Alternatives Considered:** 
  1. Base LLM internal knowledge only
  2. Hardcoded rule-based decision trees
  3. Dynamic Knowledge Access Component (RAG)
* **Selected Option:** Dynamic Knowledge Access Component (RAG).
* **Trade-off Accepted:** Adds system complexity and index management overhead, but guarantees accurate grounding and eliminates hallucinated policies.

### Decision 2: Include Background Scope & Safety Control
* **Requirement / Constraint:** RAI2 / RAI3 (Out-of-scope queries must be refused; PII must be protected).
* **Alternatives Considered:** 
  1. System prompt instructions only
  2. Explicit Scope / Safety Control Component
* **Selected Option:** Explicit Scope / Safety Control Component.
* **Trade-off Accepted:** Small latency penalty for pre-screening inputs, but prevents out-of-scope legal advice and protects user privacy.

---

# Initial Requirements Traceability Matrix

| Objective | Requirement | Evaluation Criterion | Architecture Element | Later Evidence |
|---|---|---|---|---|
| **O1** | **FR2** | Policy Decision Accuracy | Shopee Policy Knowledge Base | Test set evaluation matching claim conditions to policy clauses. |
| **O2** | **FR1 / RAI4** | Risk Score Calibration & Citations | AI Evaluation Assistant Engine | Risk score accuracy report and citation verification logs. |
| **O3** | **NFR1 / RAI2** | Response Latency & Safety Refusal | Scope / Safety Control & Pipeline | Latency benchmark logs (< 3s) and out-of-scope test suite results. |

---
