# Wisprflow Skills

Skills by the **Wisprflow** team.

## Structure

Each skill lives in its own subdirectory:

```
wisprflow/
└── <skill-name>/
    ├── SKILL.md      # skill entrypoint read by the agent
    ├── assets/       # optional templates the skill fills in
    └── references/   # optional supporting knowledge (progressive disclosure)
```

## Skills

| Skill | Path | What it does |
| --- | --- | --- |
| Brand voice | [`brand-voice/`](./brand-voice/) | Apply and maintain consistent brand voice across communications |
| Copy editing | [`copy-editing/`](./copy-editing/) | Polish existing copy for clarity, conversion, and brand voice |
| Link creator | [`link-creator/`](./link-creator/) | Create tracked Dub.co short links with UTMs, promo codes, and folder organization |
| Newsletter copy | [`newsletter-copy/`](./newsletter-copy/) | Generate newsletter sponsorship copy variants with tracking URLs and placement specs |
| Session end | [`session-end/`](./session-end/) | Capture end-of-session logs, mirror memory, and surface candidates |
| Session start | [`session-start/`](./session-start/) | Plan and prioritize a work session from structured state and open tickets |
| Writing | [`writing/`](./writing/) | Edit AI-generated drafts to read like a human wrote them |

## Adding a Skill

1. Create a new folder: `wisprflow/<skill-name>/`
2. Add a `SKILL.md` that describes what the skill does and how the agent should execute it.
3. Register the skill path in your agent settings so it can load `SKILL.md`.
