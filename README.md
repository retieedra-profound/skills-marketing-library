# Skills Repo

A monorepo of Cursor Agent Skills, organised by company. Each company folder
contains one subdirectory per skill.

## Structure

```
profound-skills/
├── profound/          # Skills for Profound
│   └── <skill-name>/
│       └── SKILL.md
├── wisprflow/         # Skills for Wisprflow
│   └── <skill-name>/
│       └── SKILL.md
├── README.md
└── LICENSE
```

## Companies

| Folder | Description |
|---|---|
| [`profound/`](./profound/) | Agent skills for the Profound product suite |
| [`wisprflow/`](./wisprflow/) | Agent skills for the Wisprflow product suite |

## Adding a New Company

1. Create a top-level folder with the company's slug (lowercase, no spaces).
2. Add a `README.md` inside it describing the company and its skills.
3. Add skill subdirectories following the pattern above.

## Adding a Skill

1. Navigate to the relevant company folder.
2. Create `<skill-name>/SKILL.md`.
3. Write the skill — the file should explain **what** the skill does and
   **how** the agent should execute it, step by step.
4. Register the absolute path to `SKILL.md` in your Cursor settings under
   `agent_skills` so the agent can discover and invoke it.

## License

[MIT](./LICENSE)
