# Newsletter Copy Framework

Reference for `/newsletter-copy`. Placement specs, funnel-stage hook mapping, copy patterns, and the validation checklist. Swap the example product framing (Wispr Flow, a voice-to-text tool) for your own, and replace every proof point with a verified claim from your own approved-claims list.

## Placement Specs

| Placement | Character Limit | Purpose |
|-----------|-----------------|---------|
| Subject Line | ≤45 chars | Inbox hook, drives open |
| Preheader | 50-90 chars | Preview text, supports subject |
| Primary | 150-250 words | Main ad unit, full pitch |
| Secondary | 100-125 words | Shorter placement, key points |
| Tertiary | ≤50 words | Brief mention, one hook |
| Link Module | Title + 10-15 words | Clickable link with description |

## Match the funnel stage to the audience

Pick the hook and CTA register from where the newsletter's audience sits relative to your product.

| Stage | Hook strategy | CTA register |
|-------|---------------|--------------|
| TOF (indifferent) | Curiosity, identity, "did you know" | Soft: "See how", "Learn more" |
| MOF (frustrated) | Pain point, "tired of X?", comparison | Medium: "Try it", "See the difference" |
| MOF (open) | Demo, proof, "watch this" | Medium: "Watch demo", "See it work" |
| BOF (ready) | Social proof, pricing, urgency | Hard: "Start free", "Get started" |

## Concept selection

Choose 1-2 angles that best match the audience. Each angle is a one-line world the copy lives in. Examples for a voice-to-text product:

| Concept | Best for | One-line world |
|---------|----------|----------------|
| Understands you | Frustrated typists | "Talk messy. It cleans it up." |
| Works everywhere | Multi-app users | "One mic for every app." |
| Time back | Busy professionals | "Move faster, log off sooner." |
| Prompt power | Developers, AI users | "Better input, better AI output." |

## Hook patterns

Categories that travel well across audiences. Write fresh lines, don't reuse stale ones.

- **Playful:** lightly anthropomorphize the old way of doing things.
- **Historical:** frame the status quo as overdue for change.
- **Personal discovery:** "a tool that changed how I work."
- **Tutorial / how-to:** lead with a concrete, repeatable win.
- **Pain point:** name the exact friction the reader feels.

## Bullet structure

Use a bold lead plus a supporting detail. Two to four bullets, never a forced trio.

```markdown
- **Faster than typing.** Dictate emails, docs, and messages in real time.
- **Cleans up as you go.** Filler words and grammar handled automatically.
- **Works in every app with no setup.** Same shortcut everywhere you type.
```

## Social proof

Use verified, attributable proof only. Never ship a quote you cannot source, and never reuse a retired endorsement. Placeholders:

> "{VERIFIED_CUSTOMER_TESTIMONIAL}" — {Name, Title, Company}

Keep a short library of approved quotes with a status column, and pull only from the approved set.

## CTA patterns

| Tone | CTA |
|------|-----|
| Casual | "Give your hands a break, start free today" |
| Direct | "Try it free right now" |
| Benefit | "Start turning your voice into clean text, free" |
| Urgency | "Start free →" |

## Image direction

When the placement allows an image, brief the designer to:
- Show the transformation (messy input → clean output)
- Include one piece of social proof if there's room
- Keep on-image text minimal (headline + CTA)
- Use the brand palette and platform badges where relevant

## Formatting rules: avoid AI tells

| Pattern | Rule | Alternative |
|---------|------|-------------|
| Em dashes (—) | Never use | Periods, commas, colons, or "and" |
| "Delve into" | Avoid | "Explore", "look at", "check out" |
| "Leverage" | Avoid | "Use", "with", "through" |
| "Seamlessly" | Avoid | Remove or use "smoothly" |

Examples:
- Bad: "This tool, the voice typing app, works everywhere"
- Good: "This is a voice typing tool that works everywhere"
- Bad: "Get clean text, instantly" (when written with an em dash)
- Good: "Get clean text, instantly" or "Get clean text. Instantly."

## Proof points: keep a verified list

Maintain a table like this and pull only from rows marked Verified. Fill it with your own claims and sources.

| Claim | Status | Source |
|-------|--------|--------|
| {speed claim, e.g. faster than typing} | Verified | Internal testing |
| {language coverage} | Verified | Product spec |
| {works across apps} | Verified | System-level integration |
| {auto-edit feature} | Verified | Core feature |
| {compliance certifications} | Verified | Security/compliance docs |
| {customer testimonial} | Verified | Public endorsement |

## Validation checklist

Before delivering the brief:

- [ ] No em dashes anywhere in copy (critical: signals AI-generated)
- [ ] Character limits respected for all placements
- [ ] Copy matches the selected ICP voice
- [ ] At least 2 variants per placement
- [ ] Proof points are verified, attributable claims (no retired quotes)
- [ ] CTAs are clear and actionable
- [ ] UTM structure is correct, unique link per send date
- [ ] Image direction aligns with brand
