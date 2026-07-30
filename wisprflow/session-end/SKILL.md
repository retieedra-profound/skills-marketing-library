---
name: session-end
description: "End-of-session capture: knowledge-base daily log, memory mirroring, candidate surfacing. Delegates session-summary synthesis to a memory plugin. Use when wrapping up a work session. Also triggers for 'end session', 'wrap up', 'session summary', 'what did we do today', or 'save progress'. For starting sessions, see session-start."
---

# Session End: Knowledge Base Sync + Memory Capture

Captures curated learnings and mirrors them into a linked knowledge base (for example, an Obsidian vault organized Zettelkasten-style).

> Adapt the paths and tool names below to your own setup. This skill assumes a daily-log knowledge base, a cross-session memory layer, and an optional memory plugin. The `<vault>/` placeholder is wherever your knowledge base lives.

## How this skill relates to a memory plugin

A memory plugin (for example, Claude Mem) automatically generates a semantic session summary at session end and stores it in its own database. **This skill does not duplicate that synthesis.** Instead it captures *curated* signal: decisions that matter, memory updates, knowledge-base mirrors, and promotion candidates. The rich observation log stays in the memory plugin (query it with its search tool).

## Step 1: Gather curated session context

Don't narrate the whole session, the memory plugin has that. Extract:

- **Key levers moved:** 1-3 decisions or strategic shifts that matter
- **Open loops:** blockers, pending items carrying forward
- **Next focus:** priority for next session
- **Projects touched:** for knowledge-base links
- **People mentioned:** for knowledge-base links

## Step 2: Daily log (primary record)

Write or append to `<vault>/daily/YYYY-MM-DD.md`. Create the file if missing with frontmatter:

```yaml
---
type: session-log
date: YYYY-MM-DD
---
```

Append a block for this session:

```markdown
## [HH:MM], [workspace], [Brief title]

**Focus:** [one-line]

**Key levers:**
- [Decision or shift that matters]

**Open loops:**
- [Items carrying forward]

**Projects touched:** [[projects/slug-1]], [[projects/slug-2]]
**People:** [[name-1]], [[name-2]]

**Next focus:** [One line]

---
```

Keep it tight. If nothing moved, write one line: `No significant levers, routine execution session.`

## Step 3: Thin local pointer

Append a short pointer to your local session log at `logs/sessions/YYYY-MM-DD.md` so a weekly review tool can still find it without re-synthesizing what the memory plugin already stored:

```markdown
## [HH:MM], [Brief title]

**Focus:** [one-line]

**Key levers:**
- [Top 1-3 items, verbatim copy from the daily log above]

**Next:** [Next focus]

_(Full session history in the memory plugin. Curated atoms live in the knowledge base.)_

---
```

## Step 4: Update agent state

Resolve the current user, then update the per-user state file (NOT the shared one):

```json
{
  "last_updated": "YYYY-MM-DD",
  "current_focus": { "initiative": "...", "session_goal": "...", "notes": null },
  "last_session": { "date": "...", "focus": "...", "key_levers": [...], "open_items": [...], "next_steps": [...] },
  "last_session_note": "narrative paragraph capturing the session's thread"
}
```

Also update `active_goals`, `reminders`, and per-user `recurring_tasks` if they changed.

**Never write personal session state to the shared state file**, that file is the shared company source of truth (company block plus shared recurring tasks only). Each user owns their own session state in their per-user file.

## Step 5: Memory files + knowledge-base mirror

Review the session for information that should persist across conversations.

| Signal | Memory action | Knowledge-base mirror |
|--------|--------------|--------------|
| New strategic decision | Create/update `project_{slug}.md` | Write to `<vault>/projects/{slug-no-underscores}.md` |
| User corrected your approach | Create/update `feedback_{slug}.md` | Write to `<vault>/references/{slug}.md` + **add candidate** |
| Learned about external resource/tool | Create/update `reference_{slug}.md` | Write to `<vault>/references/{slug}.md` |
| Metrics, targets, team changed | Update existing file | Update mirror |
| Memory now stale or completed | Remove file + index entry | Remove mirror |

**Mirror frontmatter:**
```yaml
---
type: project | reference
workspace: [workspace]
source_memory: <original memory filename, with .md>
aliases:
  - <original memory filename, without .md>
last_updated: YYYY-MM-DD
---
```

Body: verbatim copy of memory file content (drop original frontmatter).

**Slug rule:** filename without prefix, underscores → hyphens, no `.md`. For example `project_ph_takeover.md` → `ph-takeover.md`.

**Why the alias (load-bearing):** memory-file bodies link with the full slug, for example `[[reference_cac_canonical]]`, but the mirror filename is hyphenated, for example `cac-canonical.md`. A linked knowledge base like Obsidian resolves `[[slug]]` against a note's aliases, so the alias line is what keeps those links from breaking. A mirror written without it lands as an orphan. Note: `feedback_*` files mirror to `references/` with `type: reference`.

**Connect it, don't just drop it.** After writing a mirror, link it so it is not an orphan:
- Add it to the matching domain map-of-content (MOC) index.
- Make sure the daily-log block forward-links it under Projects touched or a References touched line.

A mirror with no inbound link is debt that a graph-health check will flag.

**Memory file rules:**
- The memory index stays small; one line per file, kept short
- Check for existing memory before creating new
- Update the index when files are added or removed

## Step 6: Candidate detection

Scan for promotion candidates. Append to your inbox `candidates.md` when any of these fire:

- Decision logged with explicit rationale
- New or updated `feedback_*` file
- Framework or mental model applied and worked
- User said "remember this," "important," or "worth noting"
- Memory flagged stale and the concept needs re-examination

Append under `## Pending`:

```markdown
## [YYYY-MM-DD workspace] {short title}
**Source:** memory/{filename} OR session log
**Snippet:** {1-3 lines, trimmed}
**Why surfaced:** decision | feedback | theme | explicit-flag
**Status:** pending
```

**In-flow capture (the user's own words).** When the session contains a passage where the user articulated a rule, framework, or tradeoff in their own words (chat or dictation), quote it back in the candidate entry verbatim, not paraphrased. Mark it so a later promotion pass can promote it without a fresh dictation pass:

```markdown
## [YYYY-MM-DD workspace] {short title}
**Source:** session log (user's words, [HH:MM])
**Snippet:** "{verbatim quote, exact}"
**Why surfaced:** explicit-flag
**Status:** pending
**Promotion:** eligible for direct promotion (user's words)
```

Apply mechanical AI-tell strips only (no em dashes); never rephrase the quote.

## Step 7: Surface promotion reminder

Count `Status: pending` entries in `candidates.md`. If >5, end with:

> **N candidates waiting for a voice pass.** Run the promotion skill when you want to turn them into permanent notes.

**In-flow articulations.** If this session produced any candidates marked `**Promotion:** eligible for direct promotion (user's words)`, offer to act now rather than only queuing them.

## Step 8: Permanent-instructions flag (optional)

If a learning should become permanent instructions (not just memory), ask:
> "Should any of these be added to the project instructions file for all future sessions?"

## What NOT to do

- **Never re-synthesize the full session narrative.** The memory plugin has the semantic summary. Extract key levers only.
- **Never auto-write permanent voice notes.** Those are the user's voice only, via a dedicated promotion pass.
- **Never auto-edit the MOC index files.** That is a separate synthesis step.
- **Never rephrase memory file content when mirroring.** Verbatim copy preserves voice.

## Output format

```markdown
## Session Wrapped: [Date]

### Logged
- Daily log: `<vault>/daily/YYYY-MM-DD.md`
- Local pointer: `logs/sessions/YYYY-MM-DD.md`
- (Memory plugin semantic summary: automatic)

**Key levers:** [1-3 items]
**Open loops:** [Items]
**Next focus:** [Focus]

**Memory updated:**
- [Created/Updated/Removed: file, reason → mirror path]
- (or "No memory changes this session")

**Candidates surfaced:** N

[If pending > 5] **N candidates waiting for a voice pass.**

---
**Agent state updated.** Next session will start with this context.
```

## Cross-references

- **session-start**, next session; trusts the memory plugin injection for history
- **A promotion skill**, turn pending candidates into permanent voice-pass notes
- **A synthesis skill**, refresh the workspace index and MOCs
