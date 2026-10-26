# Project Scope — Beware

**Project Name:** Beware  
**Domain:** E-commerce / Seller Operations & Dispute Management  

## Problem Statement
Shopee sellers face unfair inventory loss and shipping costs due to return abuse, fake claims, and auto-refunds. Beware provides instant, document-grounded dispute advice and evidence preparation 24/7.

## Evidence of the Problem
- **Evidence 1:** Buyers select false return reasons so sellers pay return shipping fees upfront.
  - *Source / Citation:* Shopee Seller Community Discussions & Merchant Feedback.
- **Evidence 2:** Sellers suffer direct inventory loss from product swapping and unverified auto-approved refunds.
  - *Source / Citation:* Shopee Seller Center Return & Refund Policy Documentation.

## Initial Related Work (at least 3)
- **Study / Solution 1:** Shopee Official Support
  - *Source / Citation:* Shopee Customer Service Portal
  - *Key Limitation:* Responses are slow and use generic, static templates.
- **Study / Solution 2:** Seller Community Forums
  - *Source / Citation:* Facebook Seller Groups & E-commerce Forums
  - *Key Limitation:* Advice is unverified and sellers often miss strict appeal deadlines.
- **Study / Solution 3:** General-Purpose AI Assistants
  - *Source / Citation:* Standard ChatGPT / Claude base models
  - *Key Limitation:* Flexible, but not grounded in official, up-to-date Shopee Malaysia policies.

## Engineering Gap / Limitation
Existing approaches are slow, rely on unverified advice, or fail to ground dispute recommendations consistently in official marketplace seller documents.

## Initial Project Objectives
- **O1:** Design a document-grounded AI seller dispute solution based on official marketplace documents.
- **O2:** Develop the proposed solution with retrieval and appropriate guardrails.
- **O3:** Evaluate the solution in terms of answer quality, groundedness, latency, and safety.

## Target Users
Shopee Malaysia sellers, small e-commerce store owners, and customer support staff.

## Data Sources (at least 2)
- **Source 1:** Shopee Terms of Service: Refunds & Return Policy (Shopee Help Centre)
  - *URL:* https://help.shopee.com.my/portal/4/article/77221-Refunds-and-Return-Policy
- **Source 2:** Shopee Seller Dispute & Evidence Guide (Shopee Seller Hub)
  - *URL:* https://seller.shopee.com.my/edu/article/11867
- **Source 3:** Shopee Return Eligibility Guidelines (Shopee Help Centre)
  - *URL:* https://help.shopee.com.my/portal/4/article/78496

## Similar to EduAdvisor
- Both use a RAG (Retrieval-Augmented Generation) architecture to answer queries grounded in official, static domain documents.
- Both enforce guardrails to prevent hallucinations and unsafe/out-of-scope outputs.

## Different from EduAdvisor
- Target domain is e-commerce risk/dispute management instead of higher education academic advising.
- Focuses on evidence collection, timeline-sensitive seller appeals, and financial risk reduction rather than course registration.

## Responsible AI Risks (at least 2)
- **Risk 1 (Hallucination):** Model invents non-existent dispute policies, causing the seller to submit invalid appeal evidence and lose the case.
- **Risk 2 (Safety / Policy Misinterpretation):** System provides advice encouraging fraudulent counter-claims or hostile buyer interactions.
- **Risk 3 (Latency / Outdated Data):** Delayed response or reliance on outdated Shopee policy documents leads to missed appeal submission windows.
