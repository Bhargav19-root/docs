---
title: "Link preview (Open Graph)"
description: "Override the social-share preview card title, description, image."
---

## What it is

When someone pastes your short link into Slack, LinkedIn, WhatsApp, etc., the platform fetches the URL's Open Graph tags to render a preview card. linkutm lets you override the OG title, description, and image per link without touching the destination page.

## When to use it

- Destination doesn't have OG tags (or has bad ones).
- You want a campaign-specific preview without changing the page.
- A/B testing share previews across channels.

## How to use it

<Steps>
  <Step title="Open Advanced → Social preview">
    In the link creation, expand **Advanced** and find the **Social preview** section.
  </Step>
  <Step title="Set OG fields">
    <ParamField path="ogTitle">Card headline. Keep ≤60 chars.</ParamField>
    <ParamField path="ogDescription">Subline. Keep ≤155 chars.</ParamField>
    <ParamField path="ogImage">Public image URL. Recommended 1200×630px PNG/JPG.</ParamField>
  </Step>
</Steps>

<Frame>
  <img src="/images/OGpreview.png" alt="Link Preview modal - editable OG title and description fields with social card preview" />
</Frame>

## Real-world example

Same destination URL, different previews per channel:

```
Short:        go.acme.com/launch-li     (LinkedIn)
ogTitle:      Acme Widget - built for engineering teams
ogImage:      https://cdn.acme.com/og/launch-linkedin.png

Short:        go.acme.com/launch-x      (X/Twitter)
ogTitle:      Acme Widget. Now in beta.
ogImage:      https://cdn.acme.com/og/launch-twitter.png
```

Same destination `https://acme.com/launch`. Per-link OG drives different share cards.

## Common mistakes

<AccordionGroup>
  <Accordion title="Setting OG on the destination instead">
    If destination already has correct OG tags, you don't need this. Override only when you want different cards per link.
  </Accordion>
  <Accordion title="Forgetting cache">
    LinkedIn and Meta cache OG data. Use their debug tools to flush after changes.
  </Accordion>
  <Accordion title="OG image too large or non-public">
    Files over ~5 MB or URLs behind auth won't render. 1200×630 PNG/JPG, public.
  </Accordion>
  <Accordion title="HTTP image on HTTPS short link">
    Mixed content gets blocked by some platforms. Always HTTPS for the OG image.
  </Accordion>
</AccordionGroup>

## Edge cases

<Note>
**Imported links** auto-fetch OG data from the destination during import (5s timeout). If fetch fails, favicon falls back to Google's favicon service for the destination domain.
</Note>
