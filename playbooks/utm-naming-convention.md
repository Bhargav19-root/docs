---
title: "UTM naming convention"
description: "An opinionated, copy-paste-ready standard for utm_source, utm_medium, utm_campaign, utm_content, and utm_term — so every link in GA4 lands in the right row."
---

## Why this matters

Every marketer on your team types UTMs differently. `Newsletter` vs `newsletter` vs `news_letter` creates three separate rows in GA4. Six months later, your channel attribution is split across dozens of near-duplicate source/medium combos and no one can tell you what drove pipeline last quarter.

A naming convention costs 30 minutes to set up. The cleanup it prevents costs weeks.

<Note>
This is an opinionated default. Pick the parts that fit your team, enforce them with [UTM Rules](/utm-rules/overview), and update the vocab list quarterly. A convention that gets followed beats a perfect one that doesn't.
</Note>

---

## The format

```
utm_source   = {channel}
utm_medium   = {traffic-type}
utm_campaign = {quarter}-{theme}
utm_content  = {creative-variant}
utm_term     = {paid-keyword}          ← paid search only
```

**Rules that apply everywhere:**
- Lowercase only — `google` not `Google`
- Hyphens between words — `q2-launch` not `q2_launch` not `Q2 Launch`
- No spaces, no slashes, no special characters
- No dates inside `utm_campaign` (the date is in your analytics tool, not your UTM)
- No PII — no email addresses, user IDs, or names

---

## Parameter guide

### utm_source — where the traffic came from

Use the **platform name**, lowercase, hyphen-separated. Lock this to a fixed vocab list.

| Value | Use for |
|---|---|
| `google` | Google Ads, Google Shopping |
| `meta` | Facebook Ads, Instagram Ads |
| `linkedin` | LinkedIn Ads |
| `tiktok` | TikTok Ads |
| `x` | X (Twitter) Ads |
| `newsletter` | Your own email sends |
| `youtube` | YouTube Ads or organic video |
| `podcast` | Podcast sponsorships |
| `affiliate` | Affiliate/referral partners |
| `partner-{name}` | Named partnerships — e.g. `partner-hubspot` |
| `direct` | QR codes, offline, vanity URLs |
| `organic-social` | Non-paid social posts (Instagram, LinkedIn, X) |

<Warning>
Don't use `email` as a source. It's ambiguous — is it your newsletter, a cold outreach sequence, or a transactional send? Use `newsletter`, `outbound`, or `transactional` instead.
</Warning>

**Enforce it:** Add an `allowed_values` rule on `utm_source` in [UTM Rules](/utm-rules/overview). Anyone using an off-list value gets a rejection on save — not a messy row in GA4 three weeks later.

---

### utm_medium — what kind of traffic

Medium = the marketing mechanism, not the platform.

| Value | Use for |
|---|---|
| `cpc` | Cost-per-click paid search (Google, Bing) |
| `paid-social` | Any paid social placement |
| `email` | All email — newsletter, nurture, outbound |
| `display` | Banner/programmatic display |
| `video` | Pre-roll, connected TV, YouTube TrueView |
| `affiliate` | Revenue-share or performance partner links |
| `organic-social` | Non-paid social posts |
| `podcast` | Audio sponsorship read |
| `qr` | QR codes (physical → digital) |
| `referral` | Inbound from other sites (unpaid) |

<Note>
GA4 uses `medium` to populate the **Default channel grouping** report. Stick to these values and your channels will auto-group correctly. Invent your own and they fall into "Unassigned."
</Note>

---

### utm_campaign — what campaign this link belongs to

Pattern: **`{quarter}-{theme}`**

```
q1-brand-search
q2-pricing-relaunch
q3-enterprise-outbound
q4-black-friday
evergreen-free-trial
```

Rules:
- Always start with the quarter (`q1` / `q2` / `q3` / `q4`) — or `evergreen` for always-on
- Theme is 1–3 words, hyphen-separated, describing the campaign's purpose
- No year in the value — your analytics date filter handles that
- Same campaign name across all channels that belong to one campaign

<Tip>
If your Google Ads and your newsletter and your LinkedIn post are all promoting the same Q2 pricing page, they should all share `utm_campaign=q2-pricing-relaunch`. That's how you see cross-channel campaign performance in one row.
</Tip>

---

### utm_content — which creative or placement

Use `utm_content` to tell variants apart within a campaign + channel combo.

Common patterns:

| Pattern | Example | Use for |
|---|---|---|
| `{creative-name}` | `hero-cta-blue` | A/B ad creative variants |
| `{placement}` | `sidebar` `footer` `inline` | Placement within a page/email |
| `{subject-line-variant}` | `subject-a` `subject-b` | Email subject line tests |
| `{cta-copy}` | `start-free-trial` `see-pricing` | CTA copy variants |
| `{format}` | `video` `static` `carousel` | Ad format |

Leave `utm_content` **blank in templates** — fill it per link. If you bake it into a template, every link inherits the same content value and the variant data is useless.

---

### utm_term — paid search keywords only

`utm_term` = the keyword that triggered the ad. Used almost exclusively for paid search.

```
utm_term=utm+tracking+tool
utm_term=link+shortener+for+marketing
utm_term=bitly+alternative
```

If you're not running paid search: leave it empty. Don't repurpose `utm_term` for audience segments or targeting notes — that data belongs in your ad platform, not your UTM.

---

## Channel cheatsheet

Copy-paste starting points per channel. Fill `utm_campaign` and `utm_content` per link.

<Tabs>
  <Tab title="Google Ads">
    ```
    utm_source=google
    utm_medium=cpc
    utm_campaign=q2-brand-search
    utm_content=headline-a
    utm_term={keyword}
    ```
    Use `{keyword}` as a literal ValueTrack parameter in Google Ads — it auto-populates the triggering keyword.
  </Tab>
  <Tab title="Meta Ads">
    ```
    utm_source=meta
    utm_medium=paid-social
    utm_campaign=q2-retargeting
    utm_content=carousel-pricing
    ```
    Meta auto-populates `utm_content` if you use `{{ad.name}}` in the URL parameter field — but stick to your own naming pattern for consistency across platforms.
  </Tab>
  <Tab title="LinkedIn Ads">
    ```
    utm_source=linkedin
    utm_medium=paid-social
    utm_campaign=q2-enterprise-demand
    utm_content=cta-book-demo
    ```
    LinkedIn's `{{CAMPAIGN_NAME}}` macro inserts the campaign name. Override it with your standard pattern instead of letting LinkedIn name it.
  </Tab>
  <Tab title="Newsletter / Email">
    ```
    utm_source=newsletter
    utm_medium=email
    utm_campaign=q2-product-update
    utm_content=hero-cta
    ```
    Every link in a single email send should share the same `utm_campaign`. Use `utm_content` to tell the hero CTA from the footer link from the inline text link apart.
  </Tab>
  <Tab title="Organic Social">
    ```
    utm_source=organic-social
    utm_medium=organic-social
    utm_campaign=evergreen-product-awareness
    utm_content=linkedin-post-may-19
    ```
    Source and medium are the same here — that's intentional and how GA4 groups organic social correctly. Use `utm_content` to identify the specific post.
  </Tab>
  <Tab title="Affiliate / Partner">
    ```
    utm_source=partner-hubspot
    utm_medium=affiliate
    utm_campaign=evergreen-integration-promo
    utm_content=blog-inline
    ```
    Name the partner in `utm_source` using the `partner-{name}` pattern. That way you can filter GA4 by source to see partner-by-partner performance without needing a separate dimension.
  </Tab>
  <Tab title="QR Codes / Offline">
    ```
    utm_source=direct
    utm_medium=qr
    utm_campaign=q2-event-booth
    utm_content=conference-badge
    ```
    QR codes generated in linkutm carry the short link + these UTMs. Attendees scanning the badge → `source=direct / medium=qr` in GA4.
  </Tab>
</Tabs>

---

## Bad → good examples

| Before | Problem | After |
|---|---|---|
| `utm_source=Email` | Caps → splits from `email` in GA4 | `utm_source=newsletter` |
| `utm_source=email` | Ambiguous — which email type? | `utm_source=newsletter` |
| `utm_medium=Social Media` | Spaces + caps | `utm_medium=paid-social` |
| `utm_campaign=Q2 2025 Campaign` | Spaces, caps, year | `utm_campaign=q2-brand-awareness` |
| `utm_campaign=newsletter_may_19_2025` | Date baked in, will duplicate each week | `utm_campaign=q2-weekly-digest` |
| `utm_content=` *(empty)* | No way to tell creative variants apart | `utm_content=hero-cta` |
| `utm_term=linkedin` | Term field used for channel | Delete — that's what source/medium is for |
| `utm_source=FB` | Abbreviation — won't match `meta` filter | `utm_source=meta` |
| `utm_campaign=test` | Will pollute prod data, no meaning | Block with UTM Rules prohibited values |

---

## Enforce it with UTM Rules

Setting this convention once doesn't help if someone ignores it two weeks later. Pair this playbook with [UTM Rules](/utm-rules/overview) to make the convention self-enforcing.

**Minimum ruleset to configure:**

<Steps>
  <Step title="Force lowercase + hyphen">
    Enable `forceLowercase: true` and set `spaceCharacter: "-"`. This catches 80% of drift automatically.
  </Step>
  <Step title="Lock utm_source to your vocab">
    Add a Required Field rule: `validationType=allowed_values` on `utm_source`. Paste in your approved source list. Anyone using `FB`, `Email`, or `Insta` gets rejected on save.
  </Step>
  <Step title="Lock utm_medium to your vocab">
    Same rule on `utm_medium`. Your allowed list: `cpc`, `paid-social`, `email`, `display`, `video`, `affiliate`, `organic-social`, `podcast`, `qr`, `referral`.
  </Step>
  <Step title="Require utm_campaign">
    Required Field rule: `validationType=not_empty` on `campaign`. No campaign name, no link saved.
  </Step>
  <Step title="Block test / draft values">
    Add `prohibitedValues: ["test", "draft", "tbd", "todo", "xxx"]`. Prevents test links from leaking into production data.
  </Step>
  <Step title="Auto-fill medium from source (optional)">
    Add Conditional Logic rules for common pairs:
    - `if source=google → set medium=cpc`
    - `if source=newsletter → set medium=email`
    - `if source=meta → set medium=paid-social`
    
    Reduces manual entry errors on high-volume link creation.
  </Step>
</Steps>

---

## Governance

A naming convention rots if no one owns it. Assign these before you ship.

| Role | Responsibility | Cadence |
|---|---|---|
| **Convention owner** (usually MOPs lead) | Approves new source/medium values, updates UTM Rules allowed lists, resolves disputes | On-demand + quarterly review |
| **All link creators** | Use linkutm templates for every new link; never hand-type UTMs | Per link |
| **Analytics owner** | Flags new GA4 "Unassigned" rows as signal that convention has drifted | Weekly |

**Adding a new source or medium:**
1. Convention owner approves the new value
2. Add it to the `allowed_values` list in UTM Rules
3. Create a new template for the channel (see [Create a template](/utm-templates/create-template))
4. Update this playbook

Don't let individuals add new values ad hoc. One rogue `utm_source=IG` takes one week to create and six months to clean up.

---

## Quick-start checklist

<Steps>
  <Step title="Copy the allowed source and medium lists above">
    Edit them to match your actual channels. Delete any you don't use.
  </Step>
  <Step title="Configure UTM Rules">
    Minimum: `forceLowercase`, `source allowed_values`, `medium allowed_values`, `campaign not_empty`.
  </Step>
  <Step title="Create templates for your top 5 channels">
    Newsletter, Google Ads, Meta, LinkedIn, and your highest-volume partner. See [Create a template](/utm-templates/create-template).
  </Step>
  <Step title="Run your existing links through the audit">
    Filter GA4 → Source/Medium report → look for rows with caps, spaces, or off-list values. Those are your cleanup targets.
  </Step>
  <Step title="Share this page with the team">
    Bookmark it. Link to it in your team wiki. This is the source of truth — not a Notion doc only you can find.
  </Step>
</Steps>
