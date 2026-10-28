# Section 0 — Project Framing & Application Scope Checkpoint

* **Problem Evidence:** Buyers select false return reasons to avoid paying return shipping fees, leaving sellers to cover costs (Source: Shopee Seller Education Hub — Return & Refund Shipping Fee Policy Guidelines). Merchants also suffer inventory loss from return fraud, item swapping, and auto-approved refunds executed before sellers can verify returned items (Source: E-Commerce Merchant Return Fraud Industry Reports).
* **Existing Approaches:** 
  1. Standard Shopee Return Request Flow — Auto-approves many claims without verifying if the item is opened/used or checking buyer return history.
  2. Static Rule-Based Account Blocking — Treats all returning buyers the same, failing to distinguish fair defect claims from return abuse.
  3. Unconstrained General AI Chatbots — High hallucination risk and lacks grounded knowledge of official marketplace return terms.
* **Project / Engineering Gap:** Existing systems lack an automated gatekeeper that checks real-time buyer condition inputs and historical return reason patterns against official policy text to generate an auditable Buyer Risk Score (%).
* **Objective O1:** To design an AI evaluation system that verifies item return eligibility (new/unused state) and tracks buyer return reason history.
* **Objective O2:** To build a scoring algorithm and RAG pipeline that computes a Buyer Return Risk Score (%) grounded in official marketplace policies.
* **Objective O3:** To evaluate the system on catching fraudulent return requests, answer accuracy, and safety across 20 test buyer claim scenarios.
* **Intended Users:** Shopee sellers, marketplace risk control managers, and automated return processing systems.
* **Supported Tasks:** Verifying item return condition rules, calculating buyer return abuse risk scores, retrieving official Shopee policy clauses, and flagging/blocking high-risk return claims.
* **Information / Knowledge Domain:** Shopee Malaysia Buyer Refund and Return Policies, Seller Dispute & Evidence Submission Guides, and Return Eligibility Guidelines.
* **Operating Context:** Embedded directly into the e-commerce return request pipeline as an automated background risk check.
* **Important Constraints:** Must operate without introducing complex chat steps for buyers, relies on unstructured public policy documents, and must not store unanonymized personal data.
* **Explicit Out-of-Scope Tasks:** The system SHALL NOT process financial payouts directly, mediate non-return customer service inquiries, or provide legal advice for court disputes.
* **Evaluation Focus:** Determining whether the system accurately identifies fraudulent/unsupported return claims, correctly calculates risk scores, and grounds every decision in official policy clauses without hallucinations.

---
