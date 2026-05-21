---
title: "Pre-launch link audit"
description: "A repeatable checklist for auditing campaign links before you hit send or go live, so bad UTMs don't make it into your analytics."
---

## When to use this playbook

You're about to launch a campaign: email send, paid media flight, event promotion, or product announcement. You have a set of links ready. This playbook is the 15-minute check you run before anything goes live to catch UTM errors, broken destinations, and attribution gaps before they become a data problem.

Run this for every campaign. The cost of finding a bad UTM before launch is 2 minutes. After launch it's a GA4 cleanup project.

---

## What you're checking

1. Every link has the correct UTMs (no missing fields, no off-convention values)
2. Destination URLs resolve and land on the right page
3. Short links are active and not expired
4. QR codes (if used) scan correctly
5. GA4 is reading the UTMs as expected on the destination page

---

## The audit checklist

### UTM completeness

For every link in the campaign:

- [ ] Links were built from workspace [UTM templates](/utm-templates/overview) where available - reduces manual entry and prevents drift
- [ ] `utm_source` is set and on the approved list (check [UTM naming convention](/playbooks/utm-naming-convention))
- [ ] `utm_medium` is set and maps to a valid GA4 channel group
- [ ] `utm_campaign` is set and matches the campaign name used across all channels
- [ ] `utm_content` is set if you're running more than one creative or placement variant
- [ ] `utm_term` is set for paid search links; empty for everything else
- [ ] No spaces, caps, or special characters in any value (linkutm Rules catch this on save, but verify)
- [ ] No PII in any UTM field

<Tip>
In linkutm, open the link detail page. The UTM values are displayed in the Parameters panel. Check each one before copying the link.
</Tip>

### Campaign name consistency

- [ ] All links for this campaign share exactly the same `utm_campaign` value
- [ ] The campaign name matches what's in your campaign tracker or project management tool
- [ ] Google Ads, Meta, LinkedIn, email, and any other channels all use the same campaign slug

If a Google Ads link says `q2-pricing-launch` and the newsletter link says `q2-pricing`, you'll have a split campaign in GA4 and no single view of campaign performance.

### Destination URL check

For every link:

- [ ] Click the link manually in an incognito window and confirm it lands on the right page
- [ ] The destination page loads without errors (no 404, no redirect loop)
- [ ] The UTM parameters are visible in the browser address bar on the destination page
- [ ] If the destination page has a cookie consent banner, click through it and confirm GA4 still fires

<Warning>
If your destination URL uses a redirect (e.g. a landing page platform that rewrites the URL), confirm the UTM parameters survive the redirect. Some platforms strip query strings. Test in an incognito window and check the final URL in the browser bar.
</Warning>

### Short link and expiry check

- [ ] Short link is active in linkutm (status shown on link detail page)
- [ ] If you set an expiry date, confirm it is after the campaign end date
- [ ] If the link is password-protected, confirm the password is what you intend and is documented

### QR code check (if applicable)

- [ ] Scan the QR code with a phone (not the phone's camera preview, actually follow through to the page)
- [ ] Confirm it resolves to the right destination with UTMs intact
- [ ] If the QR code is going to print, test the printed version at print size (small QR codes at low DPI often fail to scan)

---

## GA4 verification

Run this for at least one link per channel before the campaign goes live.

<Steps>
  <Step title="Open GA4 DebugView">
    In GA4 Admin → DebugView. Keep it open in a separate tab.
  </Step>
  <Step title="Click the linkutm link in an incognito window">
    Use incognito so you don't contaminate the session with your regular browsing history.
  </Step>
  <Step title="Check session_start in DebugView">
    Look for the `session_start` event in DebugView. Expand it and confirm:
    - `traffic_source.source` = your `utm_source`
    - `traffic_source.medium` = your `utm_medium`
    - `traffic_source.campaign` = your `utm_campaign`
  </Step>
  <Step title="Confirm channel grouping">
    In GA4 Reports → Traffic Acquisition, the session should appear in the correct default channel within a few minutes. If it shows as "Unassigned," your `utm_medium` value doesn't match GA4's channel rules. Fix it before launch.
  </Step>
</Steps>

See [GA4 integration](/integrations/ga4) for the full troubleshooting guide if attribution isn't showing correctly.

---

## Common failures and fixes

<AccordionGroup>
  <Accordion title="UTM params missing from destination URL">
    The most common cause: the destination URL was pasted into a system that stripped query strings (some email platforms, CMS redirect rules, or landing page builders do this). Test the full redirect chain in an incognito window. If params are stripped, configure the destination system to pass through query strings, or switch the link destination to a URL that doesn't redirect.
  </Accordion>
  <Accordion title="Campaign shows as two rows in GA4 because of inconsistent campaign names">
    Find the inconsistency before launch by listing all campaign links and comparing `utm_campaign` values. Use linkutm's link list filtered by campaign name to catch variants. Fix the outlier link before the campaign sends.
  </Accordion>
  <Accordion title="Short link returns 404 after redirect">
    The destination URL in the link record is wrong or the destination page was taken down. Open the link in linkutm, check the destination URL, update it if needed. Short links can be edited at any time and the update takes effect immediately.
  </Accordion>
  <Accordion title="GA4 shows Direct instead of the campaign source">
    Three causes: UTMs stripped in redirect (see above), GA4 tag blocked by ad blocker or cookie consent not accepted, or the destination page does not have the GA4 tag installed. Verify tag is present in browser dev tools → Network → filter for `google-analytics` or `gtag`.
  </Accordion>
</AccordionGroup>

---

## Audit log

Keep a record that the audit was completed. A one-line entry in your campaign tracker is enough:

```
2026-05-19 | Q2 pricing relaunch | 12 links | Pre-launch audit: PASS | Auditor: [name]
```

If a UTM issue surfaces post-launch, the audit log tells you whether it was a setup error (audit passed, something changed) or a process error (audit was skipped).
