# Section 0 — Project Framing & Application Scope Checkpoint

* **Problem Evidence:** High return rates in e-commerce categories erode net profitability due to reverse logistics expenses (`Return_Cost`), while unnecessary reverse shipping increases carbon emissions (`CO2_Saved`) and physical waste (`Waste_Avoided`) (Source: E-Commerce Reverse Logistics Benchmark Report & Sustainable Supply Chain Guidelines).
* **Existing Approaches:**
  1. Static Rule-Based Return Portals — Approve claims based solely on fixed day windows without evaluating profit/loss or return abuse patterns.
  2. Retroactive BI Analytics Dashboards — Track historical return rates and CO₂ metrics after losses occur, offering no real-time evaluation.
  3. Unconstrained General AI Chatbots — Prone to hallucinating return rules and unable to process structured order records accurately.
* **Project / Engineering Gap:** Current tools lack an integrated evaluation assistant that combines structured order risk/sustainability metrics with document-grounded return policy citations.
* **Objective O1:** To design an AI evaluation assistant that validates order return eligibility (`Return_Reason`, `Days_to_Return`, `Product_Category`) against official return guidelines.
* **Objective O2:** To build a RAG and risk-scoring pipeline that calculates a Return Risk Score (%), net `Profit_Loss` impact, and `CO2_Saved` / `Waste_Avoided` metrics.
* **Objective O3:** To evaluate the system on accuracy, citation grounding, latency, and demographic fairness across 20 test return scenarios.
* **Intended Users:** E-commerce operations managers, retail sellers, and supply chain/sustainability analysts.
* **Supported Tasks:** Scoring return likelihood/risk, checking return window and reason compliance, estimating financial and environmental return impact, and citing policy clauses.
* **Information / Knowledge Domain:** E-commerce return & refund policy documents, reverse logistics sustainability guidelines, and historical order/return records.
* **Operating Context:** Operates as an automated background evaluation assistant within an e-commerce order management workflow.
* **Important Constraints:** Must rely only on synthetic/anonymized data (`returns_sustainability_dataset.csv`) without real customer PII, and must ground policy explanations in indexed PDFs.
* **Explicit Out-of-Scope Tasks:** The system SHALL NOT process payment refunds directly, provide legal counsel for consumer disputes, or alter live inventory databases.
* **Evaluation Focus:** Verifying whether the system accurately predicts return risk, correctly calculates financial/CO₂ impact, avoids demographic bias, and cites valid policy clauses.
