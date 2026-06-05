---
title: "UTM Parameter library"
description: "The workspace dictionary of allowed UTM values. Powers autocomplete and consistency."
---

## What are UTMs?

UTMs (Urchin Tracking Modules) are short tags you add to the end of any URL so your analytics tool can tell you exactly where each visitor came from. Without them, GA4 and other tools report most traffic as "Direct" — meaning unknown origin.

A UTM-tagged link looks like this:

```
https://yoursite.com/pricing?utm_source=newsletter&utm_medium=email&utm_campaign=q2-launch
```

When someone clicks it, GA4 reads those tags and records: this session came from `newsletter`, via `email`, for campaign `q2-launch`. You can then compare newsletter vs Google Ads vs LinkedIn in one report, for the same campaign.

The five standard parameters are: `utm_source` (platform), `utm_medium` (channel type), `utm_campaign` (campaign name), `utm_content` (creative variant), and `utm_term` (paid keyword). The first three are the ones that matter most.

---

## What it is

The Parameter library is your workspace's hierarchical dictionary of UTM values:

- **Parents**: the five standard fields - `source`, `medium`, `campaign`, `term`, `content`.
- **Children**: the allowed values under each parent - e.g., under `source`: `google`, `facebook`, `newsletter`, etc.

The link builder's autocomplete pulls from this library.

## When to use it

- You want autocomplete suggestions when team members fill UTMs.
- You want a canonical list of acceptable values that everyone sees.
- You're enforcing values via UTM Rules.

## What gets seeded by default

When the library is empty, you can seed defaults that include:

<Tabs>
  <Tab title="Source">
    `google`, `facebook`, `twitter`, `linkedin`, `instagram`, `tiktok`, `youtube`, `email`, `newsletter`, `bing`, `reddit`, `pinterest`
  </Tab>
  <Tab title="Medium">
    `cpc`, `cpm`, `social`, `email`, `organic`, `referral`, `display`, `video`, `affiliate`, `banner`, `paid_social`, `retargeting`
  </Tab>
  <Tab title="Campaign">
    `spring_sale`, `summer_sale`, `fall_sale`, `winter_sale`, `black_friday`, `cyber_monday`, `product_launch`, `brand_awareness`, `promo`
  </Tab>
  <Tab title="Term">
    `brand`, `generic`, `competitor`, `longtail`
  </Tab>
  <Tab title="Content">
    `banner`, `textlink`, `logolink`, `image`, `video`, `cta_button`, `sidebar`, `header`, `footer`, `variation_a`, `variation_b`
  </Tab>
</Tabs>

The five parents (`source`/`medium`/`campaign`/`term`/`content`) are built-in and can't be deleted. Only their display name and tooltip can be edited. All child values are fully editable.

<Note>
The default seed values are generic starting points. Before using them, check them against your [UTM naming convention](/playbooks/utm-naming-convention) and delete or rename any that don't match — for example, rename `paid_social` to `paid-social` if you're using hyphens as your convention.
</Note>

## How to manage it

<Steps>
  <Step title="Open the library">
    Sidebar → **UTM Parameters**. Tree view: parents on top, children nested.
  </Step>
  <Step title="Seed defaults (first time)">
    If the library is empty, click **Seed defaults**. Running it again won’t duplicate or change anything.
  </Step>
  <Step title="Add a value">
    Click a parent (e.g., `source`) → **Add value**. Required: `name` (display) + `code` (lowercase identifier, becomes the actual UTM value). Optional: `tooltip`, `description`.
  </Step>
  <Step title="Edit / reorder / delete">
    - Edit name and metadata anytime.
    - Delete only if no children depend on it.
  </Step>
</Steps>

<Frame>
  <img src="/images/customutmparam.png" alt="UTM Parameters page - five system parameters on the left, Source values list on the right (Google, Facebook, Twitter, LinkedIn, and more)" />
</Frame>

## Real-world example

A B2B SaaS company customizes the library:

```
source/
├── google
├── linkedin
├── product_hunt
├── partner_capterra
├── partner_g2
└── newsletter

medium/
├── cpc
├── paid_social
├── email
├── content_partnership   ← custom
└── webinar               ← custom
```

The autocomplete now reflects how this team actually drives traffic - partner sites, content partnerships, webinars - not generic SaaS defaults.

## Common mistakes

<AccordionGroup>
  <Accordion title="Mixed-case codes">
    Codes are forced lowercase on insert. `Newsletter` becomes `newsletter`. Don't try to maintain casing here.
  </Accordion>
  <Accordion title="Duplicate codes">
    Codes are unique per workspace. If you try to add a value that already exists (e.g., `google` when it's already there), the save will fail. Check the existing list first.
  </Accordion>
  <Accordion title="Deleting a parent with children">
    You can't delete a parent parameter (like `source`) while it still has child values under it. Delete the child values first, then the parent.
  </Accordion>
  <Accordion title="Treating library as the enforcer">
    Library powers autocomplete — it suggests values but doesn't block anything. To enforce naming standards, configure [UTM Rules](/utm-rules/overview) with prohibited values and character restrictions.
  </Accordion>
</AccordionGroup>

## Edge cases

<Note>
**Seeding is one-time.** The seed function checks for existing system params and returns *"already exist"* if any are present. To restart, manually delete then reseed.
</Note>
