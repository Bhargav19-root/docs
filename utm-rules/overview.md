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
5. **Allowed characters regex** - fail if value doesn't match
6. **Required field rules** - fail if a required field is empty/short/wrong-format/not-in-list
7. **Conditional logic rules** - auto-set fields based on other fields

If `isActive = false`, validation is skipped entirely; rules are still saved.

## When to use it

- Marketing team of more than one person - drift is guaranteed without rules.
- Anyone publishing UTMs to a shared analytics tool (GA, Mixpanel) where casing/typos create duplicate rows.
- Agencies enforcing client-specific naming conventions.

## How to configure

<Steps>
  <Step title="Open the rules page">
    Sidebar → **UTM Rules**. The page is sectioned: Basic, Required Fields, Conditional Logic.
  </Step>
  <Step title="Set the basics">
    <ParamField path="forceLowercase" type="boolean" default="true">Lowercase all values on save.</ParamField>
    <ParamField path="spaceCharacter" type="string" default="_">Replace runs of whitespace with this. Common values: `_`, `-`, `+`.</ParamField>

    <Frame>
      <img src="/images/utmrulesspacecharacter.png" alt="Space Character dropdown - Underscore selected, with Hyphen, Plus, URL Encoded, and Remove spaces options each showing a live preview" />
    </Frame>
    <ParamField path="maxParameterLength" type="integer" default="100">Per-field char limit. Stripe/GA tolerate ~2k; 100 is sane for human-readable UTMs.</ParamField>
    <ParamField path="prohibitedValues" type="string[]">Substrings that fail validation. Case-insensitive contains-match.</ParamField>
    <ParamField path="allowedCharactersRegex" type="string">Optional. Values that don't match this regex are rejected. Example: `^[a-z0-9_-]+$`.</ParamField>

  </Step>
  <Step title="Add required-field rules">
    Each rule pins a validation type to one or more parameters:

    | Type | Behavior |
    |---|---|
    | `not_empty` | Field must have a value |
    | `min_length` | Value must be at least N chars |
    | `max_length` | Value must be at most N chars |
    | `regex` | Value must match the regex |
    | `allowed_values` | Value must be one of the listed values |

    Rules with `isActive=false` are stored but skipped.

  </Step>
  <Step title="Add conditional logic rules">
    Auto-fill rule format: **IF `ifField` `condition` `ifValue` THEN set `thenSet` to `toValue`**.

    Conditions: `equals`, `contains`, `starts_with`, `ends_with`, `not_empty`.

    Conditional rules run **after** required-field validation. If your rule sets a field, the user's input is overridden silently.

  </Step>
  <Step title="Save and test">
    Try creating a link with bad values. Validation errors appear inline on the failing fields. Conditional auto-fills are applied silently to the stored record.
  </Step>
</Steps>

<Frame>
  <img src="/images/utmrules1sthalf.png" alt="UTM Rules page - Space Character, Force Lowercase toggle, Max Length, Allowed Characters regex, and Prohibited Values settings" />
</Frame>

## Real-world examples

<Tabs>
  <Tab title="Force consistency">
    ```
    forceLowercase: true
    spaceCharacter: "_"
    allowedCharactersRegex: "^[a-z0-9_-]+$"
    prohibitedValues: ["test", "draft", "tbd"]
    ```
    No more `Summer Sale!` slipping into prod.
  </Tab>
  <Tab title="Require campaign">
    ```
    Required field rule:
    {
      validationType: "not_empty",
      requiredParameters: ["campaign"],
      description: "Campaign name is required"
    }
    ```
    Every link must have `utm_campaign`.
  </Tab>
  <Tab title="Allow only known sources">
    ```
    Required field rule:
    {
      validationType: "allowed_values",
      requiredParameters: ["source"],
      allowedValues: ["google", "facebook", "linkedin", "newsletter"]
    }
    ```
    Anything outside the list fails.
  </Tab>
  <Tab title="Auto-fill medium">
    ```
    Conditional logic rule:
    if ifField=source, condition=equals, ifValue=google
    then set thenSet=medium, toValue=cpc
    ```
    Anyone picking `source=google` gets `medium=cpc` automatically.
  </Tab>
</Tabs>

## Common mistakes

<AccordionGroup>
  <Accordion title="Allowed-characters regex too tight">
    `^[a-z]+$` rejects digits. Most teams want `^[a-z0-9_-]+$`. Test your regex on existing valid values before saving.
  </Accordion>
  <Accordion title="Required field with allowed_values but no list">
    Empty `allowedValues` array effectively allows everything. Either drop the rule or populate the list.
  </Accordion>
  <Accordion title="Conditional logic loops">
    *If medium=cpc then set source=google* + *if source=google then set medium=cpc* both run on save in declaration order. They don't loop, but the result depends on order. Keep conditional rules unidirectional.
  </Accordion>
  <Accordion title="Turning off rules during cleanup">
    Setting `isActive=false` skips ALL validation, including required fields and prohibited values. Disable individual rules instead, or fix bad values rather than disabling validation.
  </Accordion>
</AccordionGroup>

## Edge cases

<Note>
**Rules cleaning vs validation.** Steps 1-2 (lowercase, space replacement) **transform** values silently. Steps 3-6 (length, prohibited, regex, required) **reject** the save with errors. Step 7 (conditional) **transforms** silently - the saved record reflects the override but no warning surfaces.
</Note>

<Note>
**Invalid regex is silently skipped.** If your `allowedCharactersRegex` doesn't compile, validation skips that step rather than failing. Test regex with online tools before saving.
</Note>

<Note>
**Default rules ship per workspace.** Every new workspace gets `forceLowercase=true, spaceCharacter='_', maxParameterLength=100, isActive=true` automatically.
</Note>
