---
name: ai-search-attribution-planner
description: Designs measurement for AI mentions, delayed brand visits, assisted conversions, and business outcomes beyond direct referral clicks. Use when proving AEO impact, building analytics requirements, setting KPIs, or explaining why AI visibility does not match referral traffic.
---

# AI Search Attribution Planner

## Research basis

This skill operationalizes Profound's research, [The AI mention effect](https://www.tryprofound.com/blog/the-ai-mention-effect), published July 1, 2026.

Key takeaways from the study:

- Profound joined more than two million privacy-safe AI conversations with downstream browsing behavior.
- After an AI assistant introduced a brand, users visited its site above their forecast baseline during the following seven days.
- Only 42% of downstream visits occurred within 24 hours; a same-session window misses much of the behavior.
- More than 97% of measured downstream visits lacked a trackable AI-referral parameter, even after ChatGPT made links more clickable.

The study was observational, US-only, and measured site visits rather than purchases. Do not present its aggregate lift as a causal forecast for an individual brand.

## Goal

Measure AI search as an influence channel using direct, assisted, delayed, and self-reported evidence while keeping causal claims proportional to the design.

## Measurement layers

- **Exposure:** brand mention, recommendation, prominence, sentiment, and citation.
- **Immediate behavior:** direct referral, click, landing page, and engaged session.
- **Delayed behavior:** branded search, direct visit, return visit, and cross-session conversion.
- **Business outcome:** signup, lead, qualified pipeline, purchase, revenue, retention, or support deflection.

Keep these layers separate. A visibility increase is not automatically a revenue increase.

## Workflow

1. Define the decision the measurement must support.
2. Specify exposure by engine, prompt cohort, market, language, and date.
3. Audit current referral tagging and analytics classification.
4. Preserve known AI referrals, landing pages, query parameters, and referrers.
5. Add assisted indicators:
   - branded search movement
   - direct and organic visits to exposed pages
   - one-hour, 24-hour, and seven-day windows
   - self-reported attribution
   - CRM notes and sales-call evidence
6. Choose an evaluation design:
   - pre/post with stable cohort
   - matched market or page comparison
   - holdout when feasible
   - interrupted time series
   - exposure panel or incrementality study
7. Identify confounders such as campaigns, seasonality, launches, press, and platform changes.
8. Connect metrics to business outcomes without double counting.
9. Document privacy, consent, retention, and minimum aggregation requirements.
10. Report uncertainty and alternative explanations.

## Output

Return:

1. Measurement objective and causal confidence level.
2. Funnel from AI exposure to business outcome.
3. Event and property specification.
4. Attribution-window recommendation.
5. Dashboard metrics split into exposure, immediate, delayed, and business layers.
6. Experiment or quasi-experiment design.
7. Confounder and privacy checklist.
8. Reporting language that distinguishes observation, association, and causation.
