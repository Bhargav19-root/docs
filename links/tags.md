---
title: "Tags"
description: "Lightweight, multi-assign labels for filtering and reporting on links."
---

## What it is

Tags are color-coded labels on links. Each link can have many tags. Each tag belongs to one workspace. Use them for any cross-cutting attribute that doesn't fit a single flat folder.

## When to use it

- Status: `active`, `paused`, `draft`.
- Channel cohort: `paid-search`, `paid-social`, `email`.
- Quarterly review: `q2-2025`, `q3-2025`.
- A/B variants you might compare across campaigns.

## How to use it

<Steps>
  <Step title="Create a tag">
    Sidebar → **Folders & Tags** → **Create tag**. Name it (case-insensitive unique per workspace), pick a hex color (default orange).
  </Step>
  <Step title="Apply on a link">
    From the link builder or the Links list: select the link → **Tags** → pick one or more.
  </Step>
  <Step title="Bulk-tag">
    On the Links list: select multiple links → **Bulk Tag** → add tags.
    - **Add** mode appends without removing existing tags.
  </Step>
</Steps>

## Real-world example

Content team running a quarterly content audit:

| Tag               | Color  | Meaning                              |
| ----------------- | ------ | ------------------------------------ |
| `evergreen`       | Green  | Always-on content                    |
| `seasonal`        | Yellow | Tied to a season/holiday             |
| `experiment`      | Purple | A/B test variants                    |
| `archive-q1-2025` | Gray   | Last quarter, retained for reporting |

A single link can be `seasonal` + `experiment`. Folder might be **Email Campaigns**.

## Common mistakes

<AccordionGroup>
  <Accordion title="Folders pretending to be tags">
    Creating folders for each status (`active`, `paused`)? Use tags. Folders are separate containers for links, not nested hierarchies.
  </Accordion>
  <Accordion title="Duplicate names">
    Tag names are case-insensitive unique per workspace. `Email` and `email` collide.
  </Accordion>
  <Accordion title="Color overload">
    More than 8–10 colors becomes visual noise. Reuse colors with distinct names.
  </Accordion>
</AccordionGroup>

## Edge cases

<Note>
**Tag limit.** Each workspace has a maximum number of tags. Hitting it returns a clear error.
</Note>

<Note>
**Deleting a tag** removes it from every link automatically. Click history is unaffected.
</Note>
