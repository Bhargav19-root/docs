---
title: "Manage templates"
description: "Edit, sort, and audit usage of your templates."
---

## What it is

The Templates page shows all workspace templates with usage counts, status, and edit/delete actions.

## When to use it

- Quarterly cleanup of unused templates.
- Auditing which channels actually drive volume.
- Renaming templates after a brand/strategy shift.

## How to manage them

<Steps>
  <Step title="List view">
    Sidebar → **UTM Templates**. Default sort: active templates first, then most-recently-created.
  </Step>
  <Step title="Search">
    Search matches name, description, source, medium, campaign — useful when you have 50+ templates.
  </Step>
  <Step title="See usage">
    Each template shows the usage count — how many times it's been applied to a link. Templates with 0 uses after a month are candidates for cleanup.
  </Step>
  <Step title="Edit">
    Click any template → **Edit**. Update name, description, or any UTM field. Past links unaffected.
  </Step>
  <Step title="Delete">
    **Delete**: permanent. Past links keep their values, but the template is gone.
  </Step>
</Steps>

## Real-world example

Quarterly audit of an agency workspace:

| Template             | Uses | Action                    |
| -------------------- | ---- | ------------------------- |
| Google Brand Search  | 412  | Keep                      |
| Newsletter — generic | 287  | Keep                      |
| Test — Don't Use     | 0    | Delete                    |
| Old Logo Refresh     | 6    | Delete (retired strategy) |

## Common mistakes

<AccordionGroup>
  <Accordion title="Editing a template assuming retroactive changes">
    Past links keep their original values. Edits affect future applications only.
  </Accordion>
</AccordionGroup>

## Edge cases

<Note>
 Use the *Most-used templates* section on the UTM Templates page to identify high-leverage templates worth refining.
</Note>
