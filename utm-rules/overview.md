---
title: "UTM rules"
description: "Workspace-wide validation and standardization that runs on every link save."
---

<Tip>
Setting up UTM Rules for the first time? Start with the [UTM naming convention](/playbooks/utm-naming-convention) playbook to define your approved source, medium, and campaign values before configuring the rules engine.
</Tip>

## What it is

UTM Rules is the validation engine that runs whenever a link is created or updated. One rule set per workspace. It applies in this order:

1. **Force lowercase** (default ON) - `Summer_Sale` → `summer_sale`
2. **Space replacement** (default `_`) - `summer sale` → `summer_sale`
3. **Max length** (default 100) - reject values longer than this
4. **Prohibited values** - fail if value contains any banned term
5. **Allowed characters** - fail if value doesn't match the allowed pattern

## When to use it

- Marketing team of more than one person - drift is guaranteed without rules.
- Anyone publishing UTMs to a shared analytics tool (GA, Mixpanel) where casing/typos create duplicate rows.
- Agencies enforcing client-specific naming conventions.

## How to configure

<Steps>
  <Step title="Open the rules page">
    Sidebar → **UTM Rules**.
  </Step>
  <Step title="Set the basics">
    <ParamField path="forceLowercase" default="true">Lowercase all values on save.</ParamField>
    <ParamField path="spaceCharacter" default="_">Replace runs of whitespace with this. Common values: `_`, `-`, `+`.</ParamField>

    <Frame>
      <img src="/images/utmrulesspacecharacter.png" alt="Space Character dropdown - Underscore selected, with Hyphen, Plus, URL Encoded, and Remove spaces options each showing a live preview" />
    </Frame>
    <ParamField path="maxParameterLength" default="100">Per-field character limit. 100 is a sensible default for human-readable UTMs.</ParamField>
    <ParamField path="prohibitedValues">Substrings that fail validation. Case-insensitive contains-match.</ParamField>
    <ParamField path="allowedCharactersRegex">Optional. Values that don't match this pattern are rejected.</ParamField>

  </Step>
  <Step title="Save and test">
    Try creating a link with bad values. Validation errors appear inline on the failing fields.
  </Step>
</Steps>

<Frame>
  <img src="/images/utmrules1sthalf.png" alt="UTM Rules page - Space Character, Force Lowercase toggle, Max Length, Allowed Characters regex, and Prohibited Values settings" />
</Frame>

## Real-world example

**Force consistency across the whole team:**

- **Force lowercase**: on
- **Space character**: underscore
- **Allowed characters**: letters, numbers, underscores, hyphens only
- **Blocked values**: test, draft, tbd

No more `Summer Sale!` slipping into prod.

## Common mistakes

<AccordionGroup>
  <Accordion title="Allowed-characters regex too tight">
    `^[a-z]+$` rejects digits. Most teams want `^[a-z0-9_-]+$`. Test your regex on existing valid values before saving.
  </Accordion>
</AccordionGroup>

## Edge cases

<Note>
**Rules cleaning vs validation.** Steps 1-2 (lowercase, space replacement) **transform** values silently. Steps 3-5 (length, prohibited, allowed characters) **reject** the save with errors.
</Note>

<Note>
**Default rules ship per workspace.** Every new workspace starts with force lowercase on, underscore for spaces, and a 100-character max length automatically.
</Note>
