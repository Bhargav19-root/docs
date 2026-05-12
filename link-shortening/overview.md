---
title: "Shortening overview"
description: "How linkutm shortens URLs, what domain options exist, and how the redirect works."
---

## What it is

Every link in linkutm gets a short URL: `{domain}/{shortCode}`. Visiting it triggers a server-side `302` redirect to the destination URL with all UTMs appended. Click is recorded with geo, device, browser, OS, referrer.

## When to use it

Always — there's no "long-URL only" mode. Pick which short domain to use per link.

## Domain options

<Tabs>
  <Tab title="System default">
    Every workspace gets a default short domain on creation. No setup needed. Useful for ads where the slug isn't visible to humans (Google Ads, Meta Ads).
  </Tab>
  <Tab title="Custom branded domain">
    Bring your own domain (`go.acme.com`, `acme.link`, etc.). Set up via CNAME. Branded short URLs increase click-through rates and trust on visible channels (email, social, podcasts).

    See [Custom domains](/link-shortening/custom-domains).
  </Tab>
</Tabs>

## How the redirect works

<Steps>
  <Step title="Visitor hits the short URL">
    `GET https://go.acme.com/q2-launch`
  </Step>
  <Step title="System looks up the short code">
    Checks expiration (returns `410 Gone` if past) and archived state (returns `404`).
  </Step>
  <Step title="Records the click">
    Async insert into the click log: timestamp, IP, country/region/city (geoip), user-agent → device/browser/OS, referrer.
  </Step>
  <Step title="Builds the destination URL">
    Appends `utm_source`, `utm_medium`, `utm_campaign`, `utm_term`, `utm_content`, plus any custom UTM keys.
  </Step>
  <Step title="Fires pixels (if any)">
    If the link or workspace has enabled pixels (Facebook, GA4, GTM, TikTok, etc.), serves a brief HTML interstitial that fires the pixels, then JS-redirects.
  </Step>
  <Step title="302 to destination">
    No pixels → direct `302` redirect.
  </Step>
</Steps>

## Real-world example

A podcast sponsor read:

> "Visit go.acme.com/podcast for 20% off."

What happens:
- Listener types `go.acme.com/podcast`.
- linkutm logs the click (country = listener's, device = mobile/desktop, referrer = direct).
- Redirects to `https://acme.com/offer?utm_source=podcast&utm_medium=audio&utm_campaign=q2_launch`.
- The acme.com landing page sees the UTMs and reports them to GA.

## Common mistakes

<AccordionGroup>
  <Accordion title="Sharing the destination URL with UTMs hard-coded">
    Defeats tracking — no centralized click count, no per-channel attribution, no easy edit. Always share the short URL.
  </Accordion>
  <Accordion title="Using HTTP for the short domain">
    Browsers block mixed-content; some platforms (LinkedIn, Slack) refuse HTTP previews. Always HTTPS — automated certs are issued for verified custom domains.
  </Accordion>
  <Accordion title="Pointing a domain that's already in production">
    If `go.acme.com` is already serving a real site, the CNAME swap will break that site. Use a fresh subdomain.
  </Accordion>
</AccordionGroup>

## Edge cases

<Note>
**Pixel interstitial adds ~300ms.** If you don't have pixels configured, the redirect is direct (`302`). Pixels insert a brief HTML page that fires tracking before redirecting via JS.
</Note>

<Note>
**Bare domain.** Hitting `https://go.acme.com/` with no slug returns a not-found response unless your deployment is configured to forward bare-domain hits to a configured `defaultRedirect`. Treat slug-less hits as undefined for now and always include a path.
</Note>

<Note>
**Click counting on archived/expired links.** Archived links return `404` and don't count. Expired links return `410` and don't count.
</Note>

<Note>
**Device, geo, click-limit, and password fields.** These are stored on a link's record but the public redirect does not currently route or block based on them — visitors get the main destination URL with UTMs appended. Use the destination page to handle device or country routing if you need it today.
</Note>
