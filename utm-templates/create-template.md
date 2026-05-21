---
title: "Create a template"
description: "Save a UTM preset for a channel or campaign type."
---

## What it is

Saving a named set of UTM values that can be applied to new links with one click.

## When to use it

You're about to type the same `utm_source` / `utm_medium` combination for the third time. Stop. Make a template.

## How to create one

<Steps>
  <Step title="Open Templates">
    Sidebar → **UTM Templates** → **Create Template**.
  </Step>
  <Step title="Name and Description(optional) ">
    Name shows in the template picker. Description is internal context - when to use this template.
  </Step>
  <Step title="Fill the UTM fields">
    Set the fields you want pre-filled. Leave any field blank if it's not common to the use case.

    | Field | Set if | Leave blank if |
    |---|---|---|
    | `utm_source` | Always | (always set) |
    | `utm_medium` | Always | (always set) |
    | `utm_campaign` | One template per recurring campaign | Per-link campaigns |
    | `utm_term` | Paid search with stable keyword strategy | Otherwise |
    | `utm_content` | Same creative across all links | Different creatives per link |

  </Step>
  <Step title="Save">
    Template is immediately available in the link builder's template picker.
  </Step>
</Steps>

<Frame>
  <img src="/images/createutmtemplate.png" alt="Create Template modal - Template Name, Campaign, Description, Source, Medium, Term, Content fields" />
</Frame>

## Real-world example

Newsletter template - kept loose so one template covers all newsletters:

```
Name:         Newsletter - generic
Description:  Default for any weekly/monthly newsletter send
utm_source:   newsletter
utm_medium:   email
utm_campaign: (blank - set per send)
utm_term:     (blank)
utm_content:  (blank - set per CTA)
```

Per-link, the marketer fills `utm_campaign=weekly_digest_2025_w19` and `utm_content=hero_cta`.

## Common mistakes

<AccordionGroup>
  <Accordion title="Over-specific templates">
    `Newsletter - Week 19 - Hero CTA` becomes a single-use template. Make it generic; vary at link time.
  </Accordion>
  <Accordion title="Inconsistent naming">
    `News - Email`, `Email/Newsletter`, `newsletter_email` all describe the same thing. Settle on a convention before the team builds 30 templates.
  </Accordion>
  <Accordion title="Skipping the description field">
    Six months in, "Q2 Launch - paid" is ambiguous. Describe **when** to use this template, not just what it sets.
  </Accordion>
</AccordionGroup>

## Edge cases

<Note>
**Templates don't enforce.** A user can apply a template, then change every field. To enforce, use [UTM Rules](/utm-rules/overview) (required-field, allowed-values, conditional logic).
</Note>

<Note>
**Editing a template doesn't update past links.** Past links keep the values they had at save-time. Future links using the template get the new values.
</Note>
