---
title: "Team collaboration"
description: "Invite members, assign roles, configure notifications."
---

## What it is

Workspace members are users attached to a workspace with a role. Each gets per-workspace notification preferences, can create/edit links subject to role permissions, and can be removed by the owner.

## Roles

| Role         | Default permissions                                                                                  |
| ------------ | ---------------------------------------------------------------------------------------------------- |
| `owner`      | Everything. Created automatically for the workspace creator. Cannot be removed or have role changed. |
| `member`     | Default invite role. Create/edit links, manage folders/tags/templates within RBAC permissions.       |
| Custom roles | Defined via the RBAC system (admin, viewer, etc.) — workspace-level configurable.                    |

The exact action-level permissions are tied to the RBAC permission table — each role has a list of allowed `(method, path)` tuples.

## How to invite

<Steps>
  <Step title="Open Members">
    Sidebar → **Settings** → **Members** (or **Team**).
  </Step>
  <Step title="Send invite">
    Email + role. The system:
    - Checks the workspace's team-member maximum.
    - Rejects if the email is already a member or has a pending invite.
    - Sends an email with the accept link.
  </Step>
  <Step title="Manage pending invites">
    Resend (resets 7-day expiry) or cancel.
  </Step>
</Steps>

## How to accept an invite

The invitee clicks the link in the email. They sign in (or create an account with the same email) and confirm.

<Warning>
The invite is bound to the email it was sent to. If the invitee signs in with a different email, acceptance fails with `403 "This invite was sent to a different email address"`.
</Warning>

## Removing members

<Steps>
  <Step title="Open Members → row actions">
    The owner can remove any member except themselves.
  </Step>
  <Step title="Confirm">
    Member loses access immediately. Their created links remain in the workspace (creator user reference is retained, but they no longer see anything).
  </Step>
</Steps>

The system can't remove the owner via this flow. Transfer ownership or delete the workspace.

## Per-member notifications

Each member controls what triggers an email to them:

| Setting              | Trigger                                                       |
| -------------------- | ------------------------------------------------------------- |
| `notifyNewLinks`     | A teammate creates a link in this workspace                   |
| `notifyLinkClicks`   | Click milestones (100, 500, 1k, 5k, 10k, 50k, 100k, 500k, 1M) |
| `notifyTeamChanges`  | Member joins/leaves, role changes                             |
| `notifyWeeklyReport` | Weekly digest of workspace activity                           |

## Account-level notifications

Separately, each user has account-level toggles (under **Account → Notifications**) that override workspace-level for system events: domain updates, link expiry, billing alerts, security alerts, etc.

## Real-world example

Agency client team:

```
Workspace: Client: Globex
Members:
├── jane@acme-agency.com  — owner   (account manager)
├── kim@acme-agency.com   — member  (campaign analyst)
└── nick@acme-agency.com  — member  (designer, view-only role would fit better)
```

Jane gets all notifications. Kim gets click milestones + weekly report. Nick disables everything except weekly report.

## Common mistakes

<AccordionGroup>
  <Accordion title="Inviting beyond the team-member maximum">
    Each workspace has a team-member maximum. The invite endpoint rejects new invites once the workspace is at capacity, with a message naming the current count and limit.
  </Accordion>
  <Accordion title="Re-inviting an existing member">
    Returns `409 Conflict` — *"User is already a member of this workspace"*.
  </Accordion>
  <Accordion title="Changing the owner's role">
    Blocked by `403 "Cannot change owner role"`. Transfer ownership separately.
  </Accordion>
  <Accordion title="Removing the owner">
    Blocked. The owner can leave by deleting the workspace.
  </Accordion>
</AccordionGroup>

## Edge cases

<Note>
**Invite expiry.** 7 days. After expiry the link returns `403 "Invite has expired"`. Resend to issue a new token.
</Note>

<Note>
**Email normalization.** Invites match against lowercase-trimmed email. `Jane@Acme.com` and `jane@acme.com` are the same invite.
</Note>

<Note>
**Lowering the team-member maximum.** If a workspace's team-member maximum drops below the current count, current members keep access. The new maximum only blocks new invites until the count comes down through manual removal.
</Note>
