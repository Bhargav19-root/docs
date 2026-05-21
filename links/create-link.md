---
title: "Create a link"
description: "The full link creation flow: destination, UTMs, organization, advanced options."
---

## What it is

A link in linkutm = destination URL + UTM parameters + a short code. Visitors hit the short URL; the system records the click and redirects them to the destination with UTMs appended.

<Frame>
  <img src="/images/linkdashboardlineview.png" alt="Links dashboard - list view showing link title, short URL, destination, tags, click count, and created date" />
</Frame>

<Frame>
  <img src="/images/linkdashboardfolderview.png" alt="Links dashboard - card/grid view showing the same links as cards with click counts" />
</Frame>

## When to use it

- Every campaign URL goes through here. There's no "untracked" mode.
- Use [bulk import](#bulk-and-import) instead if you have 50+ links to migrate.
- Use a [template](/utm-templates/overview) if you create the same shape of link weekly.

## How to create one

<Steps>
  <Step title="Open the builder">
    Sidebar → **Links** → **Create Link**.
  </Step>
  <Step title="Destination URL">
    The page you're driving traffic to. Must include `https://` (or `http://`). Query strings already on the URL are preserved - UTMs append after.
  </Step>
  <Step title="Domain">
    Pick which short domain to use. Defaults to the workspace's default domain. Only **verified, enabled** custom domains are selectable.
  </Step>
  <Step title="Custom slug (optional)">
    The path after your domain. Leave blank for an auto-generated 7-char code (`abcd123`). Type your own for branded slugs (`q2-launch`).

    <Warning>Short codes are unique across the entire system. If your slug is taken, you'll see *"Short code already exists"* - pick another.</Warning>

  </Step>
  <Step title="Organize (optional)">
    Drop into a [folder](/links/folders) and add [tags](/links/tags). Both are workspace-scoped and useful for filtering large link lists.
  </Step>
  <Step title="Description (optional)">
    Only for internal reference, never shown to visitors.
  </Step>
  <Step title="UTM parameters">
    Fill from the autocomplete (powered by your [parameter library](/utm-parameters/overview)) or type freely. Workspace [UTM rules](/utm-rules/overview) clean values on save (lowercase, space → underscore, etc).
  </Step>
  <Step title="Advanced (optional)">
    Open the advanced section for password, expiration, click limits and OG preview overrides.
  </Step>
  <Step title="Create">
    Hit **Create**. Link is live, Short URL is active, click count starts at zero.
  </Step>
</Steps>

<Frame>
  <img src="/images/addlinkpanel.png" alt="Create Link modal - Destination URL, Short Link, Title, Tags, Folder, Comments, QR preview, OG card preview, and UTM/Advanced/Pixels tabs" />
</Frame>

## Real-world example

Running a Google Ads campaign for a Q2 product launch, brand keywords variant:

```
Destination:  https://acme.com/products/widget
Title:        Q2 Launch - Google Search - Brand
utm_source:   google
utm_medium:   cpc
utm_campaign: q2_launch
utm_term:     acme_widget
utm_content:  headline_a
Custom slug:  q2-acme
Folder:       Q2 Launch
Tags:         google-ads, paid-search
```

Final short URL: `go.acme.com/q2-acme` → redirects to the full UTM-tagged destination.

## Common mistakes

<AccordionGroup>
  <Accordion title="Spaces or capitals in UTM values">
    `Summer Sale` becomes `summer_sale` automatically (force-lowercase + space-replacement are on by default). But if you turned those rules off, you'll get split campaign rows in GA. Leave the rules on unless you have a reason.
  </Accordion>
  <Accordion title="Forgetting `https://`">
    Required. The builder won't accept a bare `example.com`.
  </Accordion>
  <Accordion title="Using a slug another workspace owns">
    Slugs are global, not workspace-local. Creative slugs avoid collisions: `acme-q2` beats `launch`.
  </Accordion>
</AccordionGroup>

## Edge cases

<Note>
**Workspace usage limits.** Workspaces have a maximum number of total links. When you hit the limit, link creation fails with a clear message and the workspace owner is notified by email when the link creation quota is near maximum.
</Note>

<Note>
**Unverified domain.** You cannot create a link on a custom domain that hasn't passed CNAME verification. Use the system default until [verification](/link-shortening/custom-domains) succeeds.
</Note>

## Filtering and bulk actions

Use the links dashboard to filter, sort, and act on multiple links at once.

<Frame>
  <img src="/images/linkdashboardfilters.png" alt="Filters panel - Source dropdown (Google, Facebook, Twitter, LinkedIn) and Medium dropdown for narrowing the links list" />
</Frame>

<Frame>
  <img src="/images/linkdashboarddisplaysettings.png" alt="Display settings panel - Ordering options, Show archived toggle, and Display Properties checkboxes" />
</Frame>

<Frame>
  <img src="/images/linkdashboardcalendar.png" alt="Date range picker - preset options list alongside a dual-month calendar for custom date ranges" />
</Frame>

Select links in the list to reveal bulk actions - Export, Archive, Tag, Move, Delete.

<Frame>
  <img src="/images/linkdashboardselectalllinks.png" alt="Links dashboard with all links selected - bulk action bar showing Export, Archive, Tag, Move, and Delete buttons" />
</Frame>

## Bulk and import

For 50+ links, use:

- **CSV import** - UI flow under Links → Import.
- **Bitly / Rebrandly / Short.io migration** - paste your API key, the system pulls links and recreates them. Original slugs are preserved when not taken; conflicts are skipped with a per-link error.

<Frame>
  <img src="/images/importoptions.png" alt="Import/Export dropdown - Import options (Bitly, Rebrandly, Short.io, CSV) and Export as CSV" />
</Frame>

**CSV import flow:**

<Frame>
  <img src="/images/importlinksfirststage.png" alt="CSV Import step 1 - drag-and-drop upload area with Download sample CSV button" />
</Frame>

<Frame>
  <img src="/images/csvimportfirststage.png" alt="CSV Import step 2 - column mapping view where CSV columns are mapped to Linkutm UTM fields, with Preview and check conflicts button" />
</Frame>

<Frame>
  <img src="/images/csvimportlaststage.png" alt="CSV Import step 3 - review screen showing 25 links, 0 conflicts, Ready status, and Import 25 ready links button" />
</Frame>

**Export:**

<Frame>
  <img src="/images/exportascsv.png" alt="Export as CSV modal - Date Range picker and column checkboxes (Title, Clicks, UTM fields, Created Date, Tags, Folder) with Export button" />
</Frame>
