---
name: link-creator
description: Create tracked Dub.co short links for partnerships, creators, and communities. Handles UTM parameters, promo codes, landing pages, and folder organization automatically. Use when creating a new partnership link, creator link, or community deal link.
---

# Link Creator: Partnership Links

Create properly tracked Dub.co short links with standardized UTM parameters, promo codes, and folder organization.

> Adapt the domains, folder IDs, and tag IDs below to your own Dub workspace. The `{FOLDER_ID}` and `{TAG_ID}` placeholders are where your real Dub IDs go. Keep them in a private lookup, not in a shared skill file.

## Workflow

### Step 1: Gather Required Info

Ask the user for (if not already provided):

1. **Partner/creator name**, Who is this link for?
2. **Promo code**, The code to embed (for example, `PARTNER-CODE`)
3. **Link type**, What kind of partnership? (see Link Types below)
4. **Landing page**, Which page should they land on?

### Step 2: Determine Link Type

If not explicitly stated, infer from context or ask:

| Type | When to use |
|------|------------|
| `community` | Community program, member deal, group partnership |
| `youtube` | YouTube creator sponsorship or integration |
| `linkedin` | LinkedIn creator/influencer partnership |
| `podcast` | Podcast sponsorship (pre-roll, mid-roll, host-read) |
| `newsletter` | Newsletter sponsorship placement (one link per send date) |
| `affiliate` | Ongoing affiliate/referral relationship |
| `influencer` | Regional influencer program |

### Step 3: Determine Landing Page

Ask which landing page to use:

| Page | URL | Best for |
|------|-----|----------|
| Main | `wisprflow.ai/` | General audience, broad appeal |
| Developers | `wisprflow.ai/developers` | Developer/engineer audience |
| Leaders | `wisprflow.ai/leaders` | Executives, managers, business leaders |
| Custom | `wisprflow.ai/[path]` | ICP-specific or campaign landing pages |

### Step 4: Apply UTM Standards

Use this table to generate UTM parameters based on link type:

| Type | utm_source | utm_medium | utm_campaign | utm_content | Slug pattern |
|------|-----------|------------|--------------|-------------|-------------|
| `community` | `[partner-name]` | `community` | `[partner]-[program]` | — | `[program-name]` |
| `youtube` | `youtube` | `creator` | `[creator-slug]` | — | `[creator-slug]` |
| `linkedin` | `linkedin` | `creator` | `[creator-slug]` | — | `[creator-slug]` |
| `podcast` | `[podcast-name]` | `podcast` | `[podcast-slug]` | — | `[podcast-slug]` |
| `newsletter` | `[partner-slug]` | `newsletter` | `[partner]-[publication]-[yyyy]-[mm]` | `[placement-type]-[yyyy-mm-dd]` | `[partner]-[mmm][dd]` |
| `affiliate` | `[partner-name]` | `affiliate` | `[partner]-affiliate` | — | `[partner-slug]` |
| `influencer` | `youtube` | `influencer` | `[creator-slug]` | — | `[creator-slug]` |

**Naming rules:**
- All UTM values: lowercase, hyphens for spaces, no special characters
- Slugs: lowercase-with-hyphens for new links
- Promo codes: UPPERCASE-WITH-HYPHENS as provided by your billing/admin system

### Step 5: Build Destination URL

Construct the destination URL:

```
https://wisprflow.ai/[landing-page]?promo_code=[PROMO-CODE]
```

- If landing page is main: `https://wisprflow.ai/?promo_code=[PROMO-CODE]`
- If landing page is `/developers`: `https://wisprflow.ai/developers?promo_code=[PROMO-CODE]`
- If no promo code: omit the `?promo_code=` parameter

### Step 6: Assign to Folder

Route by relationship and partner agency, not just link type. Keep a private folder inventory that maps each bucket to its Dub folder ID. A typical structure:

| Folder | Folder ID | What goes here |
|--------|-----------|----------------|
| Sponsorships | `{FOLDER_ID}` | Newsletter, podcast, and dedicated creator sponsorships; agency-mediated deals without a dedicated agency folder |
| Direct-Managed Creators | `{FOLDER_ID}` | Creators/affiliates you manage directly, no agency |
| Agency: [Agency A] | `{FOLDER_ID}` | Creator deals brokered through a specific agency |
| Agency: [Agency B] | `{FOLDER_ID}` | Creator deals brokered through a second agency |
| Regional Influencers | `{FOLDER_ID}` | Regional influencer cohort |
| Communities | `{FOLDER_ID}` | Community partnership deals |
| Advertising | `{FOLDER_ID}` | Paid ad links (Meta, Google, etc.) |
| To Sort | `{FOLDER_ID}` | Staging bucket, avoid writing here |

**Routing decision tree:**

1. **Is the partner through an agency with a dedicated folder?** → use that agency folder.
2. **Is it a newsletter/podcast sponsorship, or an agency-mediated creator without a dedicated folder?** → `Sponsorships`.
3. **Is it a community partnership?** → `Communities`.
4. **Is it a regional influencer?** → `Regional Influencers`.
5. **Is it a creator you manage directly, no agency?** → `Direct-Managed Creators`.
6. **Is it a paid ad?** → `Advertising`.

When in doubt, ask. Never invent folder names, only real folder IDs from your workspace are valid.

### Tagging (newsletters and podcasts)

Every newsletter/podcast link also gets its partner's tag so reporting rolls up in Dub. Keep one tag per main sponsor in a private lookup. If a partner doesn't have a tag yet, create it first via `POST https://api.dub.co/tags` (the Dub MCP cannot create tags) and add the ID to your lookup.

### Step 7: Confirm Before Creating

Present a summary table to the user before creating:

```
Link Summary:
| Field | Value |
|-------|-------|
| Short URL | ref.wisprflow.ai/[slug] |
| Destination | [full URL with promo code] |
| utm_source | [value] |
| utm_medium | [value] |
| utm_campaign | [value] |
| Folder | [folder name] |
| Conversion tracking | Enabled |
```

Wait for user confirmation.

### Step 8: Create in Dub

Use the Dub create-link tool (or REST `POST /links`) with:
- `url`: the destination URL (with promo_code param, without UTM params, Dub appends those)
- `domain`: your short-link domain (for example, `ref.wisprflow.ai`)
- `key`: the slug
- `folderId`: from your folder lookup
- `utm_source`, `utm_medium`, `utm_campaign`: from the standards table
- `trackConversion`: `true`
- `title`: `Wispr Flow x [Partner Name]`

### Step 9: Confirm

After creation, confirm the short URL, the full redirect URL (destination + UTM params), and the folder assignment.

---

## UTM Medium Reference

These are the only valid medium values for partnership links:

| Medium | Meaning | Groups with |
|--------|---------|-------------|
| `community` | Community partnership deals | Other community programs |
| `creator` | Paid creator sponsorships (YouTube, LinkedIn, etc.) | All creator deals regardless of platform |
| `influencer` | Regional influencer programs | Regional influencer cohort |
| `podcast` | Podcast sponsorships | All podcast deals |
| `newsletter` | Newsletter sponsorships | All newsletter placements |
| `affiliate` | Ongoing affiliate relationships | Affiliate program |

**Why `creator` instead of `social` or `video`:**
- `social` conflicts with organic social posts
- `video` conflicts with paid video ads
- `creator` cleanly groups all creator sponsorships
- Platform is captured in `utm_source` (youtube, linkedin, etc.)

---

## Examples

### Community Partnership
```
Input: a fintech community, COMMUNITY-CODE, community, main page
Output:
  slug: community-program
  url: https://wisprflow.ai/?promo_code=COMMUNITY-CODE
  utm_source: [community-name]
  utm_medium: community
  utm_campaign: [community-name]-program
  folder: Communities
```

### YouTube Creator (Developer Audience)
```
Input: a developer YouTuber, CREATOR-CODE, youtube, /developers
Output:
  slug: [creator-slug]
  url: https://wisprflow.ai/developers?promo_code=CREATOR-CODE
  utm_source: youtube
  utm_medium: creator
  utm_campaign: [creator-slug]
  folder: Direct-Managed Creators
```

### Podcast Sponsorship
```
Input: a VC podcast, PODCAST-CODE, podcast, main page
Output:
  slug: [podcast-slug]
  url: https://wisprflow.ai/?promo_code=PODCAST-CODE
  utm_source: [podcast-slug]
  utm_medium: podcast
  utm_campaign: [podcast-slug]
  folder: Sponsorships
```

---

## Newsletter Per-Placement Example

For a newsletter's flagship primary placement on Apr 17:

```
slug: [partner]-apr17
url: https://wisprflow.ai/
folder: Sponsorships
tag: [partner tag]
utm_source: [partner-slug]
utm_medium: newsletter
utm_campaign: [partner]-flagship-2026-04
utm_content: primary-2026-04-17
title: Wispr Flow x [Partner] Flagship, Primary Apr 17 2026
```

For the next placement on Apr 20, change the slug to `[partner]-apr20` and `utm_content` to `primary-2026-04-20`. The campaign stays the same so the monthly rollup works.

---

## When to Use This Skill

Invoke `/link-creator` when:
- Setting up a new community partnership deal
- Creating a tracking link for a creator sponsorship
- Adding a new affiliate partner link
- Creating a newsletter or podcast sponsorship link
- Any time a promo code needs a tracked short link
