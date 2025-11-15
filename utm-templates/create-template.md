# Create UTM Template

Learn how to create reusable UTM templates to streamline your link creation process.

## Overview

Creating UTM templates allows you to save frequently-used parameter combinations and apply them instantly when creating new links. This guide walks you through the process step-by-step.

## Before You Start

### Plan Your Template

Consider:
- **Purpose**: What type of campaign is this for?
- **Channel**: Which marketing channel (email, social, paid search)?
- **Fixed Parameters**: Which parameters stay the same?
- **Variable Parameters**: Which parameters change per link?
- **Audience**: Who will use this template?

### Gather Information

Have ready:
- Campaign naming convention
- Standard parameter values
- Any custom parameters needed
- Template description/notes

## Creating a Template: Step-by-Step

### Step 1: Navigate to Templates

1. Log into your linkutm dashboard
2. Click **Templates** in the sidebar
3. Click **Create Template** or **+ New Template** button

### Step 2: Name Your Template

**Template Name:**
- Enter a clear, descriptive name
- Include channel and purpose
- Make it easy to identify

**Examples:**
- ✅ "Email Newsletter - Weekly"
- ✅ "Facebook Ads - Lead Generation"
- ✅ "Google Ads - Brand Search"
- ❌ "Template 1" (too vague)

**Best Practices:**
- Use consistent naming format
- Include enough context
- Keep it concise (50 characters or less)

### Step 3: Add Description (Optional but Recommended)

**What to Include:**
- When to use this template
- What variable fields need
- Example use cases
- Any special instructions

**Example Description:**
```
Use for weekly email newsletters to subscribers.
- utm_campaign: Include week number (e.g., week_23_2024)
- utm_content: Specify featured article or CTA
Perfect for: Regular newsletter sends
```

### Step 4: Configure UTM Parameters

#### utm_source (Required)

**What it represents:** The platform sending the traffic

**Examples by Channel:**
- Email: `newsletter`, `promotional_email`
- Social: `facebook`, `instagram`, `linkedin`, `twitter`
- Paid Search: `google`, `bing`
- Organic: `google_organic`
- Referral: `partner_name`, `affiliate_name`

**For Templates:**
- Use specific value if always the same
- Example: Email template always uses `newsletter`
- Or leave variable if changes (e.g., multi-platform template)

#### utm_medium (Required)

**What it represents:** The marketing channel type

**Common Values:**
- `email` - Email campaigns
- `social` - Organic social media
- `cpc` - Paid advertising (cost-per-click)
- `display` - Display advertising
- `referral` - Referral traffic
- `organic` - Organic search
- `affiliate` - Affiliate marketing
- `print` - Print advertising
- `qr` - QR code campaigns

**For Templates:**
- Usually fixed for channel-specific templates
- Example: "Email Newsletter Template" always uses `email`

#### utm_campaign (Required)

**What it represents:** Specific campaign or promotion name

**Strategies for Templates:**

**Option 1: Leave Variable**
```
Template: Facebook Ads - General
utm_campaign: [To be filled per campaign]

Use case: Different campaigns on same channel
```

**Option 2: Include Pattern**
```
Template: Weekly Email Newsletter
utm_campaign: newsletter_week_[number]_2024

Use case: Recurring campaigns with consistent naming
```

**Option 3: Fixed Value**
```
Template: Product Launch 2024
utm_campaign: product_launch_q2_2024

Use case: Large campaign with multiple links
```

#### utm_term (Optional)

**What it represents:** Paid search keywords or audience targeting

**When to Include:**
- Paid search templates
- Audience-segmented campaigns
- A/B testing variations

**Examples:**
- Keywords: `running_shoes`, `blue_widgets`
- Audiences: `lookalike_audience`, `retargeting_cart`
- Segments: `cold_traffic`, `warm_leads`

**For Templates:**
- Leave blank if not applicable
- Include default value if always used
- Add note in description if variable

#### utm_content (Optional)

**What it represents:** Differentiates similar content/links

**When to Include:**
- A/B testing ads or emails
- Multiple CTAs in same campaign
- Different ad placements
- Creative variations

**Examples:**
- `headline_a`, `headline_b`
- `blue_button`, `red_button`
- `header_cta`, `footer_cta`
- `image_ad`, `video_ad`

**For Templates:**
- Leave blank for general use
- Include if always applicable
- Add examples in description

### Step 5: Add Custom Parameters (Optional)

**Why Add Custom Parameters:**
- Internal campaign IDs
- Specific audience information
- Additional tracking needs
- Integration requirements

**Common Custom Parameters:**

```
campaign_id: Internal campaign identifier
audience: Target audience segment
ad_id: Specific ad identifier
creative: Creative type or version
placement: Ad placement location
device: Device targeting
offer: Specific offer or promotion
```

**Adding Custom Parameters:**
1. Click **Add Custom Parameter**
2. Enter parameter name (no spaces, use underscores)
3. Enter default value (or leave for variable)
4. Add multiple as needed

### Step 6: Set Default Folder (Optional)

Assign a default folder where links from this template will be created:

- Select from existing folders
- Links automatically organized
- Can be overridden during link creation

**When Useful:**
- Channel-specific folders
- Client-specific folders (for agencies)
- Campaign-based organization

### Step 7: Assign Default Tags (Optional)

Add default tags that will be applied to links created from this template:

- Select tag colors
- Multiple tags supported
- Automatic categorization

**Example:**
```
Template: Facebook Ads - Lead Gen
Default Tags: 🔵 Blue (Social Media), 🟢 Green (Active)

Result: All links auto-tagged
```

[Learn more about tags →](/links/tags)

### Step 8: Add Template Notes (Optional)

**Internal Notes for Your Team:**
- Usage guidelines
- Tips and best practices
- Change log
- Contact for questions

**Example Notes:**
```
Created: May 2024
Owner: Marketing Team
Best for: Weekly promotional emails
Update utm_campaign with week number
Use utm_content to specify featured product
Questions? Contact marketing@company.com
```

### Step 9: Review and Save

**Final Checklist:**
- ✅ Template name is clear and descriptive
- ✅ Required parameters (source, medium, campaign) filled appropriately
- ✅ Optional parameters configured as needed
- ✅ Custom parameters added if necessary
- ✅ Description explains when/how to use
- ✅ Default folder assigned (if desired)
- ✅ Default tags selected (if applicable)

**Save Your Template:**
1. Click **Save Template** or **Create**
2. Template appears in your templates list
3. Ready to use immediately

## After Creating Your Template

### Test the Template

1. Create a test link using your new template
2. Verify all parameters fill correctly
3. Check if defaults are appropriate
4. Ensure variable fields are clear

### Share with Team

1. Inform team of new template availability
2. Provide usage guidelines
3. Explain when to use
4. Gather feedback

### Document Usage

Add to your team documentation:
- Template purpose
- When to use
- Example links
- Best practices

## Template Examples

### Example 1: Email Newsletter Template

```
Template Name: Email Newsletter - Weekly Digest

UTM Parameters:
- utm_source: newsletter
- utm_medium: email
- utm_campaign: [Variable - enter week_XX_2024]
- utm_content: [Variable - enter featured_article_topic]

Description:
Use for all weekly email newsletters sent to subscribers.
Campaign format: week_23_2024, week_24_2024, etc.
Content: Specify main featured content.

Default Folder: Email Campaigns
Default Tags: 🟡 Yellow (Email)

Notes:
- Send every Monday at 9 AM
- Track featured article clicks
- Update campaign with week number
```

### Example 2: Facebook Ads - Lead Generation Template

```
Template Name: Facebook Ads - Lead Gen

UTM Parameters:
- utm_source: facebook
- utm_medium: cpc
- utm_campaign: [Variable - enter campaign_name]
- utm_term: [Variable - enter audience_segment]
- utm_content: [Variable - enter ad_creative_type]

Custom Parameters:
- ad_id: [Variable]
- audience: [Variable]

Description:
For all Facebook lead generation ad campaigns.
Use utm_term for audience (e.g., lookalike, retargeting).
Use utm_content for creative type (e.g., video, carousel).

Default Folder: Social Media Ads > Facebook
Default Tags: 🔵 Blue (Facebook), 🟢 Green (Active)

Notes:
- Add Facebook Ad ID in custom parameter
- Track audience performance in utm_term
- Update creative variations in utm_content
```

### Example 3: Google Ads - Brand Search Template

```
Template Name: Google Ads - Brand Keywords

UTM Parameters:
- utm_source: google
- utm_medium: cpc
- utm_campaign: brand_search
- utm_term: [Variable - enter keyword]
- utm_content: [Variable - enter ad_variation]

Custom Parameters:
- campaign_id: [Variable - Google Ads campaign ID]

Description:
Use for all Google Ads brand keyword campaigns.
utm_term: Specific brand keyword triggering ad
utm_content: Ad headline/description variation

Default Folder: Paid Search > Google Ads
Default Tags: 🔴 Red (Paid), 🟢 Green (Active)

Notes:
- Brand keywords only (competitor keywords use different template)
- Match type doesn't need to be in UTM
- Track in Google Ads campaign_id for reconciliation
```

### Example 4: Product Launch - Multi-Channel Template

```
Template Name: Q2 Product Launch 2024

UTM Parameters:
- utm_source: [Variable - enter channel]
- utm_medium: [Variable - enter medium]
- utm_campaign: product_launch_q2_2024
- utm_content: [Variable - enter placement]

Custom Parameters:
- product: new_widget_pro
- launch_phase: pre_launch / launch / post_launch

Description:
Use for all Q2 2024 product launch marketing across channels.
Campaign is fixed: product_launch_q2_2024
Update source and medium per channel.
Track launch phase in custom parameter.

Default Folder: Product Launches > Q2 2024
Default Tags: 🟣 Purple (Product Launch), 🔴 Red (High Priority)

Notes:
- All launch-related links use this template
- Ensures consistent campaign tracking
- Update launch_phase as campaign progresses
```

### Example 5: Partner Referral Template

```
Template Name: Partner Referrals

UTM Parameters:
- utm_source: partner_[partner_name]
- utm_medium: referral
- utm_campaign: partnership_2024
- utm_content: [Variable - enter placement]

Custom Parameters:
- partner_id: [Partner internal ID]
- commission_tier: [A/B/C]

Description:
Use for all partner referral links.
Replace [partner_name] with actual partner name.
Track partner ID for commission attribution.

Default Folder: Partner Marketing
Default Tags: 🟤 Brown (Partner)

Notes:
- One template per partner or use variable
- Commission tier for internal tracking
- Reconcile with partner_id for payments
```

## Advanced Template Features

### Template Inheritance (If Available)

Create template hierarchies:

```
Parent Template: Social Media Base
- utm_medium: social

Child Template: Facebook Social
- Inherits: utm_medium: social
- Adds: utm_source: facebook

Child Template: LinkedIn Social
- Inherits: utm_medium: social
- Adds: utm_source: linkedin
```

### Conditional Parameters (If Available)

Set parameters based on conditions:

```
If utm_medium = email:
  Then utm_source = newsletter
If utm_medium = cpc:
  Then require utm_term
```

### Template Variables with Prompts (If Available)

Create prompts when using template:

```
Template: Webinar Campaign
On use, prompt for:
- Webinar Topic: [text input]
- Webinar Date: [date picker]
- Target Audience: [dropdown]

Automatically fills:
- utm_campaign: webinar_[topic]_[date]
- utm_term: [audience]
```

## Best Practices

### Template Naming

**DO:**
- ✅ Include channel in name
- ✅ Specify purpose clearly
- ✅ Use consistent format
- ✅ Keep concise but descriptive

**DON'T:**
- ❌ Use generic names
- ❌ Use abbreviations only
- ❌ Forget context
- ❌ Make too long (over 60 chars)

### Parameter Strategy

**DO:**
- ✅ Fix parameters that never change
- ✅ Document variable parameters
- ✅ Use consistent values
- ✅ Follow your naming conventions

**DON'T:**
- ❌ Leave all parameters variable
- ❌ Use inconsistent formatting
- ❌ Forget to document usage
- ❌ Over-complicate with too many parameters

### Description Writing

**DO:**
- ✅ Explain when to use
- ✅ List variable fields
- ✅ Provide examples
- ✅ Include special instructions

**DON'T:**
- ❌ Leave description blank
- ❌ Be too vague
- ❌ Assume knowledge
- ❌ Forget to update when template changes

### Template Maintenance

**DO:**
- ✅ Review quarterly
- ✅ Update as needed
- ✅ Archive outdated templates
- ✅ Gather team feedback

**DON'T:**
- ❌ Create and forget
- ❌ Let templates become stale
- ❌ Ignore usage data
- ❌ Skip documentation

## Troubleshooting

### Template Not Appearing in List

**Possible Issues:**
- Not saved properly
- Filter applied
- Wrong project/workspace
- Permissions issue

**Solutions:**
- Check save confirmation
- Clear any filters
- Verify correct workspace
- Check user permissions

### Parameters Not Auto-Filling

**Possible Issues:**
- Template not fully configured
- Browser cache issue
- System bug

**Solutions:**
- Edit template, verify all fields saved
- Refresh browser
- Try different browser
- Contact support

### Team Can't See Template

**Possible Issues:**
- Permission settings
- Not shared with team
- Wrong workspace

**Solutions:**
- Check sharing settings
- Verify template is project-level
- Ensure team members in correct workspace

## Related Documentation

- [UTM Templates Overview](/utm-templates/overview)
- [Manage Templates](/utm-templates/manage-templates)
- [Creating Links](/links/create-link)
- [UTM Parameters](/utm-parameters/overview)
- [UTM Rules](/utm-rules/overview)
- [Team Collaboration](/team-collaboration/overview)

## Need Help?

For questions about creating UTM templates, contact our support team or explore our comprehensive guides.
