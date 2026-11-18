# Section 2 — Non-Functional Requirements

| # | Quality Attribute | Requirement | Measurement Method | Metric | Threshold |
|---|---|---|---|---|---|
| **NFR1** | Performance | The system shall evaluate order return records and generate risk/sustainability outputs within the latency target. | Measure end-to-end processing time across 20 test order records. | p90 latency | < 3,000 ms |
| **NFR2** | Correctness | Policy compliance decisions and risk classifications shall match ground-truth evaluation labels. | Score a curated evaluation set of 20 order scenarios using a defined rubric. | Correct evaluation rate (%) | ≥ 85% |
| **NFR3** | Reliability | The evaluation pipeline shall process batch and single-order inputs without runtime failures. | Run repeated pipeline execution checks on the dataset. | Successful execution rate (%) | ≥ 99% |
| **NFR4** | Maintainability | New policy PDFs or updated return datasets shall be indexed without modifying core application code. | Run a controlled document/data update test. | Update re-indexing time | < 10 min |
