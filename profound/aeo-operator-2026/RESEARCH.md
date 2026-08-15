# AEO Operator 2026 — Research, Platform Notes & Output Contracts

Snapshot: 2026-08-12

This is the single supporting knowledge file for SKILL.md. Treat numeric findings as dated dataset observations unless they come from official platform documentation. Refresh current platform mechanics before using them as present-tense facts.

## Contents

1. Evidence hierarchy and research-use rules
2. Profound research operating priors
3. Cross-platform durable findings
4. Platform playbooks
5. Myth checks
6. Reusable output contracts
7. Source index

## 1. Evidence hierarchy and research-use rules

Use evidence in this order:

1. Official engine documentation, help centers, webmaster guidance, protocols
2. Primary research / controlled experiments / platform-published datasets
3. Large observational datasets from Profound or similarly rigorous platforms
4. Expert commentary and case studies

Rules:

- Use official documentation for eligibility, crawler controls, feeds, and policy.
- Use observational research to set priors, benchmarks, experiment design, and measurement architecture.
- Never transfer a percentage into a client forecast without validating model, industry, language, geography, prompt set, and date.
- Prefer the newest relevant study when datasets conflict.
- Segment Google AI Overviews, AI Mode, and Gemini rather than collapsing them into one surface.
- Segment ChatGPT, Perplexity, Copilot, Claude, Grok, and shopping/local experiences separately.

## 2. Profound research operating priors

### 2.1 Start with the citation market, not a generic channel checklist

Finding. Profound's July 30, 2026 analysis used 11.84 billion citations across 8 models, 29 industries, and 8,061 active categories. Across the dataset, about 57% of citations were to brand/company-operated sites, but the mix varied sharply by model and industry. In 24 of 29 industries, the median Profound customer received more citations from brand/company sites than either earned or social sources. ChatGPT was less brand-site-heavy in the dataset (47%) while Gemini was much more brand-site-heavy (69%).

Operational rule. Before recommending PR, Reddit, YouTube, LinkedIn, institutional outreach, or owned-content expansion:

- calculate the current source mix
- segment by model and market
- compare it with the relevant category/industry baseline
- identify the largest addressable gap
- allocate channel effort from that gap

Source: Profound, "Where do AI citations come from?", 2026-07-30. https://www.tryprofound.com/blog/where-do-ai-citations-come-from

### 2.2 Use granular citation categories for diagnosis

Profound's citation taxonomy supports Owned, Competition, Earned Media, PR Wire, Institution, Social, Other, and Custom. A strategic roll-up can group these into brand/company, earned/institutional, and social/UGC.

Use the granular layer to diagnose the gap and the roll-up for executive investment decisions.

Source: Profound, "Who Shapes AI Answers? Introducing Enhanced Citation Categories", 2026-01-08. https://www.tryprofound.com/blog/enhanced-citation-categories

### 2.3 Prompt portfolio design matters more than brute-force repetition

Finding. Profound compared the same 753 prompts across 7 U.S. platforms at 1x/day versus 10x/day for two weeks (5,271 configurations). For large portfolios, once-daily measurement was close to 10x/day for visibility; citation share benefited more from repetition, but prompt-portfolio composition remained a major source of variance.

Operational rule. Keep a stable core portfolio, build it from real demand when possible, and add exploratory prompts separately. Use more same-day repetition for small cohorts, experiments, or noisy citation-share questions rather than as the default.

Source: Profound, "Is once a day enough?", 2026-07-08. https://www.tryprofound.com/blog/is-once-a-day-enough

### 2.4 Prefer real user demand when building prompt sets

Profound Prompt Research uses a large corpus of real user prompts rather than marketer-created keyword-to-prompt transformations. Operationally, cluster real prompts by intent, audience, stage, product/category, platform, locale, and business value.

Source: Profound, "Introducing Prompt Research Reports in Profound", 2026-06-25. https://www.tryprofound.com/blog/introducing-prompt-research-reports-in-profound

### 2.5 ChatGPT citations concentrate toward the beginning of research journeys

Profound analyzed 700K+ U.S. English ChatGPT conversations from Q4 2025 and found web citations were much more common in opening turns than deep follow-ups, with cited turns often triangulating multiple sources. The study also found recurring co-citation clusters.

Operationally, weight first-question/research-opening prompts and map source neighborhoods rather than treating each citation as isolated.

Source: Profound, "How ChatGPT sources the web", 2026-02-03. https://www.tryprofound.com/blog/chatgpt-citation-sources

### 2.6 Query fan-out changes the unit of optimization

Finding. Profound tracked 10,000 prompts across ChatGPT, Perplexity, and Copilot over 14 days. All three generated roughly 1.4-2 searches per prompt execution, but repeatability differed sharply. In that dataset, 91% of ChatGPT search queries were unique across repeated runs of the same prompt, versus 14% for Perplexity and 47% for Copilot. Fan-outs often became direct fact-retrieval queries even when the original user prompt was advisory or comparative.

Operational rule. Optimize an intent/fact family, not one literal prompt. Map entities, constraints, freshness cues, standards, reviews, locations, evidence, and comparison criteria that retrieval systems may seek.

Source: Profound, "What AI engines actually search for and why ChatGPT never searches the same way twice", 2026-04-30. https://www.tryprofound.com/blog/what-ai-engines-actually-search-for

### 2.7 Citation volatility makes screenshots weak evidence

Profound's 2025 citation-drift work found substantial month-over-month source changes across AI platforms. Use stable cohorts, trend windows, and engine-specific baselines; distinguish normal platform drift from intervention effects.

Source: Profound, "AI Search Volatility: Why AI search results keep changing", 2025-07-17. https://www.tryprofound.com/blog/ai-search-volatility

### 2.8 Model and language segmentation are mandatory

Profound's April 2026 study analyzed 3.25 billion citations across 7 models and 14 countries and found materially different social-source rates by model and query language. Do not use U.S./English source mix as a global benchmark.

Source: Profound, "How query language reshapes AI citations", 2026-04-21. https://www.tryprofound.com/blog/how-query-language-reshapes-ai-citations

### 2.9 Google AI surfaces behave differently

Profound tracked 15,155 brand configurations in May 2026 and reported a median 8-point visibility gap between a brand's best and worst Google AI surface. Gemini, AI Overviews, and AI Mode should therefore be measured separately.

Source: Profound research index, "Variability of Google models: Gemini vs AIO vs AI Mode", 2026-07-14. https://www.tryprofound.com/blog/research

### 2.10 Visibility is not enough; framing is a separate dimension

Profound's Parrot Problem / FactCheck research analyzed 50,000 responses and found roughly 47% of response content was unsolicited editorial material in that dataset. Models do more than repeat sourced facts: they compare, summarize, recommend, caveat, rank, and infer.

Operationally, maintain a claim ledger for prices, compatibility, availability, "best for" labels, comparisons, downsides, limitations, and stale facts. Fix the source of truth first.

Sources:

- https://www.tryprofound.com/blog/the-parrot-problem
- https://www.tryprofound.com/blog/introducing-factcheck

### 2.11 Make brand facts concrete enough to retrieve and verify

Prefer concrete, falsifiable claims over vague superiority language. State named integrations, supported use cases, dates, prices, limits, benchmarks, methodology, compatibility, geography, and versioning when true and useful. Vague owned copy gives models more room to interpolate.

Source: Profound, content optimization guidance. https://www.tryprofound.com/articles/optimize-content-for-ai-search

### 2.12 The shortlist can influence purchase decisions

Profound's 2026 shortlist research studied real product-comparison behavior inside ChatGPT and found strong links between repeated brand appearance and user choice. Treat recommendation inclusion, prominence, "best for" framing, price, and downsides as distinct decision variables—not just mentions.

Source: Profound, "The shortlist is the new shelf", 2026-07-14. https://www.tryprofound.com/blog/the-shortlist-is-the-new-shelf

### 2.13 Direct referral traffic undercounts AI's business effect

Profound's AI Mention Effect research found downstream brand-site visitation can increase after AI brand exposure even when only a small subset of those visits are directly identifiable as AI referrals. Use this as a reason to instrument assisted and delayed effects, not as proof of causality for a specific client.

Source: Profound, "The AI mention effect", 2026-07-01. https://www.tryprofound.com/blog/the-ai-mention-effect

### 2.14 Social strategy is category/model/language specific

Do not default to Reddit, YouTube, or LinkedIn. Use the citation mix of the target category, engine, and language to identify which social or UGC surfaces materially influence answers.

Sources:

- https://www.tryprofound.com/blog/the-data-on-reddit-and-ai-search
- https://www.tryprofound.com/blog/linkedin-is-the-most-cited-domain-for-professional-queries-in-ai-search

### 2.15 Commerce is a separate AEO system

Profound's ChatGPT Shopping studies indicate that shopping activation is strongly category-dependent and that product/offer carousels can be volatile across repeated runs. Track product inclusion separately from merchant routing, headline offer share, and total offer share. Do not treat one carousel as a stable rank.

Sources:

- https://www.tryprofound.com/blog/chatgpt-shopping-prediction
- https://www.tryprofound.com/blog/chatgpt-retail-target-walmart

### 2.16 Profound metric stack

**Demand**

- Prompt Volumes / real-user demand
- intent/topic cluster
- audience / locale / platform

**Visibility**

- Visibility / mention rate
- Share of Voice
- Mention Position / prominence
- recommendation presence

**Citation influence**

- Citation Share
- cited pages/domains
- citation categories/source mix
- Co-citation Share
- competitor source overlap

**Narrative**

- sentiment
- factual accuracy
- co-mentions
- comparisons / "best for"
- prices / caveats / downsides

**Retrieval + technical**

- Query Fanouts / grounding queries
- Agent Analytics / bot visits
- indexation/accessibility
- page freshness

**Business**

- Human Referrals
- assisted visits/conversions
- self-reported attribution
- pipeline/revenue
- shopping/product inclusion metrics

### 2.17 Profound product/data hooks useful in an AEO practice

Use these when the user has Profound access or equivalent data:

- Profound Index: Visibility / Share of Voice / Citation Share benchmarking
- Pages: page-level citations, citation rank, bot activity, and page health; useful for distinguishing discoverability problems from citation-selection/content problems
- FactCheck: claim-level accuracy and source tracing
- Prompt Volumes / Prompt Research: demand-informed portfolio construction
- Query Fanouts: retrieval-path diagnosis
- Agent Analytics: crawler/bot observability
- MCP / Agents: automate recurring reports, competitor/page checks, and intervention workflows when available

Sources:

- https://www.tryprofound.com/blog/introducing-the-profound-index
- https://www.tryprofound.com/blog/one-command-center-for-your-contents-performance
- https://www.tryprofound.com/blog/introducing-factcheck
- https://www.tryprofound.com/resources/webinars/an-inside-look-at-profound-s-mcp-with-emily-kramer

## 3. Cross-platform durable findings

### 3.1 AEO is a multi-stage pipeline, not a single ranking problem

A useful operating model is: access/indexing -> retrieval -> citation -> brand mention -> narrative/recommendation -> business outcome.

A failure at one layer should not automatically trigger a content rewrite at another.

### 3.2 Google search fundamentals remain foundational

Use current Google Search documentation for crawlability, indexing, snippet eligibility, structured data, canonicals, and content quality. Treat "special AEO markup" or llms.txt as unsupported unless Google explicitly changes its guidance.

Official source: https://developers.google.com/search/docs/appearance/ai-features

### 3.3 ChatGPT Search access has its own crawler controls

Use current OpenAI guidance for OAI-SearchBot, search visibility, referrals, and shopping. Do not conflate search crawler controls with training controls.

Official sources:

- https://help.openai.com/en/articles/12627856-publishers-and-developers-faq
- https://help.openai.com/en/articles/11128490-improved-shopping-results-from-chatgpt-search

### 3.4 Perplexity robots controls are platform-specific

Check current Perplexity documentation for crawler behavior and robots directives rather than assuming historical behavior remains true.

Official source: https://docs.perplexity.ai/guides/bots

### 3.5 Bing/Copilot exposes AI citation signals

Use current Bing Webmaster Tools AI Performance reporting when available for citations, cited pages, and grounding-query insights; use IndexNow for relevant URL updates.

Official source: https://blogs.bing.com/webmaster/February-2026/Introducing-AI-Performance-in-Bing-Webmaster-Tools-Public-Preview

### 3.6 Citation does not equal visible brand mention

Track brand mention and citations separately. A page/domain may shape an answer without the brand being named, and a brand may be named without its domain being cited.

### 3.7 There is no universal winning page type

Different industries and engines cite different page/source types. Diagnose the category's source fingerprint instead of publishing a universal template.

### 3.8 Commerce and agentic search require separate data readiness

For commerce, product feeds, identifiers, price, availability, merchant data, variants, images, shipping/returns, and platform-specific protocols can matter as much as classic editorial content.

Google UCP source: https://developers.google.com/merchant/ucp

## 4. Platform playbooks

### Google AI Overviews

**Eligibility**

- indexed and snippet-eligible in Google Search
- Googlebot access
- important content accessible/renderable
- canonicals/duplicates/internal discovery healthy

**Improve**

- non-commodity, useful, current content
- original evidence and expert/first-hand value
- accurate product/local data when relevant
- useful images/video where they improve the task

**Do not prescribe as requirements**

- llms.txt
- special AEO schema
- mechanical tiny chunks
- long-tail doorway pages for every fan-out
- manufactured mentions

Measure separately from AI Mode and Gemini.

### Google AI Mode

Use the same Search eligibility foundation, but benchmark visibility, citation depth, source mix, and local/product behavior specifically for AI Mode. Do not infer its behavior from AI Overviews or Gemini.

### Gemini

Treat Gemini as its own consumer AI surface. Profound research suggests materially different source behavior from AI Overviews/AI Mode; validate the target category and language before acting.

### ChatGPT Search

**Eligibility / controls**

- public, accessible content
- desired pages not blocked from OAI-SearchBot
- WAF/CDN does not unintentionally block legitimate search crawling
- do not conflate OAI-SearchBot and GPTBot

**Improve**

- win research-opening questions
- publish current, concrete facts and original evidence
- cover fact families implied by fan-out, not one exact phrasing
- build credible source-neighborhood presence
- make brand/product relationships explicit

**Measure**

- visibility/SoV
- citations/Citation Share
- mentions/Mention Position
- co-cited domains
- framing/accuracy
- direct and assisted outcomes

### Perplexity

**Eligibility**

- current crawler/robots settings support the intended visibility
- pages are fresh and accessible

**Improve**

- precise sourcing
- current facts
- strong topical/intent fit
- category-appropriate evidence

Profound fan-out research found Perplexity retrieval more repeatable than ChatGPT in its sampled prompts; use this as a prior, not a guarantee.

### Microsoft Copilot / Bing

**Eligibility**

- Bing crawl/index health
- correct robots/canonicals/sitemaps

**Improve**

- clear expertise and subject focus
- useful headings/tables/FAQs only when natural
- evidence-backed claims and fresh updates
- IndexNow for meaningful changes where appropriate

**Measure**

- AI citations
- cited pages
- grounding queries
- model/topic/source-mix trends

### Claude and Grok

Use current official product documentation and current category/model observations. Do not infer ChatGPT or Google mechanics. Segment source mix, prompt cohorts, visibility, and narrative independently.

### Commerce

**ChatGPT**

- determine whether shopping is a relevant surface for the category
- keep product data complete and current
- verify current feed/catalog/merchant guidance
- track recommendation inclusion separately from merchant/offer routing
- repeat volatile carousel tests

**Google**

- maintain Merchant Center data
- treat UCP/agentic checkout as relevant only for real agentic-commerce goals
- keep Business Profile/product data accurate

### Local

- current Google Business Profile / Bing Places where relevant
- consistent hours, category, service area, contact details
- unique local landing-page value
- track factual accuracy around hours, location, service, availability, and price/range

## 5. Myth checks

Treat these as unsupported or overgeneralized unless fresh evidence proves otherwise:

- "AEO is mostly PR."
- "AEO is mostly owned content."
- "Reddit is always the answer."
- "Track a few prompts many times per day and you have reliable AEO measurement."
- "Optimize for the exact user prompt wording."
- "One Google AI surface tells you how all Google AI surfaces behave."
- "A citation is the same as brand visibility."
- "Direct AI referral clicks capture AEO value."
- "One shopping carousel is a rank."
- "llms.txt is required for Google AI visibility."
- "There is a special AEO schema that guarantees citations."
- "Every page should be broken into tiny answer chunks."
- "More FAQ pages automatically increase AI visibility."
- "Classic SEO no longer matters."
- "Ranking in classic search guarantees AI citation."

## 6. Reusable output contracts

Use these structures flexibly. Lead with the answer/decision. Separate observed evidence, inference, recommendation, and unknowns.

### 6.1 AEO Audit

```markdown
AEO Audit — [Brand / Domain]

Executive summary
- Current state:
- Primary bottleneck:
- Highest-leverage move:
- Confidence:

Market baseline

| Dimension | Brand | Competitor(s) | Relevant benchmark | Interpretation |
| --- | --- | --- | --- | --- |
| Visibility / Share of Voice |  |  |  |  |
| Mention Position |  |  |  |  |
| Citation Share |  |  |  |  |
| Brand/company source share |  |  |  |  |
| Earned/institution share |  |  |  |  |
| Social/UGC share |  |  |  |  |

Visibility-stack diagnosis

| Layer | Evidence | Status | Why it matters |
| --- | --- | --- | --- |
| Access/eligibility |  | Pass/Watch/Fail |  |
| Retrieval/fan-out fit |  |  |  |
| Citation readiness |  |  |  |
| Brand visibility |  |  |  |
| Narrative/accuracy |  |  |  |
| Business outcome |  |  |  |

Priority actions

| Priority | Action | Bottleneck | Impact | Confidence | Effort | Dependency | Owner |
| --- | --- | --- | --- | --- | --- | --- | --- |
|  |  |  |  |  |  |  |  |

Measurement plan
[Prompt cohort, engines/models, languages/markets, cadence, controls, Visibility/SoV, Mention Position, Citation Share, source categories, accuracy/framing, referrals, assisted outcomes]

Evidence & caveats
[Separate official guidance, Profound observations, site evidence, and assumptions]
```

### 6.2 Prompt Portfolio

```markdown
AEO Prompt Portfolio — [Brand / Category]

Demand model

| Cluster | User job | Stage | Real-demand evidence | Business value | Priority |
| --- | --- | --- | --- | --- | --- |
|  |  |  |  |  |  |

Portfolio

| Prompt family | Research-opening prompt | Variants/follow-ups | Fact/entity needs | Likely fan-outs | Engine(s) | Market/language |
| --- | --- | --- | --- | --- | --- | --- |
|  |  |  |  |  |  |  |

Measurement groups
- Stable core:
- Discovery cohort:
- Diagnostic controls:
- High-noise repeated-run experiments:
```

### 6.3 Citation Gap

```markdown
Citation Gap — [Topic / Prompt Cluster]

Current source market
[Top domains/categories by engine, language, market]

Where the brand loses

| Prompt cluster | Engine | Mentioned | Cited | Winner(s) | Source category | Fan-out/fact need | Gap type |
| --- | --- | --- | --- | --- | --- | --- | --- |
|  |  |  |  |  |  |  |  |

Citation-neighbor map

| Domain | Co-citation frequency/share | Role | Why it may be trusted | Reachability | Action |
| --- | --- | --- | --- | --- | --- |
|  |  |  |  |  |  |

Best interventions
- owned/source-of-truth action
- evidence/original-data action
- third-party ecosystem action
- entity/technical/freshness action

Test design
[Stable before/after cohort, repeats if needed, observation window, controls]
```

### 6.4 Answer Accuracy & Framing

```markdown
AI Answer Accuracy & Framing — [Brand]

Claim ledger

| Engine/prompt | Model claim | Source | Correct? | Fresh? | Solicited/editorial | Decision impact | Severity |
| --- | --- | --- | --- | --- | --- | --- | --- |
|  |  |  |  |  |  |  |  |

Source-of-truth gaps

| Fact/claim | Canonical source | Current problem | Required update | Distribution path |
| --- | --- | --- | --- | --- |
|  |  |  |  |  |

Framing
- positive decision frames:
- negative decision frames:
- missing differentiators:
- vague owned claims that invite interpolation:
- competitor frames repeatedly borrowed:
```

### 6.5 AEO Content Brief

```markdown
AEO Content Brief — [Working title]

Target user job
Prompt cluster
- primary research-opening prompt
- variants/follow-ups
- likely fan-out/fact needs
- target engine(s), market(s), language(s)

Current answer/source landscape
Information-gain requirement
Required evidence
- original data/first-hand experience where useful
- concrete claims
- current dates/versions/prices/availability where material
- methodology/provenance

Recommended structure
Use direct answers where useful, descriptive headings, evidence, nuance, and true comparison tables. Do not mechanically chunk content for AI.

Narrative risk checks
Success criteria
[Retrieval/citation, mention/position, correct framing, direct/assisted outcome]
```

### 6.6 AEO Roadmap

```markdown
AEO Roadmap — [Brand]

Strategy thesis
Opportunity map

| Theme | Demand | Visibility | Citation gap | Narrative gap | Business value | Priority |
| --- | --- | --- | --- | --- | --- | --- |
|  |  |  |  |  |  |  |

Workstreams
- Prompt demand/portfolio
- Technical eligibility/retrieval
- Content/evidence/freshness/entities
- Source ecosystem
- Narrative accuracy/competitive framing
- Measurement/attribution/experimentation
- Commerce/local/agent readiness if relevant

Experiments
For each: hypothesis, target engine/model/market/prompt cluster, bottleneck, intervention, control, sample/cadence, metric, stop/scale condition.
```

### 6.7 AEO Practice Operating System

```markdown
AEO Practice — [Company / Team]

Mission
Operating loops

| Loop | Owner | Cadence | Inputs | Trigger | Output | KPI |
| --- | --- | --- | --- | --- | --- | --- |
| Demand |  |  |  |  |  |  |
| Visibility |  |  |  |  |  |  |
| Citation |  |  |  |  |  |  |
| Narrative |  |  |  |  |  |  |
| Retrieval |  |  |  |  |  |  |
| Content |  |  |  |  |  |  |
| Distribution |  |  |  |  |  |  |
| Technical |  |  |  |  |  |  |
| Outcome |  |  |  |  |  |  |
| Learning |  |  |  |  |  |  |

Decision rules
- benchmark source mix before channel allocation
- check portfolio composition and model drift before escalating a visibility loss
- fix source-of-truth errors before cosmetic rewrites
- require experiment IDs/dates for interventions
- connect wins to business impact separately from visibility
```

## 7. Source index

### Profound

- Where do AI citations come from? — https://www.tryprofound.com/blog/where-do-ai-citations-come-from
- Enhanced Citation Categories — https://www.tryprofound.com/blog/enhanced-citation-categories
- Is once a day enough? — https://www.tryprofound.com/blog/is-once-a-day-enough
- Prompt Research Reports — https://www.tryprofound.com/blog/introducing-prompt-research-reports-in-profound
- How ChatGPT sources the web — https://www.tryprofound.com/blog/chatgpt-citation-sources
- What AI engines actually search for — https://www.tryprofound.com/blog/what-ai-engines-actually-search-for
- AI Search Volatility — https://www.tryprofound.com/blog/ai-search-volatility
- Query language and citations — https://www.tryprofound.com/blog/how-query-language-reshapes-ai-citations
- The Parrot Problem — https://www.tryprofound.com/blog/the-parrot-problem
- FactCheck — https://www.tryprofound.com/blog/introducing-factcheck
- The shortlist is the new shelf — https://www.tryprofound.com/blog/the-shortlist-is-the-new-shelf
- The AI mention effect — https://www.tryprofound.com/blog/the-ai-mention-effect
- ChatGPT Shopping trigger — https://www.tryprofound.com/blog/chatgpt-shopping-prediction
- ChatGPT retailer routing — https://www.tryprofound.com/blog/chatgpt-retail-target-walmart
- Profound Index — https://www.tryprofound.com/blog/introducing-the-profound-index
- Pages — https://www.tryprofound.com/blog/one-command-center-for-your-contents-performance
- AEO practice / MCP webinar — https://www.tryprofound.com/resources/webinars/an-inside-look-at-profound-s-mcp-with-emily-kramer

### Official platform sources

- Google AI features and Search — https://developers.google.com/search/docs/appearance/ai-features
- OpenAI publishers/developers FAQ — https://help.openai.com/en/articles/12627856-publishers-and-developers-faq
- OpenAI shopping — https://help.openai.com/en/articles/11128490-improved-shopping-results-from-chatgpt-search
- Perplexity bots — https://docs.perplexity.ai/guides/bots
- Bing Webmaster AI Performance — https://blogs.bing.com/webmaster/February-2026/Introducing-AI-Performance-in-Bing-Webmaster-Tools-Public-Preview
- Google Universal Commerce Protocol — https://developers.google.com/merchant/ucp
