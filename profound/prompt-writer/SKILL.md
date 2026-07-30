---
name: prompt-writer
description: Convert vague instructions, rough briefs, or messy user requests into structured, high-performance prompts for LLMs. Use whenever the user asks to "rewrite this prompt," "improve this prompt," "fix this prompt," "make this prompt better," "turn this into a prompt," "make this clearer for an LLM," or anything else involving prompt engineering, prompt optimization, or converting natural language instructions into LLM-ready prompts. Trigger this skill even when the user just pastes a rough request and says "make this better" without naming it as a prompt task. The skill applies to system prompts, user prompts, agent instructions, and any other LLM input.
---

# Prompt Writer

A methodology for converting messy human instructions into structured, high-performance prompts that exploit how LLMs actually generate text.

## Core premise

LLMs are next-token predictors. At each step, the model produces a probability distribution over its vocabulary, conditioned on every token that came before. This means three things matter more than anything else:

- **Early tokens condition everything that follows.** What you place at the top of the prompt shapes every generated token after it.
- **Specificity activates narrower regions of the training distribution.** "Bloomberg Terminal" pulls from a more specific region of training data than "data dense."
- **Suppression matters as much as instruction.** LLMs have default behaviors: hedging, presenting options, and over-explaining. If you do not close off those defaults, the model falls back to them.

Every technique in this skill traces back to one of these principles. When in doubt, ask: am I conditioning early tokens, activating a specific region of the distribution, or suppressing a default behavior?

## When to apply this skill

Apply this skill whenever you are converting natural-language instructions into a prompt another LLM, or the same LLM in a different turn, will execute.

This includes:

- Rewriting a user's rough request into something a model can execute well.
- Turning a brief, project description, or Slack message into a structured task.
- Building system prompts for agents.
- Creating reusable prompt templates.
- Hardening an underperforming prompt into one that produces consistent quality.

Do not apply this skill when the user is asking a question, having a conversation, or making a request you are going to execute yourself. This skill is for crafting input to a model, not for being responsive to a person.

## The conversion methodology

Work through these phases in order. Each phase has a specific purpose and output. Do not skip phases.

### Phase 1: read the original carefully

Identify what the user actually wants, separately from how they phrased it. Most rough requests contain:

- A primary task.
- Constraints.
- Implicit context.
- Tonal cues.

Note what is clear and what is vague. The vague parts are where you make decisions or occasionally ask clarifying questions. The clear parts are constraints to preserve.

Pay special attention to:

- Strong-opinion words: "hate," "love," "no," "never," "must."
- Specific named references: tools, products, people, brands.
- Examples the user volunteered.
- Contradictions between different parts of the request.

### Phase 2: identify the right persona

Open the prompt with a persona statement that places the model in the role best suited to execute the task. This is the single highest-leverage move in the methodology.

A persona is not flavor. It is a statistical steering mechanism.

Good personas:

- Name the role specifically.
- Name the domain or specialty.
- Anchor to concrete reference points.
- Include tonal calibration.

Bad personas:

- "You are a helpful assistant."
- "You are an expert."
- "You are the best X in the world."

When the task spans domains, layer the persona. When the task involves writing in a specific voice, reference the voice directly.

### Phase 3: structure the task

After the persona, lay out the task itself. The structure should match the shape of the work.

- **Sequential tasks:** Number the phases.
- **Planning before execution:** For complex tasks, insert a planning step.
- **Research before generation:** Separate research from creation.
- **Verification loops:** Add screenshot, test, review, or validation phases when output must meet specific criteria.

### Phase 4: encode constraints concretely

Vague constraints get vague compliance. Convert every constraint into something falsifiable.

| Vague              | Concrete                                                                                   |
| ------------------ | ------------------------------------------------------------------------------------------ |
| Make it data dense | Small font sizes are fine. Wasted whitespace is a failure state. Think Bloomberg Terminal. |
| Be opinionated     | One build. One path. Do not present alternatives.                                          |
| Make it serious    | Sans-serif only. No rounded-everything. No pastel gradients. No startup energy.            |
| Make it good       | If a sentence could appear in any other category description, delete it.                   |
| Hard               | A reasoning-only LLM should score below 40%. A deep student should score above 75%.        |

State what the failure mode looks like, not just what success looks like.

### Phase 5: add suppression instructions

LLMs have default behaviors that leak into output unless explicitly suppressed.

Common defaults to close off:

- Hedging.
- Over-explaining basics.
- Presenting options.
- Mirroring the original structure.
- Length inflation.
- Throat-clearing transitions.

Suppression instructions should be at least as detailed as positive instructions. They are the negative space that defines the output.

### Phase 6: anchor with examples strategically

Examples are powerful but expensive. Use them when:

- The output format is non-obvious.
- A bad pattern needs to be contrasted with a good pattern.
- A reference style or voice is being defined.

Skip examples when:

- The user explicitly said not to do few-shot.
- The task is well-described.
- The persona alone is doing enough work.

When using examples, label them clearly as GOOD and BAD. The contrast does more work than either example alone.

### Phase 7: specify the output format

Tell the model exactly what to produce. The format spec should answer:

- What sections does the output have?
- What goes in each section?
- What is the length target?
- What formatting should be used?
- What should be excluded?

"Write a 200-word product description" is weaker than "Write three sections: (1) the problem in 50 words, (2) the product's specific solution in 100 words, (3) one concrete example. No headers. No bullets."

### Phase 8: read it back

Before delivering the rewritten prompt, read it as if you are the LLM that will execute it.

Check:

- Is the persona at the top doing the work it needs to do?
- Are the most important instructions in the first third?
- Is every constraint falsifiable?
- Are default behaviors suppressed?
- Would a model with no context produce the right output?
- Could the prompt be misread?

If anything fails, fix it before delivering.

## Standard prompt architecture

Most well-built prompts follow this architecture:

1. Persona.
2. Critical context or non-negotiable rules.
3. Task statement.
4. Sequential structure.
5. Constraints and rules.
6. Suppression instructions.
7. Examples, if helpful.
8. Output format specification.
9. Verification or quality check.

Not every prompt needs every section. Use judgment.

## Common patterns

### The litmus test pattern

When the task is "build something that can handle X," list 5 to 10 specific things X must handle. If any cannot be expressed, the ontology has holes. Fill them.

### The anti-pattern pattern

Explicitly list what not to do. Example: "Hard no's: college aesthetic. Conference swag energy. Anything that screams 'I completed an online course.'"

### The validation loop pattern

After completing the task, take a screenshot or run a check for X, Y, and Z. Fix and re-verify until clean. Do not deliver until verification passes.

### The two-sided quality bar pattern

Set targets in opposite directions. Example: "Someone with deep knowledge should score 75%. Someone without should score below 40%."

### The reasoning trap pattern

When designing tests, make the most logically appealing answer to someone without domain knowledge wrong.

### The plan-before-build pattern

Before building, output design rationale, data model, and wiring map. Then build.

### The voice match pattern

When rewriting in someone's voice, match the voice in the sample. If they write short sentences, write short sentences. If they use "stuff," do not upgrade to "elements."

## Anti-patterns to avoid

- Vague positive instructions.
- Buried critical instructions.
- Conflicting instructions.
- Over-specification on small tasks.
- Under-specification on large tasks.
- Pleading or politeness as a substitute for specificity.
- Hedging in the prompt itself.

## Example transformations

Original: "make this prompt better"

This is too vague to act on. Ask what they want changed, or inspect the pasted prompt and identify the likely problem: no persona, vague constraints, conflicting instructions, or buried critical rules.

Original: "Write me a guide to X. Make it really good and thorough."

Rewritten: "You are a [specific expert role]. Write the definitive guide to X for [specific audience]. Constraints: [3 to 5 falsifiable rules]. Anti-patterns: [3 to 5 things to avoid]. Length: [specific range]. Structure: [section breakdown]."

Original: "Help me figure out what to build for my company in this space."

Rewritten: "You are a [type of strategist]. Step 1: research [specific sources] for context. Step 2: identify [N] candidates against these criteria: [list]. Step 3: pick one and pitch it with: the recommendation, the evidence, why this beat the runners-up. Do not present a ranked list. Make a recommendation."

## Why-explanations are a force multiplier

When you write a constraint, briefly explain why it matters. This helps the model decide edge cases the prompt did not anticipate.

Compare:

- "Do not use em dashes."
- "Do not use em dashes. They are an AI tell. Replace with periods, colons, or parentheses."

Use why-explanations sparingly, but use them for constraints likely to be misinterpreted.

## When to ask clarifying questions

Default to making reasonable assumptions and stating them explicitly in the rewritten prompt. Ask only when:

- A critical piece of information is missing and cannot be inferred.
- The user's request contains a contradiction.
- The user has provided two paths and explicitly asked which one to take.

Ask one question at a time. Use multiple choice when appropriate.

## The final test

Before delivering a rewritten prompt, run this check:

If you handed this prompt to a competent LLM with no context, no memory of this conversation, and no ability to ask follow-up questions, would it produce the output the user actually wants?

If yes, deliver.

If no, the prompt is not done. Identify what is missing or unclear and fix it.
