# Profound Skills

Skills by the **Profound** team.

## Structure

Each skill lives in its own subdirectory:

```
profound/
└── <skill-name>/
    └── SKILL.md   # skill entrypoint read by the agent
```

Every Profound skill is currently self-contained in a single `SKILL.md`.

## Skills

| Skill | Path | What it does |
| --- | --- | --- |
| AEO Operator 2026 | [`aeo-operator-2026/`](./aeo-operator-2026/) | Audit and operate AI search visibility across demand, retrieval, citation, narrative, and business outcome |
| AI Answer Accuracy Auditor | [`ai-answer-accuracy-auditor/`](./ai-answer-accuracy-auditor/) | Audit factual claims and editorial framing about a brand in AI answers |
| AI Citation Mix Strategist | [`ai-citation-mix-strategist/`](./ai-citation-mix-strategist/) | Benchmark which owned, earned, and social sources shape AI answers and where to invest |
| AI Prompt Portfolio Builder | [`ai-prompt-portfolio-builder/`](./ai-prompt-portfolio-builder/) | Build prompt portfolios for visibility, citation, sentiment, and recommendation tracking |
| AI Retrieval Fanout Mapper | [`ai-retrieval-fanout-mapper/`](./ai-retrieval-fanout-mapper/) | Map search queries and fact needs behind user prompts into content requirements |
| International AEO Strategist | [`international-aeo-strategist/`](./international-aeo-strategist/) | Design AI visibility strategy by language, market, and engine rather than translating an English plan |
| Commercial AI Journey Mapper | [`commercial-ai-journey-mapper/`](./commercial-ai-journey-mapper/) | Map how buyers discover, compare, and choose brands across multi-turn AI conversations |
| AI Search Attribution Planner | [`ai-search-attribution-planner/`](./ai-search-attribution-planner/) | Design measurement for AI mentions, delayed visits, and outcomes beyond referral clicks |
| AI Commerce Readiness Auditor | [`ai-commerce-readiness-auditor/`](./ai-commerce-readiness-auditor/) | Audit product data and merchant evidence for AI shopping and agentic commerce |
| Claude Code Discoverability Auditor | [`claude-code-discoverability-auditor/`](./claude-code-discoverability-auditor/) | Audit docs and product pages for retrieval and recommendation inside Claude Code |
| Humanizer | [`humanizer/`](./humanizer/) | Rewrite text to remove AI tells and restore a human voice |
| Improved copywriting | [`improved-copywriting/`](./improved-copywriting/) | Write and sharpen marketing copy grounded in customer language |

## Adding a Skill

1. Create a new folder: `profound/<skill-name>/`
2. Add a `SKILL.md` that describes what the skill does and how the agent should execute it.
3. Optionally add supporting files linked one level deep from `SKILL.md`.
4. Register the skill path in your agent settings so it can load `SKILL.md`.
