---
title: "Agency client onboarding"
description: "How to set up a new client workspace in linkutm, configure their UTM convention, invite the client, and hand off a working link system in under an hour."
---

## When to use this playbook

You're an agency operator adding client number two, five, or fifteen. You need their UTM links isolated from other clients, their naming convention locked down before anyone starts building campaigns, and a clean handoff so the client can self-serve without breaking your attribution setup.

This playbook covers one client onboarding end to end.

---

## What you'll have when done

- A dedicated workspace for the client (isolated links, analytics, team members)
- A custom short domain on the client's brand (optional but recommended)
- A UTM naming convention locked in via Rules before the first link is created
- The client invited with the right permission level
- A template set for their top 5 channels, ready to use

---

## Step 1: Create the client workspace

<Steps>
  <Step title="Create a new workspace">
    Go to **Workspaces** in the sidebar → **New Workspace**. Name it after the client: `Acme Corp` not `Client 3`.

    One workspace per client. Never share a workspace across clients - links, analytics, domains, and rules are all workspace-scoped.
  </Step>
  <Step title="Set workspace defaults">
    Inside the new workspace, go to **Settings → General**:
    - Set the workspace name exactly as it will appear in reports
    - Set the default link expiry if the client uses campaign-specific links that should expire
  </Step>
</Steps>

<Note>
Each workspace has its own UTM Rules, templates, custom domains, and team members. Switching workspaces in the sidebar is how you move between clients.
</Note>

---

## Step 2: Configure the client's custom domain (recommended)

Branded short links (`go.acmecorp.com/campaign-link`) look more professional than a shared domain and keep click data attributed to the client's brand.

<Steps>
  <Step title="Get the domain from the client">
    Ask the client to provide or create a subdomain they control: `go.clientdomain.com`, `links.clientdomain.com`, or `l.clientdomain.com` are common patterns. They need DNS access to add a CNAME record.
  </Step>
  <Step title="Add the domain in linkutm">
    Go to **Settings → Domains → Add Domain**. Enter the subdomain. linkutm will provide a CNAME target to give the client.
  </Step>
  <Step title="Client adds the CNAME record">
    The client logs into their DNS provider (Cloudflare, GoDaddy, Route 53, etc.) and adds:
    - Type: `CNAME`
    - Name: `go` (or whatever subdomain prefix they chose)
    - Value: the CNAME target linkutm provided

    DNS propagation takes 5 minutes to 48 hours depending on TTL.
  </Step>
  <Step title="Verify and set as default">
    Once propagated, the domain shows as **Active** in Settings → Domains. Set it as the default short domain for this workspace so all new links use it automatically.
  </Step>
</Steps>

---

## Step 3: Define and enforce the client's UTM convention

This is the most important step. Do it before the client or any team member creates a single link.

<Steps>
  <Step title="Agree on the naming convention">
    Walk through the [UTM naming convention](/playbooks/utm-naming-convention) with the client. Agree on:
    - Their approved `utm_source` values (which channels do they actually run?)
    - Their `utm_medium` values (match GA4 channel grouping rules)
    - Their `utm_campaign` pattern (`{quarter}-{theme}` is a sensible default)
    - Whether they need `utm_content` tracking (almost always yes for paid)
  </Step>
  <Step title="Configure UTM Rules for this workspace">
    Go to **Settings → UTM Rules** and set:

    ```
    forceLowercase: true
    spaceCharacter: "-"
    
    Required field rules:
    - utm_source: allowed_values = [their approved list]
    - utm_medium: allowed_values = [cpc, paid-social, email, display, video, affiliate, organic-social, qr, referral]
    - utm_campaign: not_empty
    
    Prohibited values: ["test", "draft", "tbd", "todo"]
    ```

    Anyone creating a link in this workspace with an off-list source or empty campaign gets rejected on save, not after the campaign has already run.
  </Step>
  <Step title="Create templates for their top 5 channels">
    Go to **UTM Templates → Create Template** for each channel the client actively uses. At minimum:
    - Google Ads template
    - Meta Ads template
    - Newsletter/email template
    - LinkedIn template (if relevant)
    - Any affiliate or partner channel they use

    Leave `utm_content` blank in every template. That gets filled per link.

    See [Create a template](/utm-templates/create-template) for the full walkthrough.
  </Step>
</Steps>

---

## Step 4: Invite the client

<Steps>
  <Step title="Decide the permission level">
    | Role | What they can do | Use for |
    |---|---|---|
    | **Admin** | Full workspace access including billing, domain settings, UTM Rules | Client's marketing lead or MOPs owner |
    | **Member** | Create/edit links, use templates, view analytics | Day-to-day campaign managers |
    | **Viewer** | View links and analytics only | Client stakeholders who need reporting access |

    Recommend giving the client's MOPs lead Admin access on their own workspace. Don't give Admin to every campaign manager.
  </Step>
  <Step title="Send the invite">
    Go to **Settings → Team → Invite Member**. Enter their email and select the role. They'll receive an email to join the workspace.
  </Step>
  <Step title="Brief them on the convention">
    Share this doc with them: [UTM naming convention](/playbooks/utm-naming-convention). Tell them the Rules are already configured to enforce it. If they try to use an off-list source value, the save will fail with an error message explaining why.
  </Step>
</Steps>

---

## Step 5: Create the first campaign links together

Don't leave the client to figure it out alone. Walk them through creating one real campaign link during onboarding.

<Steps>
  <Step title="Pick a live campaign">
    Use a real campaign they're about to launch, not a test link. This ensures the convention is battle-tested before it matters.
  </Step>
  <Step title="Use the UTM builder with a template">
    Open **Links → Create Link → UTM Builder**. Select the appropriate channel template. Show them how the source and medium pre-fill and how to add the campaign name and content variant.
  </Step>
  <Step title="Show them the QR code and short link">
    If they run any offline or event marketing, show how to download the QR code from the link detail page. If they need the short link for a bio or print material, show how to copy it.
  </Step>
  <Step title="Confirm GA4 attribution">
    If they have GA4, have them click the link in a browser and check GA4 DebugView to confirm the UTM params are arriving correctly. See [GA4 integration](/integrations/ga4) for the verification steps.
  </Step>
</Steps>

---

## Handoff checklist

Before you consider onboarding complete:

- Workspace created and named correctly
- Custom domain active (or documented as deferred with a reason)
- UTM Rules configured and tested: try creating a link with a bad source value and confirm it rejects
- Templates created for all active channels
- Client team invited with correct roles
- Client's MOPs lead can log in and create a link independently
- GA4 attribution verified on at least one live link
- UTM naming convention page shared with the client team

---

## Common mistakes

<AccordionGroup>
  <Accordion title="Sharing one workspace across multiple clients">
    All links, analytics, rules, and team members are shared inside a workspace. One workspace per client is the only safe structure for agencies. Cross-client data leakage is a support relationship risk.
  </Accordion>
  <Accordion title="Setting up UTM Rules after links have been created">
    Rules validate new links on save. Existing links in the workspace are not retroactively validated or updated. Set up Rules before the first link. If the client already has links with inconsistent UTMs, treat those as legacy and start clean from the convention date.
  </Accordion>
  <Accordion title="Giving every client team member Admin access">
    Admins can change UTM Rules, delete templates, and modify the custom domain. Campaign managers don't need this. Give them Member access. Reserve Admin for the client's MOPs lead and your own agency account.
  </Accordion>
  <Accordion title="Skipping the custom domain step">
    Links on a shared domain look unprofessional in client reports and create ambiguity when the client eventually wants to migrate. Set up the custom domain at onboarding, even if it takes an extra day for DNS propagation.
  </Accordion>
</AccordionGroup>
