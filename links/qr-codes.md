---
title: "QR codes"
description: "Generate a QR for any link to use on print, packaging, or events."
---

## What it is

Any short link in linkutm can be rendered as a QR code. The QR encodes the short URL - scanning it triggers the same redirect (and the same UTM tracking) as a click.

## When to use it

- Print: flyers, business cards, packaging.
- Events: trade-show booths, conference signage.
- TV / video overlays.
- Restaurants, retail - anywhere the audience holds a phone but can't type.

## How to use it

<Steps>
  <Step title="Find your link">
    Sidebar → **Links** → click into a link.
  </Step>
  <Step title="Generate QR">
    Click **QR Code** in the link details. The system renders a downloadable PNG/SVG/JPEG of the QR encoding the short URL.
  </Step>
  <Step title="Download and use">
    Download the high-res QR.
  </Step>
</Steps>

<Frame>
  <img src="/images/addlinkqrcode.png" alt="QR code generator - size slider, color pickers, format selector, and Download PNG button" />
</Frame>

## Real-world example

Coffee shop loyalty stamp card:

```
Destination:  https://acme-cafe.com/loyalty
utm_source:   in_store
utm_medium:   qr_code
utm_campaign: loyalty_v2
Custom slug:  cafe-loyalty
```

Print QR for `go.acme-cafe.com/cafe-loyalty` on every receipt. Analytics shows scans by region (which store), device (iOS vs Android), time of day.

## Common mistakes

<AccordionGroup>
  <Accordion title="QR encoding the destination directly">
    Bypasses linkutm - no click tracking, no UTM consistency. Always encode the **short URL**, not the long destination.
  </Accordion>
  <Accordion title="Editing the link after print">
    Changing the slug breaks every printed QR. Lock the slug before you commit to print.
  </Accordion>
</AccordionGroup>

## Edge cases

<Note>
**Pixel-firing links** insert a brief HTML interstitial before redirect. QR scans that happen inside an in-app browser may render the interstitial visibly. Not a problem for tracking accuracy.
</Note>
