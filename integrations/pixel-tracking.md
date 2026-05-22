---
title: "Pixel Tracking"
description: "Connect ad pixels (Facebook, GA4, TikTok, LinkedIn, and more) to fire automatically on every link click."
---

## What it is

Pixel tracking lets you attach one or more ad-network pixels to your workspace. When a visitor clicks any linkutm short URL, the system fires those pixels **before** redirecting - so you get a PageView event in your ad platform without touching the destination page.

## Supported platforms

| Platform | ID format | Example |
|---|---|---|
| Google Analytics 4 | Measurement ID | `G-XXXXXXXXXX` |
| Facebook Pixel | Numeric pixel ID | `1234567890123456` |
| Google Tag Manager | Container ID | `GTM-XXXXXXX` |
| Twitter / X | Tag ID | `o0abc` |
| LinkedIn Insight Tag | Partner ID | `123456` |
| TikTok Pixel | Pixel ID | `XXXXXXXXXXXXXXXXXX` |
| Pinterest Tag | Tag ID | `1234567890123` |
| Snapchat Pixel | UUID | `abc123-def456-ghi789` |

## How to set up a pixel

<Steps>
  <Step title="Open Integrations">
    **Settings → Integrations** (workspace settings, not account settings).
  </Step>
  <Step title="Add Pixel">
    Click **Add Pixel** in the top-right corner.
  </Step>
  <Step title="Fill in the form">
    - **Name** - internal label (e.g. `Facebook Pixel - Main`, `GA4 - linkutm`). Not shown to visitors.
    - **Platform** - select from the supported list.
    - **Pixel ID** - the ID from your ad platform. Use **How to find your ID** link for platform-specific instructions.
  </Step>
  <Step title="Save">
    The pixel appears in **Connected Pixels**, enabled by default.
  </Step>
</Steps>

<Frame>
  <img src="/images/addpixelintegration.png" alt="Settings > Integrations - Add Tracking Pixel modal with Name, Platform (Facebook Pixel), and Pixel ID fields; available integrations in background" />
</Frame>

<Frame>
  <img src="/images/pixeladdedsettings.png" alt="Settings > Integrations - Connected Pixels section showing Facebook Pixel enabled, with integration grid and Connected badge" />
</Frame>

## How pixels fire

Every enabled workspace pixel fires by default on every link click. You can override this per-link (see below).

The system injects a hidden redirect page that:
1. Fires all applicable pixel scripts (PageView event for each platform).
2. Immediately redirects the visitor to the destination URL.

Round-trip delay is negligible (sub-100 ms in most regions).

## Per-link pixel control

When creating or editing a link, open the **Pixels** panel in the link builder.

- **No selection** (default) - all enabled workspace pixels fire.
- **Select specific pixels** - only the checked pixels fire for that link.
- **Deselect all** - clears the override; falls back to workspace default (all fire).

Use this when running multi-channel campaigns and you want only the relevant platform pixel to fire on each link variant (e.g. only the Facebook pixel fires on links distributed via Facebook ads).

<Frame>
  <img src="/images/addpixelinlink.png" alt="Tracking Pixels panel in the link builder - Facebook Pixel - Main checkbox selected, Apply Pixels button" />
</Frame>

## Enabling / disabling pixels

Toggle the switch next to any pixel in **Settings → Integrations** to disable it workspace-wide without deleting it. Disabled pixels never fire, regardless of per-link selection.

## Real-world example

You run paid campaigns across Facebook, Google, and TikTok.

```
Workspace pixels configured:
  - Facebook Pixel - Main   (enabled)
  - GA4 - linkutm           (enabled)
  - TikTok Pixel - Q2       (enabled)

Link: go.acme.com/fb-q2
  Pixels selected: Facebook Pixel - Main only
  → Only Facebook pixel fires on click

Link: go.acme.com/tiktok-q2
  Pixels selected: TikTok Pixel - Q2 only
  → Only TikTok pixel fires on click

Link: go.acme.com/email-q2
  Pixels selected: (none - workspace default)
  → All three pixels fire on click
```

Your ad platforms each get accurate PageView events without any changes to the destination landing page.

## Common mistakes

<AccordionGroup>
  <Accordion title="Pixel fires but conversion isn't attributed">
    linkutm fires a **PageView** event. Conversion events (Purchase, Lead, etc.) must be fired separately on your destination page. linkutm handles top-of-funnel click attribution; your site handles the downstream conversion events.
  </Accordion>
  <Accordion title="Wrong Pixel ID format">
    Each platform has a distinct ID shape. Facebook IDs are all-numeric (15-16 digits). GA4 IDs start with `G-`. GTM IDs start with `GTM-`. Paste from the platform's dashboard - don't type from memory.
  </Accordion>
  <Accordion title="Pixel shows as active but no data in ad platform">
    Ad blockers and iOS 14.5+ ATT restrictions suppress pixel fires in-browser. This is expected and not a linkutm bug. Use server-side Conversions API on your destination site to recover blocked signals.
  </Accordion>
  <Accordion title="Added pixel but it's not firing on existing links">
    Existing links with an explicit pixel selection (even an empty one) are not automatically updated when you add a new workspace pixel. Edit those links and clear the per-link pixel selection to restore workspace default behavior.
  </Accordion>
</AccordionGroup>

## Edge cases

<Note>
**Plan limits.** Advanced pixel integrations (GA4 specifically) may be gated to paid plans. The integrations page shows which platforms require an upgrade.
</Note>

<Note>
**Multiple pixels from the same platform.** You can connect more than one pixel from the same platform (e.g. two Facebook pixels for two ad accounts). Each is tracked independently and both fire unless you override per-link.
</Note>

<Note>
**Deleting a pixel.** Deleting a pixel removes it from all links permanently. The per-link selection for that pixel is cleared. Historical link clicks are not retroactively affected - they already fired when they occurred.
</Note>
