---
title: "Folders"
description: "Organize links into separate folders; set a default folder for new links."
---

<Tip>
**Folders vs tags:** Use folders for primary grouping (one per link) — by campaign, client, or channel. Use tags for cross-cutting labels a link can belong to many of — status, quarter, experiment flag. Think of a folder as the filing cabinet drawer and tags as sticky notes on the file.
</Tip>

## What it is

Folders are flat containers for organizing links inside a workspace. Each folder is separate; folders don't support nesting. Each link belongs to zero or one folder. Unfiled links live in **Unsorted**.

<Frame>
  <img src="/images/fodler&tags.png" alt="Folders and Tags page - folder list with color indicators and tags panel" />
</Frame>

## When to use it

- 30+ links per workspace.
- Per-campaign or per-client grouping.
- Anytime your link list takes more than a glance to scan.

If you only need light grouping, [tags](/links/tags) are cheaper - links can have many tags but only one folder.

## How to use it

<Steps>
  <Step title="Create a folder">
    Sidebar -> **Folders** -> **Folders & Tags**. Name it (case-insensitive unique per workspace), pick a color.
  </Step>
  <Step title="Set a default">
    Mark one folder as **Default**. The link builder UI uses this as the pre-selected folder when you create a new link. Only one default at a time per workspace.
  </Step>
  <Step title="Move links in">
    From the link list: select links -> **Move to folder**.
  </Step>
</Steps>

<Frame>
  <img src="/images/foldercreation.png" alt="Create Folder modal - name field and 8-color picker" />
</Frame>

## Real-world example

Agency managing two clients:

```
Acme Corp
Acme Corp - Paid Search
Acme Corp - Paid Social
Acme Corp - Email
Acme Corp - Organic
Globex Co
Globex Co - Q2 Launch
Globex Co - Brand Awareness
```

## Common mistakes

<AccordionGroup>
  <Accordion title="One mega folder">
    Putting 800 links in "All Campaigns" defeats the point. Split links into separate folders by campaign, client, or quarter.
  </Accordion>
  <Accordion title="Same name twice">
    Folder names are case-insensitive unique per workspace. `Email` and `email` collide.
  </Accordion>
  <Accordion title="Expecting subfolders">
    Folders don't contain other folders. Use clear folder names, such as `Q2 Launch - Email`, or use tags for cross-cutting labels.
  </Accordion>
</AccordionGroup>
