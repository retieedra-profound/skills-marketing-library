---
name: session-start
description: "Start-of-session planning and prioritization. Reads structured state, checks recurring tasks, pulls open tickets, sets focus. Trusts the memory plugin's session-start injection for recent history. Use when beginning a work session. Also triggers for 'good morning', 'start session', 'what should I work on', 'plan my day', or 'what's my context'. For ending sessions, see session-end."
---

# Session Start: Daily Planning

Initializes your session with structured state, open tickets, and a prioritized plan. Relies on a memory plugin's automatic session-start injection for observation history, so it does not re-read local session logs.

> Adapt the file paths and tool names below to your own setup. This skill assumes two state files (a shared one and a per-user one), an issue tracker, and an optional memory plugin. Swap in whatever you use.

## How this skill relates to a memory plugin

If you run a memory plugin (for example, Claude Mem), it already injects recent observations and session summaries into context at session start (you see a "recent context" table with session IDs, timestamps, and types at the top of the session). **This skill does not duplicate that.** It adds what the memory layer doesn't track: structured current focus, recurring tasks, open tickets, and prioritization.

## Step 1: Read structured state

Resolve the current user (most setups map the logged-in OS user to a profile name).

Read **two files**:
1. The shared state file, `company.*` (ICPs, messaging, quarterly_goals, key_metrics) and shared `recurring_tasks` (e.g. company-context-refresh, team-routing-refresh)
2. The per-user state file, `user.*`, `current_focus`, `last_session`, `last_session_note`, `active_goals`, personal `recurring_tasks` (e.g. voice-guide-refresh), `preferences`, `reminders`

Extract:

- `current_focus.initiative` and `session_goal` (from personal)
- `last_session.open_items` and `next_steps` (from personal)
- `recurring_tasks` from BOTH files, flag any whose `next_due` ≤ today
- `reminders` from personal, surface any whose `surface_when` matches today AND whose `surface_trigger` includes `session-start`
- `company` TODO placeholders (from shared), flag if company context is still unpopulated

If you keep a spaced-repetition review file, check it too: if any cards are due (`next_review <= today`), add a one-line mention to the summary. Do not auto-run the review.

Do NOT re-read local session-log files. The memory plugin's injection at the top of context already tells you what happened last session. If the injection is missing or empty, ask: "What did we do last time?" then use the memory plugin's search tool to pull it.

Output a brief summary:

```
**Last session:** [from the memory injection, cite session IDs]
**Carried forward:** [from per-user state last_session.open_items]
**Recurring task due:** [Task name], [how to run] (if any)
**Reminders surfacing:** [Reminder title, if any matched today]
**Review:** [N cards due, only if any are due]
```

## Step 2: Pull open tickets

Query your issue tracker for issues assigned to the current user, in statuses Todo, In Progress, and Backlog (read the assignee from the per-user state file).

Filter and categorize:
- **In Progress**, currently active
- **Todo**, ready to work on
- **Backlog**, needs triage

## Step 3: Analyze and prioritize

| Factor | Weight |
|--------|--------|
| Due date < 3 days | High |
| High priority in tracker | High |
| Blocking others | High |
| Quick win (< 30 min) | Medium |
| No due date set | Flag for setting |

Create a prioritized list with clear reasoning.

## Step 4: Set due dates (with permission)

For tasks without due dates, suggest dates based on complexity and current workload.

> "These tasks need due dates. Should I set them?
> - [Task 1] → Suggested: [Date]
> - [Task 2] → Suggested: [Date]"

On approval, update the tickets.

## Step 5: Set session focus

> "What's your main focus for today?
> 1. [Top priority]
> 2. [Second priority]
> 3. Something else (specify)"

Update the per-user state file (NOT the shared one):
- `current_focus.initiative` and `session_goal`
- `last_updated` date

**Never write personal session state to the shared state file**, that file is the shared company source of truth. Each user owns their own session state in their per-user file.

## Memory staleness: reactive only

Do NOT proactively scan every memory entry on every session start, that's wasteful. Instead:

- If the memory injection mentions a concept, and a state file or memory file contradicts it, flag the specific conflict.
- If the user asks about a topic where the memory might be stale, verify the current state before answering.
- If the user explicitly asks "is my memory current," then spot-check. Otherwise defer to session-end's learning capture.

## Output format

```markdown
## Good morning

### Carried forward from last session
[From state file open_items + next_steps]

### Recurring Tasks Due
- [ ] [Task name], [Description] *(due: [date])*

---

## Open Tickets

**In Progress:** [Tickets]
**Todo:** [Tickets with due dates]
**Needs Attention:** [Undated tickets → suggested dates]

---

## Recommended Priorities for Today

1. **[Top task]**, [Why it's #1]
2. **[Second task]**, [Why]
3. **[Third task]**, [Why]

---

**What's your focus today?**
```

## What NOT to do

- Do not read local session-log files. The memory plugin's injection covers session history.
- Do not proactively scan all memory entries on every session start.
- Do not summarize memory observations back to the user, they already see them.

## Cross-references

- **session-end**, capture learnings, mirror memory to your knowledge base, surface candidates
- **A memory plugin**, automatic observation capture and session summaries (no manual action needed)
