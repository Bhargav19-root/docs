---
title: "Expiration & click limits"
description: "Auto-disable a link after a date, a click count, or both."
---

## What it is

Per-link controls related to time and volume:

- **Expires at** - a timestamp. After it passes, the redirect returns `410 Gone`. **Enforced** at the redirect.
- **Click limit** - a maximum number of clicks recorded on the link.
- **Fallback URL** - alternate destination stored on the record. The redirect routes to it, when the link expires.

## When to use it

- Limited-time promo - set expiry date and time to your sale end. This will hard-block visitors with `410 Gone` after the cutoff.
- Limited-quantity giveaway - record a click limit for reporting, but pair with expiry date and time if you need a true cutoff.
- Embargoed content - set expiration date and time to embargo lift; the link returns `410` until you clear or extend it.

## How to use it

<Steps>
  <Step title="Open Advanced">In the link builder, expand **Advanced**.</Step>
  <Step title="Set expiration">
    Pick a date and time. Once `now > expiresAt`, the redirect returns `410 Gone`.
  </Step>
  <Step title="Set a click limit (informational)">
    Type an integer to record a target. The counter is incremented on each click and surfaced in the link list. Once the click limit is hit, the link stops redirecting.
  </Step>
  <Step title="Optional fallback URL">
    Stored on the record for future use. Not consulted by the current redirect; clearing or setting it has no live effect today.
  </Step>
  <Step title="Save">
    `expiresAt` is editable any time - clear it to re-enable the link, or extend it to push the cutoff out.
  </Step>
</Steps>

<Frame>
  <img src="/images/addlineadvancedsettings.png" alt="Advanced settings panel - Password, Click Limit, Expiration date/time, iOS and Android redirect URL fields" />
</Frame>

## Real-world example

Black Friday flash deal that auto-cuts off at sale end:

```
Destination:   https://acme.com/bf-50-off
expires_at:    2025-11-29T05:00:00Z
click_limit:   500            (recorded for reporting)
Tags:          black-friday, flash
```

When the timer hits, the short URL returns `410 Gone`. If you also need to stop after 500 clicks specifically, set a click limit.

## Common mistakes

<AccordionGroup>
  <Accordion title="Click limit on a viral link">
    Clicks can spike fast. Setting `click_limit=100` for a campaign that suddenly gets 50k impressions cuts off most of your audience.
  </Accordion>
  <Accordion title="Expecting expired links to work for past clicks">
    Past clicks remain in analytics. Expiration only stops *new* redirects.
  </Accordion>
</AccordionGroup>

## Edge cases

<Note>
**HTTP status semantics.** Expired links return `410 Gone`. Archived links return `404`. Soft-deleted workspaces don't 410 - their links continue to resolve until the 7-day purge.
</Note>

<Note>
**Time zones in the UI.** Date picker uses your browser's local time.
</Note>
