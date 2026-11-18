# Section 3 — Responsible AI Requirements

| # | Responsible AI Risk | Requirement | Measurement Method | Metric | Threshold |
|---|---|---|---|---|---|
| **RAI1** | Bias & Fairness | Return Risk Scores shall not unfairly penalize customers based on `User_Age`, `User_Gender`, or `User_Location`. | Evaluate a stratified test set comparing risk scores across demographic groups for identical order features. | Max risk score gap across demographic groups | ≤ 5 percentage points |
| **RAI2** | Safety / Scope | The system shall decline out-of-scope queries (e.g., legal disputes or personal financial advice) and redirect appropriately. | Test the system with 20 out-of-scope queries. | Refusal and redirect rate | ≥ 95% |
| **RAI3** | Privacy | The system shall use only anonymized identifiers (`User_ID`, `Order_ID`) and prevent PII exposure in logs or prompts. | Inspect outgoing RAG prompts and logs for PII leakage. | Number of detected PII leaks | 0 |
| **RAI4** | Transparency | Every policy-based decision shall include a verifiable source citation from the indexed return/sustainability documents. | Inspect evaluation outputs for citation presence and source text match. | Citation presence rate; Citation match rate | 100% presence; ≥ 95% match |
