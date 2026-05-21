---
title: "linkutm Docs ICP Audit - Thorough"
date: 2026-05-19
depth: thorough
reviewer: linkutm-docs-icp-reviewer
files_reviewed: 37
scope: "Every .md / .mdx under docs/ (excluding docs/analytics-test-runner/node_modules/**)"
---

# linkutm Docs ICP Audit - Thorough (2026-05-19)

> Reviewed every real page in `docs/` (37 files) through the lens of the four ICPs:
> Marketing-ops lead, In-house performance marketer, Agency operator, API developer.
> Scored against the 5-dimension rubric (IA, Voice, Completeness, Storytelling, Actionability).

---

## SCORES

| Persona              | IA  | Voice | Compl. | Story | Action | Weighted | Δ vs baseline |
|----------------------|-----|-------|--------|-------|--------|----------|---------------|
| Marketing-ops lead   | 7   | 8     | 5      | 5     | 6      | **6.15 / 10** | **–0.35** (was 6.5; thorough surfaced missing playbooks + glossary) |
| In-house marketer    | 8   | 8     | 6      | 7     | 6      | **6.95 / 10** | **–0.55** (was 7.5; zero screenshots/GIFs confirmed across all 9 link pages + preset library still absent) |
| Agency operator      | 7   | 7     | 5      | 5     | 6      | **5.95 / 10** | **–0.05** (was 6.0; on par - onboarding playbook + white-label/billing isolation gaps unchanged) |
| API developer        | 6   | 8     | 4      | 4     | 6      | **5.50 / 10** | **0.0** (was 5.5; thorough confirmed no analytics endpoints, no webhooks, no PATCH/update, auth flow muddled) |
|                      |     |       |        |       |        | **──────** | |
|                      |     |       |        |       | **Overall** | **6.18 / 10** | **–0.82** (baseline overall 7.0; weighting per-persona equally) |

Weights: IA 20% · Voice 15% · Completeness 25% · Storytelling 20% · Actionability 20%.

**Headline.** The doc set is well-written at the **page** level (voice is consistently a peer's, not an engineer's, examples use `acme.com` / `q2_launch` instead of `example.com`, edge cases are honestly disclosed). It fails at the **system** level: there is no narrative arc, no playbook layer, no integrations beyond pixels, no analytics/webhooks API, and zero screenshots/GIFs in a UI-driven product. Thorough mode revealed the gaps are deeper than medium-depth scan suggested - hence the negative delta.

---

## STORYTELLING ARCS

| Arc | Status | Where it breaks |
|---|---|---|
| 1. **Messy-data recovery** ("I inherited bad UTMs") | **Absent** | No audit page, no backfill plan, no `messy-data-recovery.md`. Rules + Templates exist as siblings; no narrative pairing them. |
| 2. **Q2 campaign launch** (plan → bulk-create → QR → custom domain → monitor → post-mortem) | **Broken at bulk-create + post-mortem** | CSV import mentioned once in `links/create-link.md#bulk-and-import` with no schema. No "campaign post-mortem" analytics walkthrough. |
| 3. **Agency onboarding** (new workspace → custom domain → invite client → set their UTM convention → first report) | **Broken at "first report"** | `organization/overview.md` has the model right but no end-to-end playbook. White-label / billing-isolation specifics absent. Per-client reporting workflow undocumented. |
| 4. **API integration** (auth → create → list → analytics → webhook → errors → rate limits) | **Broken at analytics + webhooks** | API tab covers only links CRUD. No analytics endpoints. `best-practices.mdx` explicitly says "Webhooks are not currently implemented" - fine to disclose, but no polling-pattern example. PATCH `/links/:id` is not documented anywhere despite being referenced in `common-issues.mdx`. |

---

## FINDINGS (28 logged: 4 blocker · 16 gap · 8 polish)

| # | path | persona | sev | issue → fix |
|---|---|---|---|---|
| 1 | `docs/README.md` | all | blocker | Reads like a directory listing aimed at doc contributors, not users. Auto-generated date stamp `2024` is stale, the `📝 Additional Documentation (Can Be Added)` block telegraphs unfinished work to anyone clicking the repo. → Strip the "what doesn't exist yet" list. Replace with a 6-line orientation: who docs are for, where to start, how to contribute via PR. Update last-updated stamp to 2026. |
| 2 | `docs/index.mdx` | marketing-ops lead | blocker | The four hero cards send marketing-ops to **Quickstart / UTM Builder / Templates / Custom Domain** - none of them is the page a MOPs lead actually wants on day 1. There is no "UTM naming convention" or "rules + templates" hero card despite the `<Note>` body literally saying those two prevent 80% of dirty data. → Promote a `playbooks/utm-naming-convention.md` card into the first row; demote Custom Domain into "Advanced". |
| 3 | `docs/index.mdx` | agency operator | gap | "Common tasks" row offers `Organize links / Read analytics / Invite team / API reference` - no agency-onboarding card, no per-client-workspace card. → Add a `playbooks/agency-onboarding.md` card in Common tasks for agencies. |
| 4 | `docs/quickstart.mdx` | all | polish | 11-line stub that just redirects. Either delete and 301 at the Mintlify level, or merge content from `getting-started/introduction.md` into it (the canonical title there is "Quickstart" too - confusing duplication). |
| 5 | `docs/getting-started/introduction.md` | in-house marketer | gap | Title says "Quickstart" but frontmatter description ("Sign up, create a workspace, ship your first tracked link in under 3 minutes") makes a 3-minute promise that is broken: zero screenshots, no Loom embed, no "what done looks like" visual. The "How linkutm thinks about your data" `<AccordionGroup>` is great content but buried under the fold and hides 4 critical concepts behind clicks. → Add 2 screenshots (link builder filled in + link analytics tab populated), and pull the 4 accordions into a `<Note>`-flagged concept callout that doesn't require expansion. |
| 6 | `docs/getting-started/introduction.md` | marketing-ops lead | gap | "Next steps" CardGroup goes Rules / Templates / Custom Domain / Team. For MOPs that's correct content but wrong order. → Lead with Templates **paired with** Rules as a single card ("Set your team's UTM standards"); custom domain becomes the third. |
| 7 | `docs/links/create-link.md` | in-house marketer | gap | The most-trafficked page in the doc set has no screenshots, no GIF of autocomplete, no visual of the Advanced section expanding. The `## Bulk and import` section is 3 lines for a multi-tool feature (CSV + Bitly + Rebrandly + Short.io migration). → Add 2 GIFs (autocomplete + Advanced expand) and split bulk-import into its own page with CSV schema, sample CSV, conflict-handling matrix. |
| 8 | `docs/links/create-link.md` | api developer | polish | "Real-world example" uses `Title:` notation which is API-field shape but never names the API field name. Marketers don't care; devs reading this for orientation get inconsistency vs `api/links-create.mdx` (which uses `title` lowercase camelCase). → Either drop the field-style notation or link to the API spec. |
| 9 | `docs/links/utm-builder.md` | marketing-ops lead | gap | Excellent voice and examples - but it lives at `/links/utm-builder` while a MOPs lead is searching for "naming convention". There is **no** opinionated naming-convention playbook anywhere in docs. → Add `playbooks/utm-naming-convention.md` and link from this page's top with: *"Need a convention before you build? Start here."* |
| 10 | `docs/links/utm-builder.md` | all | polish | "Conditional rules override silently" is flagged as an edge case `<Note>` but this is exactly the kind of footgun a MOPs lead needs as a `<Warning>`, not a `<Note>`. → Upgrade to `<Warning>`. |
| 11 | `docs/links/short-link.md` | api developer | polish | "Renaming an existing slug. Edit the link → change Short code." Edit-link API endpoint isn't documented in the API tab at all. → Add `PATCH /links/:id` to API Reference (see finding #24). |
| 12 | `docs/links/password-protected.md` | all | gap | The `<Warning>` honestly admits enforcement is UI-only. Good. But the page should not exist as a peer of "QR codes" and "Folders" if the feature doesn't actually gate. → Either move under an "Advanced / Roadmap" group with a clear "not yet enforced" label in the nav, or rename the page "Link password (label only)" so search results don't oversell. |
| 13 | `docs/links/link-expiration.md` | all | polish | Inconsistent: Step 3 says click-limit "is recorded for reporting" AND "Once the click limit is hit, the link stops redirecting" - both in the same paragraph. The page top says "Click limit - a maximum number of clicks recorded on the link" (just informational). Either the redirect enforces it or it doesn't. → Pick one statement, fix everywhere. (Cross-check with `api/links-create.mdx#clickLimit` which says NOT enforced - so the create-link page is the lying one.) |
| 14 | `docs/links/qr-codes.md` | in-house marketer | gap | Zero QR screenshot in a QR-codes page. Marketer reading this can't visually confirm output. → Add 1 image of the rendered QR + 1 of the download-options panel. |
| 15 | `docs/links/folders.md` and `docs/organization/managing-projects.md` | all | gap | Two pages explain the same flat-folders model with slightly different mental models ("folders for organization" vs "folder-as-project"). Risk: reader picks one and misses the other's nuance. → Merge or cross-link explicitly at the top of each page. |
| 16 | `docs/utm-templates/overview.md` + `docs/utm-rules/overview.md` | marketing-ops lead | blocker | These two pages are documented as siblings, but a MOPs lead reads them as a **system** (templates = encouragement, rules = enforcement). Neither page has a "Templates + Rules together" diagram or decision table. → Add a 4-line decision table on each page: *Templates if X, Rules if Y, Both if Z.* Better: a third page `utm-standards/templates-and-rules-together.md`. |
| 17 | `docs/utm-templates/overview.md` | in-house marketer | gap | "Real-world example" lists 4 templates (Newsletter, Google Brand, Meta Retargeting, LinkedIn Webinar) - but there is no **preset library** anywhere in linkutm or its docs. A marketer would expect "click to import these 10 starter templates". → Either ship presets and document them at `utm-templates/preset-library.md`, or add a copy-pasteable JSON block per template at the bottom of this page. (Ask: do presets exist in product?) |
| 18 | `docs/utm-rules/overview.md` | marketing-ops lead | gap | Excellent rules-engine reference, but pure feature-shaped. Where is the **opinionated** "here's a starter ruleset for a 5-person marketing team" block? → Add an "Opinionated starter ruleset" tab in the "Real-world examples" section with the regex, allowed values list, prohibited terms, conditional rules a MOPs lead can paste. |
| 19 | `docs/utm-parameters/overview.md` | all | polish | Strong page. One issue: the relationship between this library, templates, and rules is implied but never explicitly shown. → Add a 3-line section "How this fits with Templates and Rules": *Library = autocomplete vocabulary. Templates = preset values. Rules = enforcement.* |
| 20 | `docs/link-shortening/overview.md` | api developer | polish | "Server-side 302 redirect" - good for devs. But the redirect logic block ("Records the click", "Builds the destination URL", "Fires pixels") has zero hyperlinks to the analytics or pixel pages it implicitly references. → Link "Records the click" → analytics, "Fires pixels" → pixel-tracking. |
| 21 | `docs/link-shortening/custom-domains.md` | in-house marketer | gap | The CNAME table is right, but there's no screenshot of the linkutm "Add Domain → pending" UI nor of the Cloudflare gray-cloud setting. The most-likely failure mode (proxied) is buried in a `<Warning>` inside Step 3. → Add a screenshot showing the linkutm domain page in pending state AND a Cloudflare DNS row with gray cloud highlighted. |
| 22 | `docs/analytics/overview.md` | marketing-ops lead | blocker | The doc says "Pair with a real product analytics tool (GA4, Mixpanel, Amplitude)" - but there is **no GA4 integration page, no Mixpanel mapping doc, no Amplitude doc**. A MOPs lead's literal #1 question (how do my UTMs map to GA4 source/medium and custom dimensions?) is unanswered. → Add `integrations/ga4.md` at minimum; ideally also `integrations/mixpanel.md` and `integrations/amplitude.md`. |
| 23 | `docs/analytics/overview.md` | api developer | gap | The page describes Workspace/Per-link analytics views, but there are **no API endpoints documented** for retrieving any of this data. Yet `best-practices.mdx` says "Workspace-level analytics is one query for the workspace, not N queries per link. Use it for dashboards." → Document the analytics endpoints (or, if they don't exist publicly yet, kill the bullet in best-practices and add to "Asks for the human"). |
| 24 | `docs/api/*` (whole tab) | api developer | blocker | API Reference covers **only** links Create / Get / Delete / Parameters. Missing from the public surface: `PATCH /links/:id`, bulk endpoints have no individual pages (only mentioned in `links-delete.mdx`), domains CRUD, folders, tags, templates, parameters library, UTM rules, workspaces, members/invites, analytics, pixels. → At minimum, surface PATCH on links + bulk endpoints as their own pages, and document the workspaces and tags endpoints since the create-link example depends on them (`tagIds`, `x-workspace-id`). |
| 25 | `docs/api/introduction.mdx` | api developer | gap | Auth story is muddled: section heading says JWT bearer, the API-keys callout says `lk_live_<hex>` keys exist for "long-lived API key" usage, then a `<Warning>` says "the auth strategy is JWT-bearer end-to-end" implying keys aren't usable for HTTP auth. The dev integrating from a backend cannot tell which to use. → Pick one of: (a) document the JWT exchange endpoint with curl + token TTL + refresh flow, or (b) document the API-key Authorization header format if keys actually authenticate. |
| 26 | `docs/api/best-practices.mdx` | api developer | gap | "Rate limits" section says "There's no published global request-rate limit at the API edge today." Followed by per-workspace maximums (links, clicks, API calls). The API-call maximum is the closest thing to a rate limit but its window and reset behavior are not documented. → Document API-call quota: max calls per period, period length (rolling 30d? calendar month?), how to inspect remaining quota. |
| 27 | `docs/api/best-practices.mdx` + `docs/api/introduction.mdx` | api developer | polish | "No official SDK ships today. Generate one from Swagger at `/docs`." But `/docs` is documented as `http://localhost:8001/docs` - that's a dev URL. Where is the production Swagger? → State the production Swagger URL or remove the suggestion. |
| 28 | `docs/help/*` | agency operator | gap | Help center has 3 pages (contact, common issues, feature requests) but no page on data export, billing isolation, or transferring workspaces between accounts - questions an agency operator hits on every client offboarding. → Add `help/exporting-data.md` covering links CSV export, click history export, account/billing transfer. |

### Findings by persona (count)

| Persona | Blocker | Gap | Polish | Total |
|---|---|---|---|---|
| Marketing-ops lead | 2 | 5 | 1 | 8 |
| In-house marketer  | 0 | 5 | 1 | 6 |
| Agency operator    | 0 | 2 | 0 | 2 |
| API developer      | 1 | 4 | 3 | 8 |
| Cross / all        | 1 | 0 | 3 | 4 |
| **Total**          | **4** | **16** | **8** | **28** |

---

## QUICK WINS (top 10, ranked by impact × ease)

| # | Quick win | Impact | Ease | Why now |
|---|---|---|---|---|
| 1 | Write `playbooks/utm-naming-convention.md` (opinionated, 1 page, real campaign examples) and surface as the first hero card on `index.mdx`. | High | High | Closes the biggest MOPs gap. One page fixes blocker #2 and supports findings #9, #18. |
| 2 | Add `integrations/ga4.md` mapping UTM → GA4 source/medium/campaign + custom dimensions for `utm_content`/`utm_term`. | High | Medium | Closes blocker #22 - the literal #1 MOPs question. Template-shaped, copy-pasteable. |
| 3 | Add screenshots (2 GIFs minimum) to `links/create-link.md` and `links/utm-builder.md`. | High | Medium | Single biggest in-house marketer gap. Loom-embed acceptable as a stop-gap. |
| 4 | Document `PATCH /links/:id` and add a single "Bulk operations" sub-page under API Reference. | High | Medium | Closes the most-cited API gap (finding #24) without rewriting auth story. |
| 5 | Replace `docs/README.md` body with a 6-line orientation; strip the "additional documentation can be added" telegraph. | Medium | High | 10-minute fix. Stops broadcasting unfinished doc state to anyone in the repo. |
| 6 | Resolve `clickLimit` contradiction (`links/link-expiration.md` vs `api/links-create.mdx`). Pick one truth. | Medium | High | A contradiction this clear destroys trust on every other "behavior controls" sentence. |
| 7 | Pair Templates + Rules: add a decision-table block on both overview pages ("Templates if X, Rules if Y, Both if Z"). | Medium | High | One paragraph fix; closes blocker #16. |
| 8 | Add an "Opinionated starter ruleset" tab to `utm-rules/overview.md`. | Medium | High | Closes finding #18, supports the MOPs blocker pattern. |
| 9 | Clarify API auth - pick JWT-only or API-key, document the chosen flow with token TTL. | High | Medium | Closes finding #25; unblocks API developer evaluation. |
| 10 | Add `playbooks/agency-onboarding.md` walking through new workspace → custom domain → invite client → set UTM convention → first report. | Medium | Medium | Closes Storytelling Arc #3 and finding #3 in one move. |

---

## NAV CHANGES (docs.json outline)

```diff
  Guides tab:
    Get Started
+    getting-started/introduction              (rename frontmatter title to "Get Started in 3 minutes")
+    playbooks/utm-naming-convention            ← NEW (blocker #2, quick win #1)
+    playbooks/agency-onboarding                ← NEW (finding #3, quick win #10)
+    playbooks/messy-data-recovery              ← NEW (Storytelling Arc #1)
+    playbooks/q2-launch-playbook               ← NEW (Storytelling Arc #2)

    Links
      links/create-link
      links/utm-builder
      links/short-link
+     links/bulk-import                          ← NEW (extract from create-link bulk section, finding #7)
      links/folders
      links/tags
      links/qr-codes
~     links/password-protected → rename to "Link passwords (label only)" until enforcement ships
      links/link-expiration
      links/link-preview

    UTM Standards
      utm-templates/overview
      utm-templates/create-template
      utm-templates/manage-templates
+     utm-templates/preset-library               ← NEW (finding #17, gated on product confirming presets exist)
      utm-parameters/overview
      utm-rules/overview
+     utm-standards/templates-and-rules-together ← NEW (blocker #16)

    Domains  → rename to "Short Links & Domains"
      link-shortening/overview
      link-shortening/custom-domains

    Analytics
      analytics/overview
+     analytics/exporting-data                   ← NEW (finding #28, agency offboarding)

    Workspaces & Team
      organization/overview
      organization/managing-workspaces
      organization/managing-projects
      team-collaboration/overview

    Integrations
      integrations/pixel-tracking
+     integrations/ga4                           ← NEW (blocker #22, quick win #2)
+     integrations/mixpanel                      ← NEW
+     integrations/hubspot                       ← NEW (MOPs ICP question)
+     integrations/segment                       ← NEW

+   Migrate                                       ← NEW group (Storytelling Arc - onboarding from incumbents)
+     migrate/from-bitly
+     migrate/from-rebrandly
+     migrate/from-shortio

    Help
      help/common-issues
      help/feature-requests
      help/contact-support
+     help/exporting-data                        ← NEW (finding #28)
+     help/billing-and-limits                    ← NEW (no pricing/limits page exists)
+     help/glossary                              ← NEW (source vs medium vs campaign in one place)

  API Reference tab:
    Overview
      api/introduction
      api/errors
      api/best-practices
+     api/auth-flow                              ← NEW (finding #25)
+     api/rate-limits                            ← NEW (finding #26 - promote from best-practices)

    Links
      api/links-create
      api/links-get
+     api/links-update                           ← NEW PATCH /links/:id (finding #24)
      api/links-delete
+     api/links-bulk                             ← NEW dedicated bulk page
      api/links-parameters

+   Workspaces                                    ← NEW group
+     api/workspaces-get
+     api/workspaces-stats

+   Folders & Tags                                ← NEW group
+     api/folders
+     api/tags

+   Templates & Rules                             ← NEW group
+     api/templates
+     api/utm-rules
+     api/utm-parameters

+   Analytics                                     ← NEW group (api-developer blocker)
+     api/analytics-workspace
+     api/analytics-link

+   Webhooks                                      ← NEW group (placeholder if not yet shipped - document polling pattern)
+     api/webhooks-overview
```

Reorder Guides top-to-bottom: **Get Started → Playbooks → Links → UTM Standards → Short Links & Domains → Analytics → Workspaces & Team → Integrations → Migrate → Help**. Rationale: a MOPs lead's mental model is *standards-first* (playbooks + standards before tactics), not *features-first*.

---

## ASKS FOR THE HUMAN (open product questions)

1. **Preset template library** - does linkutm ship starter templates per channel out of the box? If not, the doc proposal in finding #17 should be a roadmap item, not docs.
2. **Analytics API** - do public endpoints exist for workspace/per-link analytics? `best-practices.mdx` implies yes; nothing in `api/*` documents them. Confirm before adding the `api/analytics-*` pages.
3. **Webhooks** - `best-practices.mdx` says "not currently implemented." Is this on the roadmap? If yes, document the planned event shape under "Asks for feedback"; if no, kill all webhook references.
4. **Click-limit enforcement** - the redirect either enforces it or it doesn't. `links/link-expiration.md` Step 3 says it does. `api/links-create.mdx` says it doesn't. Pick the truth, then I'll align the docs.
5. **Password enforcement** - same question. `links/password-protected.md` admits UI-only today. Is server-side gating on the roadmap? If not, the feature page is misleading by existing as a peer of QR/Folders.
6. **API-key auth (`lk_live_<hex>`)** - do these keys actually work as `Authorization: Bearer lk_live_...` against the API, or are they management-only artifacts? Doc currently implies both.
7. **Pricing / plan limits** - every page references "workspace maximums" (links, tags, templates, domains, password-protected links, team members, API calls). Are these published anywhere? A `help/billing-and-limits.md` page needs concrete numbers per tier.
8. **Production Swagger URL** - `api/introduction.mdx` mentions `http://localhost:8001/docs`. Is there a public Swagger / OpenAPI URL at `api.linkutm.com/docs`?
9. **Bitly / Rebrandly / Short.io migration** - `links/create-link.md` says importers exist. UI flow only? Are they API-callable too? If UI-only, add a `migrate/` group with screenshots, not API docs.
10. **Ownership transfer** - `organization/managing-workspaces.md` mentions "Transfer ownership separately" but no page or endpoint is documented for it. Does the flow exist?

---

## DELTA SUMMARY vs 2026-05-19 baseline (medium scan)

| Persona | Baseline (medium) | Thorough | Delta | Rationale |
|---|---|---|---|---|
| Marketing-ops lead | 6.5 | **6.15** | **–0.35** | Thorough confirmed: zero playbooks, no naming-convention page, no GA4 page, no glossary, no opinionated starter ruleset. Voice and rules-engine docs still strong. |
| In-house marketer  | 7.5 | **6.95** | **–0.55** | Zero screenshots/GIFs across all 9 link pages; preset library absent; bulk-import undersold to 3 lines. Quickstart promise of 3 minutes broken without visuals. |
| Agency operator    | 6.0 | **5.95** | **–0.05** | On-par with baseline. Workspace model is solid; onboarding playbook, white-label/billing-isolation specifics, data export still missing. |
| API developer      | 5.5 | **5.50** | **0.0** | Confirmed: only 4 endpoints documented, no analytics, no webhooks, no PATCH, no auth-flow detail. Quality of what IS there remains good. |
| **Overall**        | **7.0** | **6.18** | **–0.82** | Thorough mode penalizes missing surface area more aggressively than medium mode (which scores the pages that exist, not the pages that don't). The doc set is **shallower** than it appears at the overview level. |

Translation: the docs that exist are good. The docs that should exist (playbooks, GA4, agency onboarding, analytics API, webhooks, glossary, pricing) don't. Quick wins #1, #2, #3 alone would push the overall to 7.2+.
