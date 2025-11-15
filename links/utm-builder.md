# UTM Builder

Learn how to use LinkUTM's UTM parameter builder to create perfectly tagged marketing links.

## Overview

The UTM Builder is your central tool for creating trackable links with UTM parameters. It provides an intuitive interface to add, customize, and manage all UTM parameters for your marketing campaigns.

## What are UTM Parameters?

UTM (Urchin Tracking Module) parameters are tags added to URLs that help you track the effectiveness of your marketing campaigns in analytics tools like Google Analytics.

### Standard UTM Parameters

**utm_source** (Required)
- Identifies which site or platform sent the traffic
- Examples: `google`, `facebook`, `newsletter`, `twitter`

**utm_medium** (Required)
- Identifies the type of marketing medium
- Examples: `cpc`, `email`, `social`, `banner`, `affiliate`

**utm_campaign** (Required)
- Identifies the specific campaign or promotion
- Examples: `summer_sale`, `product_launch`, `back_to_school`

**utm_term** (Optional)
- Identifies paid search keywords or audience targeting
- Examples: `running_shoes`, `blue_widgets`, `luxury_watches`

**utm_content** (Optional)
- Differentiates similar content or links within the same campaign
- Examples: `banner_ad`, `text_link`, `blue_button`, `header_cta`

## Using the UTM Builder

### Step 1: Enter Your Destination URL

1. In the link creation form, enter your destination URL
2. Include the full URL with `https://` or `http://`
3. Example: `https://example.com/product-page`

### Step 2: Build Your UTM Parameters

#### From Scratch

**Manual Entry**
1. Click on each UTM parameter field
2. Type your value
3. Use lowercase letters, numbers, and underscores
4. Avoid spaces (use underscores or hyphens instead)

**Using Suggestions**
- As you type, the system shows previously used values
- Click a suggestion to auto-fill
- Maintains consistency across campaigns

#### From Saved Parameters

1. Click **Select from Parameters**
2. Browse your saved UTM parameter values
3. Click to add to your link
4. [Learn more about managing parameters →](/utm-parameters/overview)

#### Using Templates

1. Click **Use Template**
2. Select a pre-configured template
3. All UTM parameters auto-fill
4. Customize as needed
5. [Learn more about templates →](/utm-templates/create-template)

### Step 3: Preview Your Link

- See the complete URL with all UTM parameters
- Copy the full URL to clipboard
- Verify all parameters are correct

### Step 4: Add Custom Parameters (Optional)

Need tracking beyond standard UTM parameters?

1. Click **Add Custom Parameter**
2. Enter parameter name (e.g., `campaign_id`, `user_type`)
3. Enter parameter value
4. Multiple custom parameters supported

**Common custom parameters:**
- `campaign_id`: Internal campaign identifier
- `ad_id`: Specific ad identifier
- `creative_type`: Type of creative asset
- `placement`: Ad placement location
- `audience`: Target audience segment

## UTM Parameter Best Practices

### Naming Conventions

**Use Consistent Formatting**
- ✅ Good: `facebook_ads`, `summer_campaign_2024`
- ❌ Avoid: `Facebook Ads`, `SUMMER-campaign 2024`

**Be Specific But Concise**
- ✅ Good: `email_newsletter_weekly`
- ❌ Too vague: `email`
- ❌ Too long: `email_newsletter_weekly_digest_sent_monday_morning`

**Use Descriptive Values**
- ✅ Good: `instagram_story`, `google_search_brand`
- ❌ Avoid: `ig_s`, `goog1`

### Standardization

**Create a Naming Standard**
- Document your conventions
- Share with your team
- Use [UTM Rules](/utm-rules/project-rules) to enforce

**Common Patterns:**
```
utm_source: [platform]
- facebook, google, linkedin, newsletter

utm_medium: [channel_type]
- cpc, email, social, referral, organic

utm_campaign: [campaign_name]_[timeframe]
- summer_sale_2024, product_launch_q1

utm_content: [variant]_[placement]
- blue_button_header, carousel_slide2
```

### Source Examples by Platform

**Social Media**
- Facebook: `facebook`
- Instagram: `instagram`
- Twitter/X: `twitter`
- LinkedIn: `linkedin`
- TikTok: `tiktok`
- Pinterest: `pinterest`

**Search Engines**
- Google Ads: `google`
- Bing Ads: `bing`
- Google Organic: `google_organic`

**Email**
- Newsletter: `newsletter`
- Promotional: `promo_email`
- Transactional: `transactional_email`

**Other**
- Affiliate: `affiliate_name`
- Partner: `partner_name`
- QR Code: `qr_code`
- SMS: `sms`

### Medium Examples by Channel Type

**Paid Advertising**
- Cost-per-click: `cpc`
- Display ads: `display`
- Video ads: `video`
- Shopping ads: `shopping`

**Owned Channels**
- Email: `email`
- Website: `website`
- Blog: `blog`

**Earned & Shared**
- Social: `social`
- Referral: `referral`
- Organic: `organic`

**Offline**
- Print: `print`
- QR Code: `qr`
- Event: `event`

## Advanced UTM Builder Features

### Auto-Complete

The UTM Builder remembers your previous values:
- Start typing to see suggestions
- Click to auto-fill
- Maintains consistency
- Reduces typos

### Parameter Validation

Built-in validation ensures quality:
- Checks for invalid characters
- Warns about spaces
- Enforces required fields
- Applies [UTM Rules](/utm-rules/required-fields)

### Bulk Parameter Application

Need to create multiple similar links?
1. Create your first link with UTM parameters
2. Use [Duplicate Link](/links/duplicate-link) feature
3. Modify only what changes
4. Save time on repetitive tasks

### Template Integration

Save time with templates:
1. Create UTM templates for common scenarios
2. Apply template when building links
3. Override specific parameters as needed
4. [Learn about templates →](/utm-templates/create-template)

## Real-World Examples

### Example 1: Facebook Ad Campaign

```
Destination URL: https://shop.example.com/summer-collection
utm_source: facebook
utm_medium: cpc
utm_campaign: summer_sale_2024
utm_content: carousel_ad_beachwear
utm_term: women_25_34

Final URL: https://shop.example.com/summer-collection?utm_source=facebook&utm_medium=cpc&utm_campaign=summer_sale_2024&utm_content=carousel_ad_beachwear&utm_term=women_25_34
```

### Example 2: Email Newsletter

```
Destination URL: https://blog.example.com/new-features
utm_source: newsletter
utm_medium: email
utm_campaign: weekly_digest_week23
utm_content: featured_article

Final URL: https://blog.example.com/new-features?utm_source=newsletter&utm_medium=email&utm_campaign=weekly_digest_week23&utm_content=featured_article
```

### Example 3: Instagram Story

```
Destination URL: https://example.com/signup
utm_source: instagram
utm_medium: social
utm_campaign: product_launch_q2
utm_content: story_swipe_up
Custom: influencer: @johndoe

Final URL: https://example.com/signup?utm_source=instagram&utm_medium=social&utm_campaign=product_launch_q2&utm_content=story_swipe_up&influencer=@johndoe
```

### Example 4: Google Ads - Brand Search

```
Destination URL: https://example.com/
utm_source: google
utm_medium: cpc
utm_campaign: brand_search
utm_term: example_company
utm_content: text_ad_headline1

Final URL: https://example.com/?utm_source=google&utm_medium=cpc&utm_campaign=brand_search&utm_term=example_company&utm_content=text_ad_headline1
```

### Example 5: Partner Referral

```
Destination URL: https://example.com/partner-offer
utm_source: partner_techblog
utm_medium: referral
utm_campaign: partnership_q1_2024
utm_content: blog_post_footer

Final URL: https://example.com/partner-offer?utm_source=partner_techblog&utm_medium=referral&utm_campaign=partnership_q1_2024&utm_content=blog_post_footer
```

## Common Mistakes to Avoid

### ❌ Using Spaces
```
Wrong: utm_source=facebook ads
Right: utm_source=facebook_ads
```

### ❌ Inconsistent Casing
```
Wrong Campaign 1: utm_source=Facebook
Wrong Campaign 2: utm_source=facebook
Wrong Campaign 3: utm_source=FACEBOOK
Right: utm_source=facebook (always)
```

### ❌ Too Generic
```
Wrong: utm_campaign=campaign1
Right: utm_campaign=summer_sale_2024
```

### ❌ Special Characters
```
Wrong: utm_campaign=sale@2024!
Right: utm_campaign=sale_2024
```

### ❌ Missing Required Fields
```
Wrong: Only adding utm_source
Right: Include source, medium, and campaign (minimum)
```

## Integrations

### Google Analytics 4
- UTM parameters automatically tracked
- View campaign performance
- Attribution reporting
- [Connect Google Analytics →](/analytics/google-analytics-integration)

### Other Analytics Platforms
- Compatible with all major analytics tools
- Adobe Analytics
- Mixpanel
- Amplitude
- Custom analytics solutions

## UTM Builder Shortcuts

### Keyboard Shortcuts
- `Tab`: Move to next parameter field
- `Ctrl/Cmd + V`: Paste URL
- `Ctrl/Cmd + C`: Copy generated link

### Quick Actions
- **Duplicate Last**: Copy parameters from your last created link
- **Clear All**: Remove all UTM parameters
- **Reset**: Return to default values

## Quality Control

### Before Creating Your Link

✅ **Checklist:**
- [ ] Destination URL is correct and accessible
- [ ] All required UTM parameters filled
- [ ] No spaces in parameter values
- [ ] Consistent lowercase formatting
- [ ] Campaign name is descriptive
- [ ] Values match your naming convention
- [ ] Custom parameters have clear purposes

### After Creating Your Link

✅ **Verification:**
1. Copy the link and test in a browser
2. Verify it redirects correctly
3. Check UTM parameters in the URL bar
4. Confirm tracking in analytics (wait a few minutes)
5. Share with team for review if needed

## Troubleshooting

### UTM Parameters Not Appearing

**Problem:** Parameters not showing in analytics

**Solutions:**
- Ensure analytics tracking code is installed
- Check that parameters are in the URL
- Wait 24-48 hours for data processing
- Verify analytics configuration

### Special Characters in Parameters

**Problem:** Parameters contain special characters

**Solutions:**
- UTM Builder automatically URL-encodes special characters
- Avoid using special characters when possible
- Use underscores or hyphens instead of spaces

### Link Too Long

**Problem:** Final URL is extremely long

**Solutions:**
- Use [link shortening](/links/short-link)
- Simplify parameter values
- Remove unnecessary custom parameters
- Consider using custom short codes

## Related Documentation

- [UTM Parameters Management](/utm-parameters/overview)
- [Creating UTM Templates](/utm-templates/create-template)
- [UTM Rules](/utm-rules/overview)
- [Link Analytics](/analytics/link-analytics)
- [Google Analytics Integration](/analytics/google-analytics-integration)

## Need Help?

For questions about UTM parameters or the UTM Builder, contact our support team or explore our comprehensive guides.
