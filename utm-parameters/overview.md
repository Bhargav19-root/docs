# UTM Parameters Overview

Learn how to manage and organize your UTM parameters in LinkUTM for consistent campaign tracking.

## What are UTM Parameters?

UTM (Urchin Tracking Module) parameters are tags you add to URLs to track the effectiveness of marketing campaigns across different traffic sources and mediums. They help you understand which campaigns drive the most traffic, conversions, and ROI.

## Standard UTM Parameters

### utm_source (Required)

**Identifies where the traffic is coming from**

**Examples:**
- `google` - Google search or ads
- `facebook` - Facebook posts or ads
- `newsletter` - Email newsletter
- `twitter` - Twitter/X posts
- `partner_site` - Referral partners

**Best Practice:** Use consistent, lowercase values

### utm_medium (Required)

**Identifies the marketing channel type**

**Examples:**
- `email` - Email campaigns
- `social` - Social media posts
- `cpc` - Cost-per-click advertising
- `display` - Display advertising
- `referral` - Referral links
- `organic` - Organic search

**Best Practice:** Stick to standard medium types for easier analytics

### utm_campaign (Required)

**Identifies the specific campaign or promotion**

**Examples:**
- `summer_sale_2024`
- `product_launch_q2`
- `newsletter_week_23`
- `black_friday`

**Best Practice:** Use descriptive, date-specific names

### utm_term (Optional)

**Identifies paid search keywords or audience segments**

**Examples:**
- `running_shoes` - Keyword for paid search
- `blue_widgets` - Product keyword
- `lookalike_audience` - Audience segment
- `retargeting_cart` - Retargeting audience

**Best Use:** Paid search campaigns and audience targeting

### utm_content (Optional)

**Differentiates similar content or links**

**Examples:**
- `banner_ad` vs `text_link`
- `blue_button` vs `red_button`
- `header_cta` vs `footer_cta`
- `image_a` vs `image_b`

**Best Use:** A/B testing and multiple CTAs in same campaign

## Managing UTM Parameters in LinkUTM

### Parameter Library

LinkUTM allows you to create and manage a library of UTM parameter values that can be reused across campaigns.

**Benefits:**
- **Consistency:** Use same values across campaigns
- **Autocomplete:** Previously used values suggest automatically
- **Organization:** Group parameters by type
- **Sub-parameters:** Create hierarchies for complex tracking
- **Team Alignment:** Everyone uses standardized values

### Creating Parameters

**Navigate to Parameters:**
1. Go to **Parameters** in the sidebar
2. Click **Create Parameter** or **+ New**
3. Select parameter type (source, medium, campaign, term, content)
4. Enter parameter value
5. Optionally add description
6. Save parameter

**When to Create:**
- New marketing channel
- New campaign launch
- New audience segment
- Standardize frequently-used values

[Learn how to create parameters →](/utm-parameters/create-parameter)

### Sub-Parameters

Organize related parameter values hierarchically:

```
utm_source: facebook
└─ Sub-parameters:
   ├─ facebook_ads
   ├─ facebook_organic
   └─ facebook_stories

utm_medium: email
└─ Sub-parameters:
   ├─ email_newsletter
   ├─ email_promotional
   └─ email_transactional
```

**Benefits:**
- Better organization
- Easier selection
- Logical grouping
- Clearer analytics

### Parameter Suggestions

As you create links, LinkUTM suggests previously used parameters:

- Type to search existing parameters
- Click to auto-fill
- Reduces typos
- Maintains consistency

## Custom Parameters

Beyond standard UTM parameters, you can add custom parameters for additional tracking:

**Common Custom Parameters:**
- `campaign_id` - Internal campaign identifier
- `ad_id` - Specific ad identifier
- `audience` - Target audience name
- `creative` - Creative type or version
- `placement` - Ad placement location
- `device` - Device targeting
- `offer` - Specific offer code

**Example:**
```
https://example.com/page?
  utm_source=facebook&
  utm_medium=cpc&
  utm_campaign=summer_sale&
  campaign_id=12345&
  audience=lookalike&
  creative=video
```

**Use Cases:**
- Internal tracking needs
- Integration with other tools
- Advanced segmentation
- Detailed attribution

## Parameter Best Practices

### Naming Conventions

**DO:**
- ✅ Use lowercase consistently
- ✅ Use underscores or hyphens instead of spaces
- ✅ Be descriptive but concise
- ✅ Follow a standard format
- ✅ Document your conventions

**DON'T:**
- ❌ Use spaces in parameter values
- ❌ Mix uppercase and lowercase randomly
- ❌ Use special characters
- ❌ Create overly long values
- ❌ Use inconsistent formatting

### Consistency Examples

**Good - Consistent:**
```
utm_source: facebook (always lowercase)
utm_source: instagram (always lowercase)
utm_source: linkedin (always lowercase)
```

**Bad - Inconsistent:**
```
utm_source: Facebook (mixed case)
utm_source: INSTAGRAM (all caps)
utm_source: linked-in (incorrect name)
```

### Value Standardization

**Use Standard Values:**

**utm_medium Standard Values:**
- `email`, `social`, `cpc`, `display`, `referral`, `organic`, `affiliate`

**utm_source Standard Values:**
- Platform names: `facebook`, `google`, `twitter`, `linkedin`
- Keep consistent: always `facebook`, never `fb` or `Facebook`

### Documentation

**Create a Parameter Guide:**

```
UTM Parameter Standards - Our Company

utm_source:
- newsletter (all email newsletters)
- promo_email (promotional emails)
- facebook, instagram, linkedin (social media)
- google, bing (search engines)

utm_medium:
- email (all email campaigns)
- social (organic social)
- cpc (paid advertising)
- referral (partner referrals)

utm_campaign:
- Format: [campaign_name]_[quarter]_[year]
- Example: summer_sale_q2_2024
```

## Importing and Exporting Parameters

### CSV Import

Bulk create parameters from CSV file:

1. Prepare CSV with parameter values
2. Navigate to **Parameters** page
3. Click **Import** or **Import CSV**
4. Upload file
5. Map columns to parameter types
6. Review and confirm import

**Use Cases:**
- Migrate from another tool
- Bulk setup for new project
- Standardize across team
- Annual campaign setup

[Learn about CSV import →](/utm-parameters/import-export)

### CSV Export

Export your parameter library:

1. Navigate to **Parameters** page
2. Select parameters to export (or all)
3. Click **Export** or **Download CSV**
4. Save file

**Use Cases:**
- Backup parameter library
- Share with other teams
- Documentation
- Audit and review

## Parameter Analytics

### Usage Tracking

View parameter performance:
- **Most Used Parameters:** Which parameters are used most
- **Recent Parameters:** Latest additions
- **Unused Parameters:** Candidates for cleanup
- **Performance by Parameter:** Which parameters drive results

### Performance Insights

Analyze by parameter:
- Click-through rates by source
- Conversions by medium
- ROI by campaign
- Engagement by content variant

**Strategic Decisions:**
- Allocate budget to best-performing sources
- Optimize underperforming mediums
- Replicate successful campaigns
- Sunset ineffective channels

## Integration with Other Features

### Parameters + Templates

Save frequently-used parameters in templates:
- Create template with standard parameters
- Apply to new links instantly
- Ensure consistency
- Speed up link creation

[Learn about UTM templates →](/utm-templates/overview)

### Parameters + Rules

Enforce parameter standards automatically:
- Require specific parameters
- Validate parameter formats
- Standardize capitalization
- Set default values

[Learn about UTM rules →](/utm-rules/overview)

### Parameters + Links

Use parameter library when creating links:
- Select from saved parameters
- Autocomplete suggestions
- Quick parameter application
- Consistent tracking

[Learn about creating links →](/links/create-link)

## Common Parameter Strategies

### By Industry

**E-commerce:**
```
utm_campaign: [season]_[promotion]_[year]
- summer_sale_2024
- black_friday_2024
- holiday_deals_2024

utm_content: [product_category]_[placement]
- dresses_homepage_banner
- shoes_sidebar_ad
```

**SaaS:**
```
utm_campaign: [goal]_[month]_[year]
- trial_signups_may_2024
- feature_launch_june_2024
- upgrade_campaign_q2_2024

utm_term: [audience_segment]
- free_users
- trial_expiring
- power_users
```

**Agency:**
```
utm_campaign: [client]_[campaign_type]_[timeframe]
- acme_brand_awareness_q1
- techco_lead_gen_may

utm_source: [channel]_[client]
- facebook_acme
- google_techco
```

**Content/Media:**
```
utm_campaign: [content_type]_[topic]_[timeframe]
- blog_seo_tips_may
- podcast_ep_123
- video_tutorial_series

utm_content: [placement]_[cta]
- inline_cta
- sidebar_subscribe
- footer_newsletter
```

## Parameter Cleanup

### Regular Audits

**Monthly Review:**
- Check for unused parameters
- Identify duplicates or near-duplicates
- Merge similar parameters
- Remove obsolete values

**Quarterly Cleanup:**
- Archive old campaign parameters
- Consolidate sources/mediums
- Update documentation
- Train team on changes

### Identifying Issues

**Common Problems:**

**Duplicates:**
```
❌ facebook, Facebook, FACEBOOK, fb
✅ facebook (standardize on one)

❌ email_newsletter, newsletter_email, newsletter
✅ newsletter (pick one format)
```

**Typos:**
```
❌ googl, gogle, google (typos)
✅ google (correct spelling)

❌ instgram, intagram
✅ instagram (correct spelling)
```

**Inconsistent Formatting:**
```
❌ summer sale 2024, summer-sale-2024, SummerSale2024
✅ summer_sale_2024 (consistent format)
```

### Merge and Consolidate

**Steps:**
1. Identify similar parameters
2. Choose standard version
3. Update links using old versions (if needed)
4. Delete duplicate parameters
5. Document change

## Troubleshooting

### Parameter Not Appearing in Suggestions

**Solutions:**
- Verify parameter is saved
- Check spelling
- Refresh browser
- Clear browser cache
- Check project/workspace

### Analytics Not Tracking Parameter

**Solutions:**
- Verify analytics integration active
- Check parameter is in URL
- Wait 24-48 hours for data
- Verify analytics tool configuration
- Test with different analytics tool

### Too Many Parameters

**Solutions:**
- Conduct cleanup audit
- Merge duplicates
- Archive old campaigns
- Document which to keep
- Set retention policy

## Related Documentation

- [Create UTM Parameters](/utm-parameters/create-parameter)
- [Import/Export Parameters](/utm-parameters/import-export)
- [UTM Builder](/links/utm-builder)
- [UTM Templates](/utm-templates/overview)
- [UTM Rules](/utm-rules/overview)
- [Link Analytics](/analytics/link-analytics)

## Need Help?

For questions about UTM parameters, contact our support team or explore our comprehensive guides.
