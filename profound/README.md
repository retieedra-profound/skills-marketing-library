# Profound Skills

Skills for **Profound**.

## Structure

Each skill lives in its own subdirectory:

```
profound/
└── <skill-name>/
    ├── SKILL.md      # skill entrypoint read by the agent
    └── RESEARCH.md   # optional supporting knowledge (progressive disclosure)
```

## Skills

| Skill | Path |
| --- | --- |
| AEO Operator 2026 | [`aeo-operator-2026/`](./aeo-operator-2026/) |
| Humanizer | [`humanizer/`](./humanizer/) |
| Improved copywriting | [`improved-copywriting/`](./improved-copywriting/) |

## Adding a Skill

1. Create a new folder: `profound/<skill-name>/`
2. Add a `SKILL.md` that describes what the skill does and how the agent should execute it.
3. Optionally add supporting files (for example `RESEARCH.md`) linked one level deep from `SKILL.md`.
4. Register the skill path in your agent settings so it can load `SKILL.md`.
