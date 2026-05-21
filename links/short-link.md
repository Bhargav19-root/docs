---
title: "Short links"
description: "How short codes work, when to customize them, and what makes one valid."
---

## What it is

The short code is the path after your short domain: `go.acme.com/{shortCode}`. linkutm stores one mapping per code; clicks on the code redirect to your full UTM-tagged destination URL.

## When to use it

- Always - every link gets a short code, auto-generated or custom.
- When the slug appears in print, on a podcast read, or anywhere a human reads it aloud.
- Skip customization for ads - auto-generated codes are fine and prevent typos.

## How to set one

<Tabs>
  <Tab title="Auto-generated">
    Leave the **Custom slug** field empty when creating a link. linkutm generates a 7-character alphanumeric code.
  </Tab>
  <Tab title="Custom slug">
    Type your slug in the **Custom slug** field. Allowed: lowercase letters, numbers, hyphens. Keep it short - 3–15 chars reads best.
  </Tab>
</Tabs>

<Frame>
  <img src="/images/addlinkpanel.png" alt="Create Link modal - Short Link field showing auto-generated slug and custom slug input" />
</Frame>

## Real-world example

| Use case             | Slug strategy         | Example                |
| -------------------- | --------------------- | ---------------------- |
| Paid ads             | Auto-generated        | `go.acme.com/k7m2qpz`  |
| Email newsletter CTA | Auto or themed        | `go.acme.com/may-deal` |
| Podcast read         | Memorable, brand-tied | `go.acme.com/acme-pod` |
| QR on print          | Short, no ambiguity   | `go.acme.com/menu`     |

## Common mistakes

<AccordionGroup>
  <Accordion title="Reusing a slug">
    Short codes are globally unique across linkutm. If the system says *"already exists"*, pick another - even if no one in your workspace uses it.
  </Accordion>
  <Accordion title="Long descriptive slugs">
    `q2-2025-product-launch-google-ads` defeats the purpose. Aim for ≤15 characters.
  </Accordion>
  <Accordion title="Special characters">
    Only `a-z`, `0-9`, `-` allowed. Underscores, slashes, periods get rejected.
  </Accordion>
</AccordionGroup>

## Edge cases

<Note>
**Renaming an existing slug.** Edit the link → change **Short code**. Old slug stops working immediately (404). All historical clicks remain attached to the link's analytics.
</Note>

<Note>
**System paths.** Slugs that collide with system paths (`api`, `health`, `docs`, `favicon.ico`) won't resolve through the redirect. Avoid these as custom slugs.
</Note>

<Note>
**Archived links.** An archived link's slug returns 404, not the destination. Unarchive to restore.
</Note>

<Note>
**Expired links.** Past `expiresAt` returns `410 Gone`. Clear or update the expiration to revive.
</Note>
