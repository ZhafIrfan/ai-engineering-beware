# Beware — AI-Powered E-Commerce Return Risk & Sustainability Assistant

> Evaluates e-commerce order return likelihood, financial profit/loss impact, and CO₂/waste reduction, grounded in standard e-commerce return and reverse logistics guidelines.

## Problem Statement
Online retailers lose significant profit margins and generate avoidable packaging waste due to high product return rates and late return claims. Existing return workflows approve claims blindly without evaluating order risk patterns, financial loss impact, or policy compliance. Beware acts as an automated background assistant that scores return risk, estimates profit/loss and environmental impact, and cites standard return policy rules.

## Evidence of the Problem
- High return rates in e-commerce categories such as clothing and electronics directly erode net order profitability through reverse logistics costs (Source: E-Commerce Reverse Logistics & Returns Industry Benchmark Report).
- Unchecked product returns generate substantial carbon emissions and physical landfill waste from repackaging and shipping (Source: Sustainable E-Commerce & Circular Supply Chain Guidelines).

## Initial Related Work / Existing Approaches
- **Static Rule-Based Return Portals** — Automatically approve returns within a fixed day window, failing to account for customer return history, discount abuse, or profit/loss thresholds.
- **Standalone BI Dashboards (Power BI/Tableau)** — Visualize past return rates and CO₂ metrics retroactively, but do not evaluate active return claims in real time.
- **Unconstrained General AI Assistants** — Can summarize return rules, but lack grounded access to structured order metrics and hallucinate policy thresholds.

## Engineering Gap / Limitation
Existing approaches separate historical financial/sustainability analytics from active return policy checking, lacking a unified AI assistant that scores return risk while citing verified return and sustainability guidelines.

## Project Objectives
- **O1:** To design an AI evaluation system that analyzes order attributes, return reasons, and return windows against standard e-commerce return guidelines.
- **O2:** To develop a document-grounded RAG and tabular risk-scoring pipeline that outputs a Return Risk Score (%), financial loss estimate, and CO₂/waste impact.
- **O3:** To evaluate the system on decision accuracy, policy citation grounding, latency, and fairness across customer demographics (`User_Age`, `User_Gender`, `User_Location`).

## Target Users
E-commerce operations managers, online store owners, and sustainability/logistics analysts.

## Data Sources
- **Source 1:** Synthetic E-Commerce Returns Management Dataset (`returns_sustainability_dataset.csv`) — https://www.kaggle.com/datasets/sowmihari/returns-management
- **Source 2:** Standard E-Commerce Return & Refund Policy Guidelines (PDF)
- **Source 3:** Reverse Logistics & Sustainable Packaging Impact Report (PDF)

## Weekly Progress
| Week | Focus | Deliverable | Status |
|------|-------|-------------|--------|
| W1 | System map + project scope | `README.md` + `docs/week1_project_scope.md` | ✅ |
| W2 | Requirements, evaluation criteria, V1 architecture | `docs/week2_*.md` + `docs/week2_architecture_v1.png` | ✅ |
| W3 | Multimodal ETL pipeline (PDF RAG + Tabular CSV) | `notebooks/week3_pipeline.ipynb` + `docs/week3_*.md` | ✅ |
