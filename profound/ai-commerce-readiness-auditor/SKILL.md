---
name: ai-commerce-readiness-auditor
description: Determines whether AI shopping surfaces are relevant to a product category and audits the product data, merchant information, pricing, availability, offers, and evidence needed for reliable inclusion. Use for ChatGPT Shopping or other agentic-commerce readiness work.
---

# AI Commerce Readiness Auditor

## Research basis

This skill operationalizes Profound's research, [We reverse-engineered ChatGPT's Shopping trigger](https://www.tryprofound.com/blog/chatgpt-shopping-prediction), published March 17, 2026.

Key takeaways from the study:

- Product category was a stronger Shopping trigger than purchase-intent wording.
- Physical consumer products activated Shopping far more often than software, services, travel, or financial products.
- Commercial intent amplified activation within eligible product categories but was not sufficient by itself.
- Product constraints helped only after the category was plausibly eligible.

The study reports historical observational behavior, not an official OpenAI specification. Verify current merchant and feed requirements using official platform documentation.

## Goal

Decide whether an AI commerce surface deserves investment, then find the data and content gaps that could prevent accurate product inclusion or merchant routing.

## Eligibility gate

Before auditing details, classify the offering:

- shippable consumer product
- consumable or grocery
- large equipment or vehicle
- software or digital product
- service
- travel or hospitality
- financial or telecom product
- local-only offering

If the surface rarely activates for the category, state that clearly and redirect effort to ordinary AI recommendations or another commerce surface.

## Workflow

1. Define target product categories, markets, engines, and commercial prompt families.
2. Test whether the shopping surface activates using repeated representative prompts.
3. Separate three outcomes:
   - product inclusion
   - headline merchant or offer
   - all available merchants or offers
4. Audit product data:
   - canonical title and description
   - brand and identifiers
   - category and attributes
   - variants, size, color, and compatibility
   - images
   - price, currency, sale status, and availability
   - shipping, returns, and merchant policies
   - reviews and current evidence
5. Compare feeds, product pages, structured data, merchant records, and marketplaces for conflicts.
6. Check freshness and update latency.
7. Identify recommendation gaps across use cases, constraints, comparisons, and "best for" framing.
8. Prioritize data correctness before editorial optimization.
9. Retest over multiple runs because cards and merchant offers can vary.

Never fabricate reviews, ratings, availability, discounts, or product claims.

## Output

Return:

1. Surface-fit decision: invest, test narrowly, or deprioritize.
2. Activation evidence by prompt family.
3. Product-data readiness scorecard.
4. Conflict ledger across feeds, pages, and merchants.
5. Priority fixes with source system, owner, and freshness requirement.
6. Recommendation-content opportunities supported by real product evidence.
7. Measurement plan for inclusion consistency, headline-offer share, all-offer share, and downstream outcomes.
