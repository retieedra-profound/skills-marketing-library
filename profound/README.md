# Profound Skills

Agent skills built for **Profound**.

## Structure

Each skill lives in its own subdirectory:

```
profound/
└── <skill-name>/
    └── SKILL.md   # skill entrypoint read by the agent
```

## Adding a Skill

1. Create a new folder: `profound/<skill-name>/`
2. Add a `SKILL.md` that describes what the skill does and how the agent should execute it.
3. Register the skill path in your Cursor settings under `agent_skills`.
