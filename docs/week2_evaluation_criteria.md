# Evaluation Criteria Table — Beware

| Objective / Requirement ID | Evaluation Criterion | Capability Bucket | Measurement Method | Metric | Threshold | User / Business Outcome |
|---|---|---|---|---|---|---|
| **O3 / NFR2** | Policy Decision Accuracy | Domain-specific capability | Test 20 realistic return claim scenarios against official Shopee guidelines. | Correct evaluation rate (%) | ≥ 85% | Sellers are protected from false returns while valid buyer claims pass smoothly. |
| **O1 / FR3 / RAI4** | Policy Source Citation & Matching | Instruction-following capability | Inspect outputs for exact policy clause references and check if cited text supports the decision. | Citation presence rate; Citation match rate | 100% presence; ≥ 95% match | Evaluation results can be audited and verified against official marketplace terms. |
| **O2 / RAI2** | Out-of-Scope Refusal | Instruction-following capability | Input 20 out-of-scope queries (e.g., asking for legal sue advice or general chat). | Refusal & redirect rate | ≥ 95% | Keeps the AI focused purely on return evaluation and avoids misleading legal advice. |
| **O3 / NFR1** | Evaluation Latency | Cost and latency | Measure total processing time from return submission to risk score generation. | p90 latency | < 3,000 ms | Return claims are checked in real-time without delaying the customer experience. |
| **O2 / FR1** | Risk Score Calibration | Domain-specific capability | Compare AI-generated Buyer Risk Scores (%) against human expert risk labels on test cases. | Score correlation / Accuracy | ≥ 80% match | Creates an objective score that accurately reflects true buyer return abuse risk. |

---
