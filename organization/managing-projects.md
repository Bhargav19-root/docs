---
title: "Projects (folders within workspaces)"
description: "Use separate folders as project containers when one workspace holds multiple initiatives."
---

## What it is

linkutm doesn't have a separate "project" entity. The equivalent is a **separate folder inside a workspace**. Use one folder per campaign, brand, or client initiative when you don't need full data isolation.

Folders are flat. They don't support nesting, parent/child relationships, or linked folder structures.

## When to use folder-as-project

| Need                                               | Use             |
| -------------------------------------------------- | --------------- |
| Data isolation, separate billing, separate members | A new workspace |
| Logical grouping, shared team, shared domain       | A folder        |
| Per-campaign tracking                              | A folder        |
| Per-quarter rollup                                 | A folder        |

If multiple stakeholders need access but **shouldn't see each other's links**, use workspaces. If everyone on the team already sees everything, use folders.

## How to set up

<Steps>
  <Step title="Create separate folders for each project">
    Sidebar -> **Folders** -> **New Folder**. Examples: `Q2 Launch`, `Brand Refresh`, `Client: Globex`.
  </Step>
  <Step title="Create additional folders for channels if needed">
    If you want to separate channels, create each one as its own folder. For example: `Q2 Launch - Paid Search`, `Q2 Launch - Paid Social`, `Q2 Launch - Email`, `Q2 Launch - Organic`.
  </Step>
  <Step title="Set a default folder">
    Make the active project the **Default** folder. The link builder UI pre-selects it for new links unless you pick another.
  </Step>
  <Step title="Apply tags for cross-project attributes">
    `experiment`, `evergreen`, `paused` - cross-cuts every project. See [Tags](/links/tags).
  </Step>
</Steps>

## Real-world example

Internal SaaS marketing team running three projects in one workspace:

```
Workspace: Acme Marketing

Folders:
- Q2 Product Launch
- Q2 Product Launch - Paid Search
- Q2 Product Launch - Paid Social
- Q2 Product Launch - Email
- Q2 Product Launch - PR
- Lifecycle Email
- Lifecycle Email - Onboarding
- Lifecycle Email - Retention
- Lifecycle Email - Win-back
- Always-On
- Always-On - Brand Search
- Always-On - Organic CTA
```

Tags: `experiment`, `paused`, `seasonal` - apply across folders.

## Common mistakes

<AccordionGroup>
  <Accordion title="Reaching for a new workspace when a folder fits">
    Workspaces are heavy: separate billing, separate domains, separate members. If you don't need isolation, use a folder.
  </Accordion>
  <Accordion title="Expecting nested folders">
    Folders are separate, flat containers. Use naming conventions or tags to represent channel, quarter, or status instead of nesting folders.
  </Accordion>
  <Accordion title="Project sprawl">
    Once a project ends, deactivate or delete its folder. Use **archive** on links if you want them out of default views but kept for analytics.
  </Accordion>
</AccordionGroup>

## Edge cases

<Note>
**Default folder logic.** Only one default per workspace. Setting a new default unsets the old one automatically.
</Note>
