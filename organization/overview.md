---
title: "Workspaces & organization"
description: "How linkutm structures multi-team, multi-client setups."
---

## What it is

The mental model:

- **Account** — your user. Can belong to many workspaces.
- **Workspace** — the unit of isolation. All links, folders, tags, templates, UTM rules, custom domains, pixels, API keys, analytics, billing, and members live here.
- **Member** — a user attached to a workspace with a role (`owner`, `member`, custom).
- **Folders** — sub-organization _within_ a workspace.

There's no concept of "organization" above workspace. Run multiple workspaces (e.g., per client, per brand) on one account.

## When to use multiple workspaces

<Tabs>
  <Tab title="Agency, multi-client">
    One workspace per client. Their links/domains/templates/billing isolated. Owner moves between workspaces from the workspace switcher.
  </Tab>
  <Tab title="Multi-brand company">
    One workspace per brand. Different custom domains per brand (`go.acme.com`, `pro.acme.link`).
  </Tab>
  <Tab title="Internal vs external">
    One workspace for marketing-public links, one for internal/dogfood links. Cleaner analytics, separate access control.
  </Tab>
  <Tab title="Don't multiply">
    Don't create a workspace per campaign or per quarter. Use [folders](/links/folders) for that.
  </Tab>
</Tabs>

## Real-world example

Acme Marketing Agency:

```
Account: jane@acme-agency.com
Workspaces:
├── Acme Internal       (slug: acme-internal)        — owner: jane
├── Client: Globex      (slug: client-globex)        — owner: jane
├── Client: Initech     (slug: client-initech)       — owner: jane
└── Client: Soylent     (slug: client-soylent)       — owner: jane

Each workspace:
├── Members (with per-client account managers)
├── Domains (each client's branded short domain)
├── Templates (per-client UTM presets)
├── UTM Rules (per-client naming convention)
└── Billing (per-client)
```

## Common mistakes

<AccordionGroup>
  <Accordion title="Workspace per campaign">
    Creates billing fragmentation and member-management overhead. Use folders.
  </Accordion>
  <Accordion title="Sharing one workspace across two clients">
    Defeats data isolation. Members of Client A can see Client B's links.
  </Accordion>
  <Accordion title="Confusing slug with name">
    Slug is the URL identifier (`acme-internal`). Name is the display name (`Acme Internal`). They're independent.
  </Accordion>
</AccordionGroup>

## Edge cases

<Note>
**Workspace name unique per owner.** You can't own two workspaces with the same name (case-insensitive). Different owners can.
</Note>

<Note>
**Slug uniqueness.** Slugs are globally unique across linkutm.
</Note>
