---
name: claude-code-discoverability-auditor
description: Audits documentation, pricing, compatibility, and technical pages for retrieval and accurate recommendation inside Claude Code. Use when a developer product, API, SDK, infrastructure tool, or SaaS company wants to improve how Claude Code agents discover, evaluate, and use it.
---

# Claude Code Discoverability Auditor

## Research basis

This skill operationalizes Profound's research, [Claude and Claude Code are distinct Answer Engines](https://www.tryprofound.com/blog/claude-and-claude-code-are-distinct-answer-engines), published August 24, 2026.

Key takeaways from the study:

- In 24,135 sampled responses with web search enabled, Claude searched in 93% of responses while Claude Code searched in 13%.
- Brand overlap between the two products averaged only 20%, despite their related model foundation.
- Nearly three-quarters of observed Claude Code agent visits went to documentation, informational, and pricing pages.
- Claude Code favored shorter, highly structured responses and frequently used lists and tables.

These are observational results from a defined sample and period. Do not claim that page formatting guarantees a mention or that Claude Code always behaves this way.

## Goal

Make the exact facts a coding agent needs easy to discover, retrieve, verify, and apply without sacrificing human usability or technical accuracy.

## Intake

Collect:

- product and canonical domain
- documentation, API reference, SDK, pricing, changelog, and support-policy URLs
- supported languages, runtimes, frameworks, regions, and environments
- authentication and installation methods
- current limitations, deprecations, and migration paths
- priority Claude Code tasks and competing tools

## Workflow

1. Define the tasks users ask Claude Code to perform: install, authenticate, integrate, migrate, debug, compare, estimate cost, or verify compatibility.
2. Map each task to its canonical page and required facts.
3. Audit discovery: navigation, internal links, sitemap, robots controls, canonical URLs, status codes, and rendered text.
4. Audit retrieval:
   - precise page titles and headings
   - direct answers before background
   - explicit commands and prerequisites
   - copyable examples
   - named versions and dates
   - stable anchors and URLs
5. Audit product facts: supported versions, platform constraints, limits, uptime claims, pricing units, rate limits, data handling, and availability.
6. Check consistency across docs, pricing, README files, package registries, examples, and changelogs.
7. Identify missing decision pages such as compatibility matrices, migration guides, troubleshooting references, and pricing explanations.
8. Test representative tasks using fresh sessions and record whether the product is mentioned, retrieved, and represented accurately.
9. Prioritize corrections by task frequency, decision impact, evidence confidence, and maintenance cost.

Use question-shaped headings only when they match real user tasks. Do not mechanically rewrite every heading or stuff product names into documentation.

## Output

Return:

1. Executive diagnosis.
2. Task-to-page coverage map.
3. Technical fact ledger with canonical source and freshness owner.
4. Retrieval blockers and conflicting claims.
5. Page-level recommendations with proposed facts, structure, and examples.
6. Claude versus Claude Code test matrix.
7. Retest plan with prompt, environment, date, and observed outcome.

Never infer official Anthropic ranking factors from Profound's observations. Verify crawler and access controls against current Anthropic documentation.
