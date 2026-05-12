---
title: "Analytics"
description: "What's tracked, what's surfaced, and how retention works."
---

## What it is

Every click on a linkutm short URL is logged with rich context. The Analytics page surfaces aggregations at workspace and per-link level.

## What's tracked per click

| Field                         | Source           | Notes                                   |
| ----------------------------- | ---------------- | --------------------------------------- |
| `timestamp`                   | server clock     | UTC                                     |
| `ip`                          | request headers  | `x-forwarded-for` or socket             |
| `country`, `region`, `city`   | geoip-lite       | falls back to ipinfo.io for private IPs |
| `device`                      | UA parse         | `mobile`, `tablet`, `desktop`           |
| `browser`, `os`               | UA parse         | best-effort string                      |
| `referrer` + `referrerDomain` | `Referer` header | fallback: messaging-app UA detection    |
| `userAgent`                   | request header   | full string                             |

## When to use it

- Daily — see clicks over time at a glance.
- Per-link — debug "is this link working" or compare creative variants.
- Workspace-level — channel mix, top performing links, top countries, top sources.

Pair with a real product analytics tool (GA4, Mixpanel, Amplitude) for funnel/conversion metrics. linkutm shows clicks → other tools show what happened next.

## What the Analytics page shows

<Tabs>
  <Tab title="Workspace view">
    - **Total clicks** in the date window.
    - **Unique visitors** (distinct IPs).
    - **Conversion rate** = unique / total clicks (rough proxy).
    - **Top links** by click count.
    - **Clicks over time** — daily series, fills 0 for empty days.
    - **Top countries** — bar / map visualization.
    - **Top sources** — by `utm_source` of the originating link.
  </Tab>
  <Tab title="Per-link view">
    - **Total clicks** + **unique visitors**.
    - **Clicks over time** — daily series.
    - **Top countries / regions / cities**.
    - **Top referrers** (with messaging-app detection).
    - **Device / browser / OS breakdown**.
  </Tab>
</Tabs>

## Real-world example

After a Q2 launch:

```
Workspace analytics, last 30 days:
- 18,420 clicks across 24 links
- 11,238 unique visitors (61% conversion proxy)
- Top source: google (cpc) — 8.3k clicks
- Top country: US — 12.1k
- Top device: mobile — 11.2k

Per-link: q2-launch-google
- 8,302 clicks
- 73% mobile, 24% desktop, 3% tablet
- Top referrer: Direct (typed/QR/in-app browser)
- Top country breakdown: US 71%, UK 9%, CA 6%
```

This tells the marketer: Google ads driving most volume, mostly mobile, mostly US — optimize landing page for mobile US, expand UK budget.

## Common mistakes

<AccordionGroup>
  <Accordion title="Treating clicks as conversions">
    A click is not a sale, signup, or page view. Pair with GA/Mixpanel/Amplitude (using the appended UTMs) for downstream events.
  </Accordion>
  <Accordion title="Counting bot traffic as humans">
    Some referrers are crawlers (Slack, Twitter, etc. when fetching OG previews). The system identifies common ones via UA pattern (Slack, WhatsApp, LinkedIn-bot, etc.) and labels them in the referrer column.
  </Accordion>
  <Accordion title="Querying beyond the retention window">
    Each workspace has a retention window for click data. Queries that ask for older data are silently clipped to the start of the window. Old clicks aren't deleted — they're just outside the queryable range.
  </Accordion>
</AccordionGroup>

## Edge cases

<Note>
**Retention window.** The Analytics API silently clips `startDate` to `now - retentionDays` if you ask for older data. Historical clicks remain in the database but aren't returned past the window.
</Note>

<Note>
**Reset analytics per link.** A link's click history can be wiped (resets click counter to 0 and deletes its `link_clicks` rows). Use sparingly — the data is gone.
</Note>
