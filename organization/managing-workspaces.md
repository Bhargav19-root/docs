---
title: "Managing workspaces"
description: "Create, rename, soft-delete, restore, or permanently delete a workspace."
---

## What it is

Operations on a workspace: create, update name/slug/logo, switch between workspaces, soft-delete (trash), restore, permanent delete.

## How to create

<Steps>
  <Step title="Open workspace switcher">
    Top-left of the dashboard → **+ New workspace**.
  </Step>
  <Step title="Name + slug">
    Name is the display name. Slug must be lowercase alphanumeric + hyphens; system also generates one from the name + 6-char suffix if you don't specify.
  </Step>
  <Step title="Done">
    You become the **owner**. The workspace gets the system default short domain attached automatically. UTM rules start at defaults.
  </Step>
</Steps>

## How to update

<Steps>
  <Step title="Open workspace settings">
    Sidebar → **Settings** → **Workspace** (or `/{slug}/settings`).
  </Step>
  <Step title="Edit name, slug, logo">
    - Name: case-insensitive unique per owner.
    - Slug: must remain unique globally.
    - Logo: image upload.
  </Step>
</Steps>

## How to delete

Two-stage delete process for safety:

<Steps>
  <Step title="Soft delete (trash)">
    Settings → **Danger zone** → **Delete workspace**. Type `delete/{slug}` to confirm.

    The workspace moves to trash. Members get a notification email. **Workspace remains restorable for 7 days.**

  </Step>
  <Step title="Restore (within 7 days)">
    Settings (or trash view) → **Restore**. Owner only. Workspace becomes active again, members regain access.
  </Step>
  <Step title="Permanent delete">
    After 7 days, the workspace is purged automatically. Or owner can hard-delete immediately by confirming again — owner email gets a final confirmation.

    All data is gone: links, click history, templates, domains, members. Cannot be recovered.

  </Step>
</Steps>

<Warning>
Permanent delete is irreversible. Click history, custom domains (DNS records remain — you must reassign), member access, and billing history are removed. Export anything you need first.
</Warning>

## Real-world example

Closing out an agency client:

```
Day 0:    Soft-delete "Client: Soylent". Members get email.
Day 1-6:  Client requests final reports — restore, export, soft-delete again.
Day 7+:   Auto-purged. Custom domain (soy.link) becomes orphan; client takes it back via DNS.
```

## Common mistakes

<AccordionGroup>
  <Accordion title="Confusing soft-delete with deactivate">
    Soft-delete blocks workspace use. There's no "pause" mode short of removing members and not creating new links.
  </Accordion>
  <Accordion title="Deleting a workspace with active subscriptions">
    Soft-delete doesn't cancel subscriptions automatically. Cancel billing first via the billing page.
  </Accordion>
</AccordionGroup>

## Edge cases

<Note>
**Only the owner can delete.** Members with `admin` role on the membership table aren't enough.
</Note>

<Note>
**Soft-deleted workspace links still resolve.** Until the 7-day purge, short URLs continue to redirect. After purge, they `404`. If your custom domain is on the workspace, plan the cutover.
</Note>
