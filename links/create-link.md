# Create a Link

Learn how to create UTM-tagged links in linkutm to track your marketing campaigns effectively.

## Overview

Creating a link in linkutm allows you to generate trackable URLs with UTM parameters for your marketing campaigns. You can customize every aspect of your link, from basic UTM parameters to advanced features like password protection and device targeting.

## How to Create a Link

### Step 1: Navigate to Links

1. Go to your **Dashboard**
2. Click on **Links** in the sidebar
3. Click the **Create Link** or **+ New Link** button

### Step 2: Enter Basic Information

#### Destination URL
- Enter the full URL where you want to direct your users
- Example: `https://example.com/landing-page`
- Make sure to include `https://` or `http://`

#### Link Name
- Give your link a descriptive name for easy identification
- This is for internal use only and won't be visible to users
- Example: "Summer Campaign 2024 - Facebook Ad"

### Step 3: Configure UTM Parameters

UTM parameters help you track the source and effectiveness of your campaigns.

#### Required Parameters

**utm_source**
- The platform sending traffic (e.g., facebook, google, newsletter)
- Example: `facebook`

**utm_medium**
- The marketing medium (e.g., cpc, email, social, banner)
- Example: `social`

**utm_campaign**
- The specific campaign name
- Example: `summer_sale_2024`

#### Optional Parameters

**utm_term**
- Paid search keywords or target audience
- Example: `running_shoes`

**utm_content**
- Differentiates similar content or links within the same ad
- Example: `blue_button` or `header_link`

### Step 4: Choose Organization Options

#### Folder
- Select a folder to organize your link
- Create a new folder if needed
- Links can be moved between folders later

#### Tags
- Add color-coded tags for quick visual identification
- Available colors: Red, Yellow, Green, Blue, Purple, Brown
- Multiple tags can be added to a single link

### Step 5: Add Internal Notes (Optional)

- Add notes visible only to your team
- Use for collaboration, reminders, or context
- Supports markdown formatting

### Step 6: Configure Link Shortening (Optional)

- Choose your preferred link shortener
- Options include:
  - No shortening (use full URL)
  - Custom branded domain
  - Default project shortener
- [Learn more about link shortening](/link-shortening/custom-domains)

### Step 7: Set Advanced Options (Optional)

**Password Protection**
- Require a password before users can access the link
- Auto-generate secure passwords or create custom ones
- [Learn more about password protection](/links/password-protected)

**Link Expiration**
- Set an expiration date and time
- Configure a redirect URL for expired links
- [Learn more about link expiration](/links/link-expiration)

**Click Limits**
- Set maximum number of clicks allowed
- Link becomes inactive after reaching the limit
- [Learn more about click limits](/links/click-limits)

**Device Targeting**
- Set different URLs for iOS and Android devices
- [Learn more about device targeting](/links/device-targeting)

**Geo-location Targeting**
- Route users to different URLs based on their location
- [Learn more about geo-targeting](/links/geo-targeting)

**Social Media Preview**
- Customize Open Graph tags for social sharing
- Add custom title, description, and image
- [Learn more about link previews](/links/link-preview)

### Step 8: Save Your Link

1. Review all settings
2. Click **Create Link** or **Save**
3. Your link will be generated and added to your links list

## After Creating a Link

Once created, you can:
- **Copy** the link to clipboard
- **View analytics** to track performance
- **Generate QR code** for offline sharing
- **Edit** link details and settings
- **Duplicate** the link for similar campaigns
- **Share** with team members

## Quick Tips

- **Use Templates**: Save time by creating [UTM templates](/utm-templates/create-template) for recurring campaign types
- **Apply UTM Rules**: Set up [UTM rules](/utm-rules/project-rules) to automatically standardize your parameters
- **Bulk Creation**: Need multiple links? Use [bulk import](/links/bulk-import) with CSV files
- **Link Duplication**: Create variations quickly by [duplicating existing links](/links/duplicate-link)

## Best Practices

1. **Consistent Naming**: Use a consistent naming convention for your links
2. **Descriptive Parameters**: Make UTM parameters clear and descriptive
3. **Test Before Sharing**: Always test your link before using it in campaigns
4. **Use Folders**: Organize links by campaign, client, or time period
5. **Tag Strategically**: Use tags for priority, status, or campaign type
6. **Document Notes**: Add context in notes for future reference

## Common Use Cases

### Email Campaign Link
```
Destination: https://example.com/promo
utm_source: newsletter
utm_medium: email
utm_campaign: weekly_digest_jan
Folder: Email Campaigns
Tag: Blue (Email)
```

### Facebook Ad Link
```
Destination: https://example.com/product
utm_source: facebook
utm_medium: cpc
utm_campaign: summer_sale
utm_content: carousel_ad
Folder: Social Media Ads
Tag: Green (Active)
Password: Protected (for internal review)
```

### QR Code for Event
```
Destination: https://example.com/event-registration
utm_source: event_booth
utm_medium: qr_code
utm_campaign: tech_conference_2024
Generate QR Code: Yes
Folder: Events
Tag: Purple (Event)
```

## Troubleshooting

**Link not working?**
- Verify the destination URL is correct and accessible
- Check if link expiration or click limits have been reached
- Ensure password is correctly entered if protected

**UTM parameters not showing in analytics?**
- Confirm your analytics tool is properly configured
- Check that UTM parameters are appended to the URL
- Verify analytics integration is active

**Can't save link?**
- Check for required field validation errors
- Ensure UTM rules requirements are met
- Verify you have permission to create links in this project

## Related Documentation

- [UTM Parameters Overview](/utm-parameters/overview)
- [Link Shortening](/link-shortening/overview)
- [UTM Templates](/utm-templates/create-template)
- [UTM Rules](/utm-rules/overview)
- [Link Analytics](/analytics/link-analytics)

## Need Help?

If you have questions or need assistance, please contact our support team or refer to our comprehensive guides.
