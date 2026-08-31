---
name: ai-answer-accuracy-auditor
description: Audits factual claims and editorial framing about a brand across AI answers, traces likely source-of-truth failures, and produces a prioritized correction ledger. Use when ChatGPT, Gemini, Claude, Perplexity, Copilot, or AI Overviews describes a company, product, price, feature, limitation, or comparison incorrectly.
---

# AI Answer Accuracy Auditor

## Research basis

This skill operationalizes Profound's research, [The Parrot Problem: Why AI Search has a second dimension marketers can't ignore](https://www.tryprofound.com/blog/the-parrot-problem), published June 25, 2026.

Key takeaways from the study:

- Across 50,000 prompts, about 47% of response content was unsolicited editorial material such as comparisons, rankings, caveats, and recommendations.
- A brand can be visible while still being described inaccurately or framed poorly.
- Specific, current, verifiable first-party facts give answer engines stronger material than generic marketing claims.
- Profound recommends recurring claim audits, source-of-truth updates, and human-reviewed correction workflows.

Treat these findings as observational evidence, not universal model behavior. Record engine, model or surface, locale, prompt, and capture date for every answer.

## Goal

Find material claims about a brand, verify them against current evidence, diagnose where errors originate, and recommend the smallest legitimate correction.

## Intake

Ask only for missing inputs that block the audit:

- brand and canonical domain
- products or services in scope
- engines, markets, and languages
- captured AI answers or permission to research them
- current product documentation, pricing, policies, and approved claims
- competitors and high-risk topics

Never treat the brand's preferred wording as proof. Use official product material for first-party facts and reliable independent sources for external claims.

## Workflow

1. Define the audit cohort by engine, market, language, prompt family, and date.
2. Extract every decision-relevant claim, including unsolicited editorial claims.
3. Label each claim: requested fact, comparison, recommendation, ranking, caveat, price, availability, compatibility, limitation, or sentiment.
4. Verify the claim against the strongest current source available.
5. Classify the result:
   - accurate and current
   - accurate but incomplete
   - ambiguous
   - stale
   - false
   - subjective framing
   - unverifiable
6. Trace the likely source: owned page, documentation, feed, profile, third-party publisher, community page, or unknown.
7. Score severity using decision impact, exposure, confidence, and correction difficulty.
8. Fix the source of truth before proposing cosmetic rewrites.
9. Define a retest cohort and observation window.

Do not fabricate corrections, manipulate Wikipedia, astroturf communities, or pressure publishers to remove legitimate criticism.

## Severity

- **Critical:** safety, legal, eligibility, price, availability, or compatibility errors that can materially harm a decision.
- **High:** false comparisons, wrong limitations, or stale product facts in important prompt clusters.
- **Medium:** incomplete or misleading framing with plausible decision impact.
- **Low:** stylistic sentiment or immaterial wording.

## Output

Return:

1. Executive finding: accuracy rate, highest-risk narrative, and primary source-of-truth problem.
2. Claim ledger with engine, prompt, claim, type, verdict, evidence, likely source, severity, and owner.
3. Source correction plan with exact facts and canonical destinations.
4. Third-party correction plan limited to factual, evidence-backed outreach.
5. Retest plan using the same prompt cohort plus controlled variants.
6. Unknowns and limitations.

Never promise that correcting a source will change an AI answer. Report observed movement over time.
