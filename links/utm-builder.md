---
title: "UTM builder"
description: "The five fields, what they mean, and how linkutm cleans them before saving."
---

## What it is

The UTM section of the link builder. Five standard fields plus optional custom UTMs. Values are cleaned by your [workspace UTM rules](/utm-rules/overview) on save.

## When to use it

Every link. UTMs are how Google Analytics, Mixpanel, Amplitude, and most attribution tools tell campaigns apart.

## The five fields

<ParamField path="utm_campaign" type="string">
  Which initiative this belongs to.
  Examples: `q2-launch`, `black-friday-2025`, `weekly-digest`.
</ParamField>

<ParamField path="utm_source" type="string">
  Where the click came from. Treat as a "platform name."
  Examples: `google`, `facebook`, `newsletter`, `partner-blog`.
</ParamField>

<ParamField path="utm_medium" type="string">
  How the click was delivered. The "channel type."
  Examples: `cpc`, `email`, `social`, `display`, `affiliate`.
</ParamField>

<ParamField path="utm_term" type="string">
  Optional. Paid search keyword or audience segment.
  Examples: `running-shoes`, `lookalike-us`.
</ParamField>

<ParamField path="utm_content" type="string">
  Optional. Differentiator for A/B variants or creative pieces.
  Examples: `headline-a`, `carousel-3`, `cta-orange`.
</ParamField>

## How it works under the hood

When you save a link, the entered values pass through your workspace's UTM Rules in this order:

<Steps>
  <Step title="Force lowercase">`Summer-Sale` → `summer-sale` (default ON).</Step>
  <Step title="Space replacement">`summer sale` → `summer-sale` using your configured space character (default `_`).</Step>
  <Step title="Max length">Truncated/rejected if over the workspace limit (default 100).</Step>
  <Step title="Prohibited terms">Hard fail if value contains any banned term you set ("test", "draft", etc).</Step>
  <Step title="Allowed characters regex">Hard fail if value doesn't match your allowed-character pattern.</Step>
  <Step title="Required fields">Hard fail if required field is empty / too short / not in your allowed values list.</Step>
  <Step title="Conditional logic">Auto-fill rules fire (e.g., if `source=google` then set `medium=cpc`).</Step>
</Steps>

The cleaned values are stored. See [UTM Rules](/utm-rules/overview) to configure each step.

## Custom UTM parameters

Beyond the five standards, you can attach arbitrary `utm_*` keys. Stored under `customUtmParams`, appended to every redirect.

```json
{
    "utm_source": "facebook",
    "utm_medium": "social",
    "utm_campaign": "q2-launch",
    "customUtmParams": {
        "audience": "lookalike-3",
        "creative": "video-15s"
    }
}
```

Final URL appends `&utm_audience=lookalike-3&utm_creative=video-15s`.

## Real-world examples

<Tabs>
  <Tab title="Google Ads">
    ```
    utm_source=google
    utm_medium=cpc
    utm_campaign=q2-launch
    utm_term={keyword}        ← Google Ads dynamic insertion
    utm_content=headline-a
    ```
  </Tab>
  <Tab title="Meta Ads">
    ```
    utm_source=facebook
    utm_medium=paid-social
    utm_campaign=q2-launch
    utm_content=video-carousel-v2
    ```
  </Tab>
  <Tab title="Email">
    ```
    utm_source=newsletter
    utm_medium=email
    utm_campaign=weekly-digest-2025-w19
    utm_content=hero-cta
    ```
  </Tab>
  <Tab title="Influencer / partner">
    ```
    utm_source=partner-jane-doe
    utm_medium=affiliate
    utm_campaign=q2-launch
    ```
  </Tab>
</Tabs>

## Common mistakes

<AccordionGroup>
  <Accordion title="Source vs medium swapped">
    `source=email, medium=newsletter` is wrong. Source = *platform name*; medium = *channel type*. Right: `source=newsletter, medium=email`.
  </Accordion>
  <Accordion title="Free-form campaign names">
    `Q2 Launch !!`, `q2 launch`, `Q2_Launch` become different rows in GA without rules. Use a [template](/utm-templates/overview) per campaign.
  </Accordion>
  <Accordion title="Using utm_term for non-search">
    `utm_term` is conventionally paid-search keyword. For audience segments use `utm_content` or a custom UTM.
  </Accordion>
  <Accordion title="PII in UTMs">
    UTMs land in your destination URL and analytics. Don't include emails, names, anything personally identifiable.
  </Accordion>
</AccordionGroup>

## Edge cases

<Note>
**UTMs already on the destination URL** are preserved. linkutm appends its UTMs as additional params; on key collision, the link's value wins.
</Note>

<Note>
**Conditional rules override silently.** If you typed `utm_medium=organic` but a rule says *"if source=google then medium=cpc"*, the rule wins and the saved record reflects `cpc` — no warning surfaces.
</Note>
