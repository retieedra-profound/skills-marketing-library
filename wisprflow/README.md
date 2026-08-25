# Wisprflow Skills

Skills for **Wisprflow**.

## Structure

Each skill lives in its own subdirectory:

```
wisprflow/
└── <skill-name>/
    └── SKILL.md   # skill entrypoint read by the agent
```

## Adding a Skill

1. Create a new folder: `wisprflow/<skill-name>/`
2. Add a `SKILL.md` that describes what the skill does and how the agent should execute it.
3. Register the skill path in your agent settings so it can load `SKILL.md`.
