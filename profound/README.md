# Profound Skills

Skills for **Profound**.

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
| Humanizer | [`humanizer/`](./humanizer/) | Rewrite text to remove AI tells and restore a human voice |
| Improved copywriting | [`improved-copywriting/`](./improved-copywriting/) | Write and sharpen marketing copy grounded in customer language |

## Adding a Skill

1. Create a new folder: `profound/<skill-name>/`
2. Add a `SKILL.md` that describes what the skill does and how the agent should execute it.
3. Optionally add supporting files linked one level deep from `SKILL.md`.
4. Register the skill path in your agent settings so it can load `SKILL.md`.
