---
title: "UTM Parameter library"
description: "The workspace dictionary of allowed UTM values. Powers autocomplete and consistency."
---

## What it is

The Parameter library is your workspace's hierarchical dictionary of UTM values:

- **Parents**: the five standard fields — `source`, `medium`, `campaign`, `term`, `content`.
- **Children**: the allowed values under each parent — e.g., under `source`: `google`, `facebook`, `newsletter`, etc.

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

The five parents (`source`/`medium`/`campaign`/`term`/`content`) are **system parameters** — they cannot be deleted, and only their `name` and `tooltip` can be edited. Children are fully editable.

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

The autocomplete now reflects how this team actually drives traffic — partner sites, content partnerships, webinars — not generic SaaS defaults.

## Common mistakes

<AccordionGroup>
  <Accordion title="Mixed-case codes">
    Codes are forced lowercase on insert. `Newsletter` becomes `newsletter`. Don't try to maintain casing here.
  </Accordion>
  <Accordion title="Duplicate codes">
    Codes are unique per workspace. Trying to add `google` when it exists returns `409 Conflict`.
  </Accordion>
  <Accordion title="Deleting a parent with children">
    Blocked. Returns `400` with `"Cannot delete parameter with N child value(s). Delete child values first."`
  </Accordion>
  <Accordion title="Treating library as the enforcer">
    Library powers autocomplete. To **enforce** allowed values, configure a [Required field rule](/utm-rules/overview) with `validation_type=allowed_values`.
  </Accordion>
</AccordionGroup>

## Edge cases

<Note>
**Seeding is one-time.** The seed function checks for existing system params and returns *"already exist"* if any are present. To restart, manually delete then reseed.
</Note>
