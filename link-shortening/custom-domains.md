---
title: "Custom domains"
description: "Set up a branded short domain (e.g., go.acme.com) via CNAME."
---

## What it is

Use a domain you own as the short-URL host. `go.acme.com/q2-launch` instead of the system default. SSL is auto-issued once the CNAME verifies.

## When to use it

- Customer-facing channels: email, social, podcasts, packaging.
- Anywhere the URL is read by a human and brand trust matters.
- Multi-brand agencies running per-client domains.

Skip it for ads-only links - auto-generated codes on the system domain are fine and the URL isn't visible.

## How to set one up

<Steps>
  <Step title="Pick a subdomain">
    Recommended: a fresh subdomain like `go.acme.com`, `link.acme.com`, `acme.link`. Don't use a domain or subdomain already serving production traffic.
  </Step>
  <Step title="Add the domain in linkutm">
    Sidebar → **Domains** → **Add Domain**. Enter `go.acme.com`. The system creates the record in `pending` status and shows you the CNAME target.
  </Step>
  <Step title="Configure DNS">
    In your DNS provider (Cloudflare, Route 53, etc.):

    | Type | Name | Value | TTL |
    |---|---|---|---|
    | `CNAME` | `go` | `cname-staging.linkutm.com` (or your env's target) | 300–3600 |

    The exact CNAME target is shown in the Domains page after you add the domain.

    <Warning>If you use Cloudflare, set the record to **DNS only** (gray cloud), not proxied. Proxying breaks SSL provisioning.</Warning>

  </Step>
  <Step title="Verify">
    Click **Verify** on the domain row. The system runs a CNAME lookup against your DNS. Status flips to `active` once the CNAME points correctly. SSL is issued automatically within ~1 minute.
  </Step>
  <Step title="Set as default (optional)">
    Mark the domain as **Default** so new links use it without picking. Only one default per workspace.
  </Step>
  <Step title="(Optional) Default redirect">
    You can set a `defaultRedirect` URL on the domain record. Whether bare-domain hits forward to it depends on your deployment's edge configuration - verify by visiting `https://go.acme.com/` after saving.
  </Step>
</Steps>

<Frame>
  <img src="/images/domainsscreen.png" alt="Domains page - list of custom and system domains with Verified status badges" />
</Frame>

<Frame>
  <img src="/images/addcustomdomain.png" alt="Add Custom Domain modal - domain field, optional default redirect, and DNS setup note" />
</Frame>

## Real-world example

Acme has two brands, two domains:

```
Workspace: Acme Main
Domain:    go.acme.com  (default, verified, active)

Workspace: Acme Pro
Domain:    pro.acme.link  (default, verified, active)
```

Marketers in Acme Main create links on `go.acme.com`; Pro team on `pro.acme.link`. Per-workspace branding stays clean.

## Common mistakes

<AccordionGroup>
  <Accordion title="Cloudflare proxy enabled">
    Orange-cloud (proxied) breaks the CNAME lookup and SSL handshake. Set to gray-cloud (DNS only).
  </Accordion>
  <Accordion title="Apex domain (no subdomain)">
    `acme.com` directly is rarely a good idea - most DNS providers won't allow CNAME at apex, and it conflicts with your main site. Use a subdomain.
  </Accordion>
  <Accordion title="Verifying before DNS propagates">
    DNS changes can take minutes to hours. If verification fails, re-check with `dig CNAME go.acme.com` and retry.
  </Accordion>
  <Accordion title="Deleting a domain that has links">
    Returns `400 Bad Request` if any link uses it. Reassign or delete the links first.
  </Accordion>
</AccordionGroup>

## Edge cases

<Note>
**Domain limit.** Each workspace has a maximum number of custom domains. If you reach it, remove an unused one before adding another.
</Note>

<Note>
**Renaming a domain.** Editing the `domain` field resets verification. Re-verify after the rename.
</Note>

<Note>
**System default cannot be deleted. It exists for new workspaces to function out of the box.
</Note>
