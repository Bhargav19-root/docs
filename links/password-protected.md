---
title: "Password-protected links"
description: "Gate access to a link behind a password. Useful for previews, drafts, partner shares."
---

## What it is

A link with a password set has its password stored on the record. The password is captured at link-creation time and surfaced in the link details so a teammate or recipient knows what to enter when prompted.

## When to use it

- Sharing a draft preview with a client before launch (the URL is private; the password is shared context).
- Sending an embargoed press release where you want to remind the recipient of the embargo password verbally.
- Tracking which password-keyed campaign a click came from.

## How to use it

<Steps>
  <Step title="Open Advanced">
    In the create new link panel, click the **Advanced** button in the bottom bar.
  </Step>
  <Step title="Set a password">
    In the **Password Protection** field, type a password.
  </Step>
  <Step title="Save the link">
    The password is stored on the link record.
  </Step>
  <Step title="Share password separately">
    If you intend the recipient to enter it on a destination page that requires it, send the password through a different channel than the link.
  </Step>
</Steps>

<Frame>
  <img src="/images/addlineadvancedsettings.png" alt="Advanced settings panel - Password, Click Limit, Expiration date, and iOS/Android redirect fields" />
</Frame>

## Real-world example

PR team annotating an embargoed share so the recipient knows the embargo password to use on the destination's gated landing page:

```
Destination:  https://acme.com/press/q2-launch     (gated by acme.com auth)
Password:     ember-2025-jun-7                     (label for recipient)
Tags:         press, embargo
Folder:       PR / Q2 Launch
```

The destination page enforces the password; linkutm tracks the click and passes the user through.

## Common mistakes

<AccordionGroup>
  <Accordion title="Assuming it gates the redirect">
    The current public redirect does not block visitors based on the link's password - your destination page must enforce access.
  </Accordion>
  <Accordion title="Reusing one password across many links">
    If one link leaks, all leak. Generate per-link.
  </Accordion>
</AccordionGroup>

## Edge cases

<Note>
**Password and expiration interact at the redirect layer.** Past the expiry date, the link returns `404 Not Found` regardless of any password.
</Note>
