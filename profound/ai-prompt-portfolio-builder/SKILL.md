---
name: ai-prompt-portfolio-builder
description: Builds statistically useful prompt portfolios for AI visibility, citation, sentiment, and recommendation tracking. Use when selecting prompts, setting monitoring cadence, separating stable and exploratory cohorts, or diagnosing noisy AEO measurements across answer engines.
---

# AI Prompt Portfolio Builder

## Research basis

This skill operationalizes Profound's research, [Is once a day enough?](https://www.tryprofound.com/blog/is-once-a-day-enough), published July 8, 2026.

Key takeaways from the study:

- Profound compared identical portfolios run once and ten times daily across 753 prompts and seven platforms for two weeks.
- Once-daily visibility estimates landed within about two percentage points of the heavier measurement.
- Additional runs reduced citation-share noise more than visibility noise, but could not remove day-to-day platform drift.
- Prompt portfolio composition mattered more than run frequency, especially for citation share.

These results came from a large portfolio and specific setup. Small cohorts, experiments, and noisy citation questions may need repeated runs.

## Goal

Build a prompt portfolio whose composition matches the business question and whose cadence is sufficient to distinguish useful movement from noise.

## Intake

Collect:

- brand, products, audience, competitors, and business objective
- engines, models or surfaces, markets, languages, and personas
- real prompt-demand data when available
- customer research, search terms, sales calls, support questions, and category vocabulary
- monitoring budget and required decision cadence

## Portfolio design

Cover relevant intent families:

- category discovery
- problem and solution research
- comparisons and alternatives
- recommendations and "best for" decisions
- trust, risk, and validation
- pricing, availability, compatibility, and limitations
- implementation and troubleshooting
- local, shopping, or regulated intents when applicable

Do not turn every keyword into a conversational prompt. Prefer observed demand and preserve the user's natural language.

## Workflow

1. State the measurement question before selecting prompts.
2. Cluster demand by user job, intent, stage, product, audience, language, and market.
3. Assign business value and evidence quality to each cluster.
4. Select representative prompts without allowing one cluster or wording pattern to dominate.
5. Create three cohorts:
   - stable core for trend measurement
   - exploratory cohort for emerging demand
   - diagnostic controls for known outcomes
6. Add paraphrase variants only where wording sensitivity must be measured.
7. Keep engines, markets, languages, and personas as separate configurations.
8. Choose cadence:
   - default to once daily for a broad monitoring portfolio
   - add repeated runs for small samples, short experiments, or citation-share precision
9. Define minimum observation window, change-control rules, and review cadence.
10. Version the portfolio and document every addition, removal, or weighting change.

Never compare periods that used materially different portfolios without recalculating a common cohort.

## Output

Return:

1. Measurement question and scope.
2. Demand model with cluster, user job, stage, evidence, and business value.
3. Prompt portfolio with cohort, prompt, variants, engine, market, language, and rationale.
4. Coverage analysis showing over- and underrepresented clusters.
5. Cadence and sample plan.
6. Versioning rules and change log template.
7. Reporting guidance covering uncertainty, platform drift, and portfolio changes.
