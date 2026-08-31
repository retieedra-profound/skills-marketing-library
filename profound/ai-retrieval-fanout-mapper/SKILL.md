---
name: ai-retrieval-fanout-mapper
description: Maps the search queries and concrete fact needs that answer engines may generate behind a user prompt, then turns them into evidence-backed content requirements. Use when content matches visible prompts but is not retrieved or cited by ChatGPT, Perplexity, or Copilot.
---

# AI Retrieval Fan-Out Mapper

## Research basis

This skill operationalizes Profound's research, [What AI engines actually search for and why ChatGPT never searches the same way twice](https://www.tryprofound.com/blog/what-ai-engines-actually-search-for), published April 30, 2026.

Key takeaways from the study:

- Profound tracked 10,000 prompts across ChatGPT, Perplexity, and Copilot for 14 days.
- The engines generated similar numbers of searches per run but differed greatly in repetition and wording.
- ChatGPT generated highly varied research paths; Perplexity stayed closest to the prompt; Copilot compressed prompts into shorter search-style queries.
- All three often converted broad advice or comparison prompts into concrete fact-retrieval searches.

These findings are observational and may change with models and product updates. Use observed fan-outs when available and label inferred fan-outs as hypotheses.

## Goal

Identify the facts, entities, constraints, vocabulary, and supporting evidence an answer engine may retrieve while answering a prompt family.

## Workflow

1. Define the prompt family, audience, stage, engine, language, and market.
2. Capture observed fan-out queries when the platform or analytics product exposes them.
3. Otherwise infer candidate retrieval paths and label them clearly as inferred.
4. Decompose the user job into:
   - entities and category terms
   - factual subquestions
   - comparison criteria
   - constraints such as price, compatibility, location, and recency
   - standards, definitions, reviews, and primary evidence
5. Group fan-outs into stable fact families rather than exact query strings.
6. Map each family to the current best source and competing cited sources.
7. Audit whether the brand has a canonical, current, specific answer.
8. Recommend improving, consolidating, or creating content only when a real information gap exists.
9. Test across repeated runs and engines; do not expect identical retrieval paths.

Do not create one doorway page per fan-out query. One strong resource can satisfy several related retrieval needs.

## Engine considerations

- For ChatGPT, plan for broad vocabulary and adjacent research paths.
- For Perplexity, preserve clear category terms and direct factual matches.
- For Copilot, cover concise search-style formulations and core entities.
- For every engine, verify actual behavior before turning a prior into a rule.

## Output

Return:

1. Prompt-family definition.
2. Fan-out map marking each query as observed or inferred.
3. Fact-family matrix with user need, evidence, current source, competitor source, and gap.
4. Content recommendation identifying which existing page should own each fact.
5. Required claims, sources, dates, examples, and comparison criteria.
6. Test plan by engine with repeated observations and success measures.
