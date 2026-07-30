---
name: newsletter-copy
description: "Generate newsletter sponsorship copy with 2-3 ready-to-paste variants, tracking URLs via link-creator, and placement-spec compliance. Pulls approved angles from an upstream ICP campaign when applicable. Use when asked 'newsletter ad', 'sponsorship copy', 'newsletter placement', 'email sponsorship', 'creator newsletter', or 'partner handoff doc'. For copy polish see copy-editing."
---

# Newsletter Copy Generator

Generate newsletter sponsorship copy briefs with ready-to-paste variants optimized for conversion. This skill produces complete copy briefs including multiple variants, tracking URLs, and placement specs.

> Adapt the paths, domains, and IDs below to your own setup. This is the anchor of a sponsorship waterfall: it ingests a deal, researches the audience and prior performance, writes copy on proven best practices, then hands off to link-creator for tracked links and to copy-editing / writing for the final voice pass.

## Pre-flight reminders

Before generating copy, check the per-user state file for `reminders` whose `surface_when` matches today AND whose `surface_trigger` includes `newsletter-copy invocation`. If one matches, surface it at the top of the output and list the pending placements whose submit-by dates are within 7 days.

## Integration with an upstream ICP campaign

When a newsletter placement targets an ICP that already has a campaign package, read the campaign's `messaging/approved-angles.md` before writing. The newsletter copy becomes a short-form render of the anchor angle for the most relevant subgroup.

Handoff flow:

- An ICP campaign produces angle cards
- `/newsletter-copy` pulls the subgroup-relevant card and writes 2-3 newsletter-length variants
- `/link-creator` provides the Dub tracking URL for each variant
- `/copy-editing` polishes before send to partner
- `/writing` final voice pass

## When NOT to use

- Paid ad copy → generated within the ICP campaign
- General copy review → `/copy-editing`

## Process

1. **Gather inputs**: newsletter name, placement date(s), placement type, campaign goal
2. **Pull partner performance from Dub** (see Phase 0.5 below), required when the partner has ≥1 shipped placement. Drives angle selection.
3. **Load messaging**: pull ICP messaging from your product context
4. **Check specs**: verify character limits and placement constraints
5. **Generate variants**: write 2-3 copy variants per placement, leaning into proven winners and avoiding recently-shipped angles
6. **Create a unique Dub link per placement** (see Tracking Standards below), one short link per date, tagged with the partner, in the Sponsorships folder
7. **Deliver brief**: complete brief using assets/copy-brief-template.md, with the performance-analysis table at the top so rationale is transparent
8. **Save the brief** to `sponsorships/copy/{partner-slug}/YYYY-MM-DD-{publication}-{placement}.md` (one file per send date, see File Organization below)

## File Organization

Every sponsorship brief lives under `sponsorships/copy/`.

### Rules

- **One folder per partner.** Folder name is the lowercase-hyphenated partner slug.
- **One file per placement.** File name is `YYYY-MM-DD-{publication}-{placement}.md`.
  - `YYYY-MM-DD` = send date
  - `{publication}` = specific show/newsletter (for example, `flagship`, `ai`, `tech`, `dev`, `founders`, `pm`)
  - `{placement}` = ad unit (for example, `primary`, `secondary`, `quicklinks`, `takeover`, `midroll`)
- **Never merge multiple send dates into one file.** If you're drafting two placements on the same day, write two separate files so each has its own Dub link, compliance check, and sign-off trail.
- **`_library/`** inside a partner folder = multi-placement planning docs (quarterly plans, master briefs). Overviews, not the final copy that ships.
- **`_archive/`** inside a partner folder = superseded drafts, deprecated messaging. Keep for reference, never ship from here.
- **New partner?** Create the folder using the partner slug and note any quirks in a partner-specific README (for example, a partner with multiple publications under one brand).

## Required Inputs

| Field | Required | Description |
|-------|----------|-------------|
| Newsletter Name | Yes | The specific newsletter and publication |
| Placement Type | Yes | Primary, Secondary, Subject Line |
| Campaign Goal | Optional | Awareness, Trial Signups, Upgrades |
| ICP | Optional | Will infer from newsletter audience |

## Placement Specs

| Placement | Char Limit | Purpose |
|-----------|------------|---------|
| Subject Line | ≤45 chars | Inbox hook (rarely available) |
| Preheader | 50-90 chars | Preview text |
| Primary | 150-250 words | Main ad unit (most common) |
| Secondary | 100-125 words | Shorter placement |

## Phase 0: Silent Context Load

Before generating any copy, silently read your shared product context. Extract:
- `company.icps`, use for audience matching per newsletter
- `company.messaging.value_props`, use as proof points and angle sources
- `company.messaging.differentiators`, use when claims need backing

If these fields are still unpopulated, proceed and infer the ICP from the newsletter audience. Flag at the end.

## Phase 0.5: Performance Pre-Flight (REQUIRED)

Before drafting any copy, pull performance data for prior placements with this partner. Past performance is the single best signal for what angle to write next. **This step is required when the partner has ≥1 shipped placement** (skip only for net-new partners with no history).

### Step 1: Pull placement-level data from Dub

Use the Dub REST API directly (the workspace-ID MCP lookup can 404):

```bash
source .env && curl -s -H "Authorization: Bearer $DUB_API_KEY" \
  "https://api.dub.co/links?tagIds={PARTNER_TAG_ID}&pageSize=50&sort=createdAt"
```

Substitute the partner's tag ID from your private lookup. Each link object returns `clicks`, `leads`, `sales`, `saleAmount`, `createdAt`, and `key` (the slug, which encodes the send date).

### Step 2: Cross-reference angles with the brief files

For each link with traffic, open the matching brief in `sponsorships/copy/{partner}/YYYY-MM-DD-{publication}-{placement}.md` and pull the **Angle** line. Performance is meaningless without knowing what angle ran.

### Step 3: Build the analysis table

Render a table at the top of the new brief:

| Date | Placement | Angle | Clicks | Leads | Sales | $ | Lead CVR |

Order by send date. Compute lead CVR = leads / clicks.

### Step 4: Identify winners, losers, and recent angles

Write 3-5 bullets under the table covering:

- **Top performer by clicks / sales / $.** The structural pattern to lean into.
- **Top performer by lead CVR.** The hook pattern to lean into.
- **Anomalies** (a placement with near-zero clicks usually means it didn't ship, not that the angle failed, flag, don't penalize).
- **Recently-shipped angles** (last 30 days). Avoid these to prevent fatigue on overlapping subscriber bases.
- **Implication for this placement.** State the angle choice and why.

### Step 5: Drive angle selection from the read

The copy you write should clearly inherit from the analysis. If you pick a different angle than the data supports, justify it.

### When to skip Phase 0.5

- Net-new partner with no shipped placements
- Partner tag does not exist yet (create via `POST /tags` first)
- Same-week reshoot of a placement already drafted (use the existing draft's analysis)

## ICP Messaging

Pull ICP messaging from your shared product context. If not yet populated, use defaults like these until the context is refreshed:

- **Knowledge Worker:** Speed (type faster by speaking), ease, works everywhere
- **Leaders/Executives:** ROI, team productivity, premium positioning
- **Developers:** IDE integration, syntax awareness, prompt power

## Critical Copy Rules

1. **No em dashes (—) and no double hyphens (--)**, both signal AI-generated copy. Restructure with periods, commas, or parentheses instead.
2. **Match ICP voice to newsletter audience**, tech newsletters get developer messaging.
3. **Include 2+ variants per placement**, for testing and flexibility.
4. **Use verified proof points only**, keep an approved-claims reference and pull from it.
5. **Stay under character limits**, newsletters enforce strict limits.
6. **Unique link per placement**, never reuse a short link across multiple send dates.

## Tracking Standards (Dub.co)

Every newsletter placement gets its own Dub short link so click attribution lands on the specific send date.

### Link pattern

| Field | Value |
|-------|-------|
| Domain | `ref.wisprflow.ai` |
| Slug | `{partner}-{mmm}{dd}` (readable, year-implicit, for example `partnername-apr17`) |
| Destination | `https://wisprflow.ai/` (or ICP-specific page if targeted) |
| Folder | **Sponsorships** (`{FOLDER_ID}`) |
| Tag | The partner's own tag (one tag per main sponsor) |
| Track conversion | `true` |
| Title | `Wispr Flow x {Partner} {Publication} — {Placement} {Date}` |

### UTM shape

| Param | Value | Example |
|-------|-------|---------|
| `utm_source` | `{partner-slug}` — one source per partner, groups all publications | `partnername` |
| `utm_medium` | `newsletter` | `newsletter` |
| `utm_campaign` | `{partner}-{publication}-{yyyy}-{mm}` (monthly rollup per publication) | `partnername-flagship-2026-04` |
| `utm_content` | `{placement-type}-{yyyy-mm-dd}` (unique per placement) | `primary-2026-04-17` |

### Partner tags

Keep one tag per main sponsor in a private lookup. **New partner?** Create the tag first via `POST https://api.dub.co/tags` (the Dub MCP cannot create tags), then add the ID to your lookup and to your `/link-creator` configuration.

### How to create the link

Call your Dub create-link tool with the fields above, or hand off to `/link-creator`. The link returned is what you paste into the copy; Dub appends the UTMs server-side on redirect.

## Output Format

Deliver a complete copy brief using [assets/copy-brief-template.md](assets/copy-brief-template.md) with:
- Campaign context and goals
- 2-3 copy variants per placement
- Character counts and compliance checks
- UTM tracking URLs
- Proof point sources
- Approval checklist

## Cross-References

- **copywriting**: for general marketing copy
- **copy-editing**: for copy review and improvement
- **brand-voice**: for brand voice consistency checks
- **writing**: final humanize pass before send

## References

- [references/framework.md](references/framework.md), placement specs, funnel-stage hook mapping, copy patterns, and validation checklist
- [assets/copy-brief-template.md](assets/copy-brief-template.md), the output brief template
