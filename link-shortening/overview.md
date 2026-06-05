---
title: "Shortening overview"
description: "How linkutm shortens URLs, what domain options exist, and how the redirect works."
---

## What it is

Every link in linkutm gets a short URL: `{domain}/{shortCode}`. Visiting it triggers a server-side `302` redirect to the destination URL with all UTMs appended. Click is recorded with geo, device, browser, OS, referrer.

## When to use it

Always - there's no "long-URL only" mode. Pick which short domain to use per link.

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
  <Step title="Visitor clicks the short link">
    Their browser opens `go.acme.com/q2-launch`.
  </Step>
  <Step title="linkutm validates the link">
    Checks whether the link is active. Expired or archived links show an error page instead of redirecting.
  </Step>
  <Step title="Click is recorded">
    Country, city, device type, browser, OS, and referrer are captured. This is what populates your analytics.
  </Step>
  <Step title="UTMs are appended to the destination URL">
    The visitor's browser is sent to your destination URL with all UTM parameters attached.
  </Step>
  <Step title="Pixels fire (if configured)">
    If you've added pixels (Facebook, TikTok, GTM, etc.) to the link or workspace, they fire before the final redirect. Adds ~300ms but does not affect ad quality scores.
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
    Defeats tracking - no centralized click count, no per-channel attribution, no easy edit. Always share the short URL.
  </Accordion>
  <Accordion title="Using HTTP for the short domain">
    Browsers block mixed-content; some platforms (LinkedIn, Slack) refuse HTTP previews. Always HTTPS - automated certs are issued for verified custom domains.
  </Accordion>
  <Accordion title="Pointing a domain that's already in production">
    If `go.acme.com` is already serving a real site, the CNAME swap will break that site. Use a fresh subdomain.
  </Accordion>
</AccordionGroup>

## Edge cases

<Note>
**Pixel interstitial adds ~300ms.** This only applies if you've enabled pixels (Facebook, TikTok, GTM, etc.) on the link or workspace. With no pixels configured, the redirect is a direct `302` with no added latency. The delay happens before the destination page loads and does not affect Google Ads Quality Score or paid social delivery.
</Note>

<Note>
**Bare domain.** Visiting `https://go.acme.com/` with no slug after it shows a not-found page. Always share the full short URL including the slug.
</Note>

<Note>
**Clicks on archived or expired links don't count.** The link stops working and the click is not recorded.
</Note>

<Note>
**Device, geo, click-limit, and password fields.** These are stored on a link's record but the public redirect does not currently route or block based on them - visitors get the main destination URL with UTMs appended. Use the destination page to handle device or country routing if you need it today.
</Note>
