# Week 3 Pipeline Decisions & Stage Contracts — Beware

## Part B Preparation Comparison & Trade-Offs

| Pathway | Approach / Configuration A | Approach / Configuration B | Observed Evidence | Selected Approach and Trade-Off |
| :--- | :--- | :--- | :--- | :--- |
| **Pathway A (PDF Policy)** | Fixed-size character chunking (`size=500`) | Paragraph-aware character chunking (`size=500`) | Fixed chunking splits mid-sentence across return window clauses, whereas paragraph-aware chunking keeps complete policy rules intact within 500-character blocks. | **Selected: Paragraph-aware (`size=500`)** to preserve policy rule context for FR2/RAI4 citations. *Trade-off:* Basic whole-document splitter sets `page: None` rather than preserving PDF page numbers. |
| **Pathway B (Tabular CSV)** | Raw uncleaned CSV (`returns_sustainability_dataset.csv`) | Deduplicated and whitespace-trimmed CSV (`remove_duplicates=True`, `trim_text=True`) | Input has 5,000 rows and 23 columns with 0 exact duplicates and 0 missing values. String trimming standardizes categorical labels (`Product_Category`, `Return_Status`, `Return_Reason`) while preserving all 5,000 rows. | **Selected: Deduplication + String Trimming** to guarantee clean category grouping for FR1/FR4 without altering target values or leaking train/test statistics. *Trade-off:* Synthetic flat `Return_Cost = 200` is retained as-is and flagged for Topic 4 review. |

---

## Engineering Architecture & Traceability

- **Linked Topic 2 Requirements:** `FR1` (Return Risk Score), `FR2` (Policy Eligibility Verification), `FR4` (Net `Profit_Loss` and `CO2_Saved`/`Waste_Avoided` Metrics), `RAI1` (Demographic Parity `<= 5%`), and `RAI4` (Citation Grounding).
- **ETL vs. ELT Decision:** **ETL (Extract, Transform, Load)** — Raw CSV and PDF files are extracted, cleaned, chunked, and validated in Python before writing structured artefacts (`prepared_table.csv` and `prepared_text.jsonl`) to storage.
- **Batch vs. Streaming Rationale:** **Batch Processing** — Both the 5,000-row historical dataset and policy PDFs are static files processed reproducibly per version run rather than live event streams.
- **Output Locations:**
  - Part B Prepared Artefacts: `data/processed/prepared_text.jsonl` and `data/processed/prepared_table.csv`
  - Part B Common Lineage Manifest: `data/week3_manifest.json`
  - Part C Executable Pipeline Outputs: `data/pipeline_v1/documents/` and `data/pipeline_v1/tabular/`
- **Provenance / Access Caveat:** Dataset S01 is synthetic (flat simulated logistics cost of 200) and covers orders up to `2025-09-03`. Demographic columns (`User_Age`, `User_Gender`, `User_Location`) remain in the prepared table strictly for RAI1 parity checks and must be dropped prior to model training.

---

## Stage Contracts & Failure Responses

| Stage | Contract / Evidence | Failure Response |
| :--- | :--- | :--- |
| **Ingest** | `returns_sustainability_dataset.csv` and `return_policy_guidelines.pdf` exist under `data/raw/` and are readable. | Raise `FileNotFoundError` and halt execution if either source file is missing. |
| **Inspect** | CSV loads as non-empty DataFrame `(5000, 23)` with expected columns; PDF extracts non-empty character text. | Raise `ValueError` and stop pipeline if table is empty or PDF yields zero extractable text. |
| **Prepare** | Pathway A outputs paragraph-aware 500-char chunks; Pathway B trims string columns and checks duplicates. | Stop and report transformation failure if chunk list or prepared DataFrame is empty. |
| **Validate** | `prepared_text.jsonl` and `prepared_table.csv` exist, have byte size `> 0`, and match expected record counts. | Assert failure and block manifest creation if output files are missing, empty, or corrupted. |
| **Record Lineage** | Source and output SHA-256 checksums, processing configurations, and mappings are written to `week3_manifest.json` and `pipeline_manifest.json`. | Raise checksum or count mismatch error in Cell 6B / Cell 9 if any file fingerprint changes. |
