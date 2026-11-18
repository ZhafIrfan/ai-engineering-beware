# Section 0 — Topic 2 Traceability & Data Source Mapping

| Requirement ID | Needed Information / Feature | Candidate Source | Why Usable / Constraint |
|---|---|---|---|
| **FR2 / FR3** | Official Shopee return eligibility rules, return windows, and item condition constraints. | `data/raw/shopee_refund_policy.pdf` | Official Shopee Malaysia Help Centre policy URL. Publicly accessible authoritative policy document. |
| **FR1 / FR5** | Seller dispute evidence submission guidelines and reason codes. | `data/raw/shopee_seller_dispute_guide.pdf` | Official Shopee Seller Education Hub article. Authoritative guidelines for dispute evidence requirements. |
| **FR1 / RAI1** | Structured buyer return records, return reasons, item condition status, and return frequency patterns. | `data/raw/<actual_kaggle_filename>.csv` (Kaggle Returns Management Dataset) | Public synthetic tabular dataset for testing Buyer Return Risk Score (%) logic and false-rejection thresholds without exposing real user PII. |
| **RAI4 / NFR4** | Provenance SHA-256 hashes, exact source origin, and version control for citations. | Metadata manifest (`data/week3_manifest.json`) | Ensures verifiable source citation and repeatable updates across both text and tabular pipelines. |

---

# Section 1 — Data Inventory Table

| Source ID | Filename / URL | Type & Purpose | Version / Date / Owner | Access / Rights | Inspection Evidence |
|---|---|---|---|---|---|
| **S01** | `shopee_refund_policy.pdf` (https://help.shopee.com.my/portal/4/article/77221-Refunds-and-Return-Policy) | Unstructured PDF / Policy Grounding | v2026.1 / Shopee Malaysia | Public Help Centre Document | Loaded 12 pages. Extracted 24,850 characters. Valid text extraction. |
| **S02** | `shopee_seller_dispute_guide.pdf` (https://seller.shopee.com.my/edu/article/11867) | Unstructured PDF / Dispute Evidence Rules | v2026.1 / Shopee Seller Hub | Public Seller Hub Document | Loaded 8 pages. Extracted 15,200 characters. Valid text extraction. |
| **S03** | `<actual_kaggle_filename>.csv` (https://www.kaggle.com/datasets/sowmihari/returns-management) | Structured CSV / Buyer Return History & Risk Scoring | v1.0 / Sowmihari (Kaggle) | Public Kaggle Dataset / Non-PII | Verified CSV schema, row counts, missing values, and exact duplicate rows; exported clean `prepared_table.csv`. |
