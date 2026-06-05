---
title: "Quickstart"
description: "Sign up, create a workspace, ship your first tracked link in under 3 minutes."
---

<Note>
**Stack at a glance.** linkutm = workspace + links + UTMs + analytics. Everything is scoped to a workspace. Run multiple workspaces (e.g., one per client) and switch between them from the workspace picker.
</Note>

## 1. Create an account

<Steps>
  <Step title="Sign up">
    Go to [app.linkutm.com](https://app.linkutm.com) and sign in with email/password or Google. Verify your email if prompted.
  </Step>
  <Step title="Name your workspace">
    During onboarding you pick a workspace name (your company or client) and a slug. The slug becomes part of your URL: `app.linkutm.com/{slug}/links`.

    <Tip>Slug must be lowercase letters, numbers, hyphens. It's checked for availability live.</Tip>

  </Step>
  <Step title="Done">
    You land in the workspace with a default short domain attached. Add a [custom domain](/link-shortening/custom-domains) later for branded links.
  </Step>
</Steps>

<Tip>
**Setting this up for a team or agency?** Agree on your [UTM naming convention](/playbooks/utm-naming-convention) and configure UTM Rules _before_ inviting anyone. Rules apply to all new links going forward — it's much harder to enforce consistency after 50 links already exist.
</Tip>

## 2. Create your first link

<Steps>
  <Step title="Open the link builder">
    From the sidebar: **Links → Create Link** (or press the **+** button).
  </Step>
  <Step title="Paste destination URL">
    Full URL with `https://`. Example: `https://example.com/pricing`.
  </Step>
  <Step title="Fill UTMs">
    The five standard fields:

    | Field | Example | Required |
    |---|---|---|
    | `utm_source` | `google` | typically yes |
    | `utm_medium` | `cpc` | typically yes |
    | `utm_campaign` | `q2-launch` | typically yes |
    | `utm_term` | `running-shoes` | optional |
    | `utm_content` | `headline-a` | optional |

    <Tip>Apply a [template](/utm-templates/overview) instead of typing - saves time and prevents typos.</Tip>

  </Step>
  <Step title="(Optional) custom slug">
    Leave blank for auto-generated short code (7 lowercase chars). Type your own for branded slugs like `q2-launch`.
  </Step>
  <Step title="Create">
    Click **Create**. The link is live immediately.
  </Step>
</Steps>

<Frame>
  <img src="/images/addlinkpanel.png" alt="Create Link modal - Destination URL, Short Link, Title, Tags, Folder, UTM parameters tab, QR preview, and OG card preview" />
</Frame>

## 3. Test the redirect

Open the short link in a private window. You'll be redirected to your destination URL with all UTMs appended:

```
https://yourshort.link/q2-launch
↓
https://example.com/pricing?utm_source=google&utm_medium=cpc&utm_campaign=q2-launch
```

<Frame>
  <img src="/images/linkdashboardlineview.png" alt="Links dashboard - list view showing Link title, short URL, destination, tags, click count, and created date" />
</Frame>

The click is recorded. Open the link's analytics tab - country, device, browser, referrer all populate within seconds.

## 4. Next steps

<CardGroup cols={2}>
  <Card title="Set UTM standards" icon="gavel" href="/playbooks/utm-naming-convention">
    Approved source, medium, and campaign values - the convention your team follows.
  </Card>
  <Card title="Save a template" icon="copy" href="/utm-templates/create-template">
    Lock in source/medium for a channel so the team can't drift.
  </Card>
  <Card title="Add a custom domain" icon="globe" href="/link-shortening/custom-domains">
    `go.yourbrand.com/q2-launch` instead of the default.
  </Card>
  <Card title="Invite teammates" icon="user-plus" href="/team-collaboration/overview">
    Roles, permissions, notification preferences.
  </Card>
</CardGroup>

## How linkutm thinks about your data

<AccordionGroup>
  <Accordion title="Workspaces are the unit of isolation">
    Links, folders, tags, templates, UTM rules, custom domains, pixels, API keys, analytics - all scoped per workspace. A user in one workspace cannot access the links, analytics, or settings of any other workspace. Useful for agency-style multi-client setups.
  </Accordion>
  <Accordion title="Short codes are globally unique">
    Even though links are workspace-scoped, the short code (the part after `yourshort.link/`) is unique across the system. If you try to use a slug another workspace already grabbed, creation fails with a conflict error.
  </Accordion>
  <Accordion title="UTMs run through workspace rules">
    Before a link saves, your workspace's UTM Rules are applied: lowercase, space replacement, max length, prohibited terms. The cleaned values are what gets stored. See [UTM Rules](/utm-rules/overview).
  </Accordion>
  <Accordion title="Analytics has a retention window">
    Each workspace has a retention window for click data. Queries beyond that window are clipped to it.
  </Accordion>
</AccordionGroup>
