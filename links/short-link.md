# Short Link

Learn how to create shortened links using LinkUTM's link shortening feature.

## Overview

Link shortening converts long, complex URLs with UTM parameters into short, memorable links. This makes your links easier to share, track, and manage across all marketing channels.

## Why Use Short Links?

### Benefits

**Better User Experience**
- Clean, professional-looking URLs
- Easier to read and remember
- Better for social media sharing with character limits

**Improved Click-Through Rates**
- Short links appear more trustworthy
- Less intimidating than long parameter-filled URLs
- Better for SMS and print marketing

**Brand Recognition**
- Use custom branded domains
- Reinforce brand identity in every link
- Build trust with recognizable domains

**Easier Tracking**
- Simplified link management
- All UTM parameters hidden but still tracked
- Easier to share internally with teams

## How Short Links Work

When you create a short link:

1. **Original URL**: `https://example.com/product?utm_source=facebook&utm_medium=cpc&utm_campaign=summer_sale&utm_content=ad1`

2. **Shortened URL**: `https://yourbrand.link/abc123`

3. **User clicks short link** → Redirects to original URL with all UTM parameters intact

4. **Analytics tracked** → All click data and UTM information captured

## Creating a Short Link

### During Link Creation

1. Create a new link or edit an existing one
2. Navigate to the **Link Shortening** section
3. Select your preferred shortener:
   - **Custom Branded Domain** (recommended)
   - **Default Project Shortener**
   - **No Shortening** (use full URL)
4. Save your link

The system automatically generates a unique short code for your link.

### For Existing Links

1. Go to your **Links** page
2. Find the link you want to shorten
3. Click the **Edit** button
4. Enable link shortening
5. Select your shortener
6. Save changes

## Shortener Options

### Custom Branded Domain

Use your own domain for link shortening (e.g., `go.yourbrand.com`, `link.yourcompany.io`)

**Advantages:**
- Full brand control
- Builds trust with your audience
- Professional appearance
- Custom domain ownership

**Requirements:**
- Own a domain
- Configure DNS settings
- Verify domain ownership

[Learn how to set up custom domains →](/link-shortening/custom-domains)

### Default Project Shortener

Use the default shortener configured at the project level.

**Advantages:**
- No setup required
- Instant availability
- Consistent across project

**When to use:**
- Quick testing
- Internal links
- Small campaigns

### No Shortening

Use the full URL with visible UTM parameters.

**When to use:**
- Transparency required
- Email marketing (some filters flag shortened links)
- Partners require full URL visibility
- Internal documentation

## Managing Short Links

### View Short Link

1. Go to **Links** page
2. Your shortened URL appears in the link list
3. Click the **Copy** icon to copy to clipboard

### Edit Short Link

- You can change the shortener service
- You cannot change the short code (it's permanent)
- Original URL and UTM parameters can be modified

### Deactivate Short Link

1. Edit the link
2. Change shortener to "No Shortening"
3. The short code becomes inactive
4. Previous short links will show an error

## Short Link Analytics

Track performance of your short links:

- **Total clicks** on the short link
- **Unique visitors** who clicked
- **Geographic data** of clickers
- **Device and browser** information
- **Referrer sources** that shared your link
- **Click timeline** showing activity over time

[Learn more about analytics →](/analytics/link-analytics)

## Custom Short Codes

### Automatic Generation

By default, LinkUTM generates a random short code:
- Example: `abc123`, `x7k9m2`, `qr4t8p`
- Ensures uniqueness
- Case-sensitive

### Custom Short Codes (Feature Availability)

Some plans allow custom short codes:
- Example: `summer-sale`, `signup-now`
- Must be unique within your domain
- Limited characters (a-z, 0-9, hyphens)

## Best Practices

### Domain Selection

1. **Use Branded Domains for External Campaigns**
   - Customer-facing marketing
   - Social media posts
   - Print materials

2. **Use Default Shortener for Internal Use**
   - Team sharing
   - Testing
   - Draft campaigns

3. **Avoid Shortening for Email**
   - Some email filters flag shortened URLs
   - Consider using full URLs in emails
   - Test with your email service provider

### Link Management

1. **Organize by Campaign**
   - Group short links in folders
   - Tag by platform or campaign type
   - Use descriptive link names

2. **Test Before Launching**
   - Verify the short link redirects correctly
   - Test on different devices
   - Check analytics tracking

3. **Monitor Performance**
   - Track click-through rates
   - Compare short vs. long links
   - Analyze user behavior

### Security

1. **Password Protect Sensitive Links**
   - Pre-launch campaign links
   - Internal resources
   - Limited audience content

2. **Set Expiration Dates**
   - Time-sensitive offers
   - Event-specific links
   - Seasonal campaigns

3. **Use Click Limits**
   - Limited inventory offers
   - Early bird specials
   - Exclusive access

## Short Link Examples

### Social Media Campaign
```
Original: https://example.com/summer-collection?utm_source=instagram&utm_medium=social&utm_campaign=summer_2024
Shortened: https://brand.link/summer24
Use case: Instagram bio link, Instagram stories
```

### Email Newsletter
```
Original: https://example.com/blog/new-features?utm_source=newsletter&utm_medium=email&utm_campaign=weekly_digest
Shortened: https://brand.link/features
Use case: Email newsletter, text-based emails
```

### Print Advertisement
```
Original: https://example.com/special-offer?utm_source=magazine&utm_medium=print&utm_campaign=fall_ads
Shortened: https://brand.link/offer
Use case: Magazine ads, billboards, business cards
```

### SMS Campaign
```
Original: https://example.com/flash-sale?utm_source=sms&utm_medium=text&utm_campaign=flash_friday
Shortened: https://brand.link/flash
Use case: SMS marketing, character limit constraints
```

### QR Code
```
Original: https://example.com/menu?utm_source=qr&utm_medium=offline&utm_campaign=restaurant_table
Shortened: https://brand.link/menu
Generate QR: Yes
Use case: Restaurant table tents, product packaging
```

## Common Issues & Solutions

### Short Link Not Working

**Problem:** Short link shows error or doesn't redirect

**Solutions:**
- Verify the link is still active
- Check if link has expired
- Ensure click limit hasn't been reached
- Verify domain DNS is configured correctly

### Short Link Analytics Not Tracking

**Problem:** Clicks not appearing in analytics

**Solutions:**
- Confirm analytics integration is active
- Check that tracking is enabled for the link
- Wait a few minutes for data to sync
- Verify your analytics tool is properly connected

### Custom Domain Not Working

**Problem:** Branded domain short links not resolving

**Solutions:**
- Verify DNS records are correctly configured
- Allow 24-48 hours for DNS propagation
- Check domain verification status
- Contact support for domain troubleshooting

[See DNS configuration guide →](/link-shortening/dns-configuration)

## Security Considerations

### Link Expiration
- Set expiration dates for time-sensitive links
- Configure redirect URLs for expired links
- Automatically deactivate after campaign ends

### Password Protection
- Protect pre-launch links from public access
- Require password for sensitive content
- Share password securely with intended audience

### Click Limits
- Prevent abuse with maximum click thresholds
- Useful for limited offers
- Stops tracking after limit reached

[Learn about link security features →](/links/password-protected)

## Comparing Shortener Options

| Feature | Custom Branded | Default Shortener | No Shortening |
|---------|---------------|-------------------|---------------|
| Setup Required | Yes (DNS config) | No | No |
| Brand Control | Full | Limited | Full URL visible |
| Trust Factor | High | Medium | Varies |
| Cost | Domain cost | Included | Free |
| Best For | External campaigns | Testing, internal | Email, transparency |
| Custom Domain | Your domain | Shared | N/A |
| Analytics | Full | Full | Full |

## Integration with Other Features

### QR Codes
- Generate QR codes for short links
- Perfect for offline marketing
- Shorter URLs create simpler QR patterns
- [Learn about QR codes →](/links/qr-codes)

### Templates
- Include shortener settings in templates
- Automatically apply to new links
- Consistent shortening across campaigns
- [Learn about templates →](/utm-templates/create-template)

### UTM Rules
- Set default shortener at project level
- Enforce shortening for specific campaigns
- Standardize link formats
- [Learn about UTM rules →](/utm-rules/project-rules)

## Advanced Features

### Domain Rotation
- Use multiple custom domains
- Distribute links across domains
- Reduce dependency on single domain
- Better for high-volume campaigns

### Link Aliases
- Create multiple short codes for same destination
- A/B test different short URLs
- Platform-specific short links

### Redirect Types
- 301 (Permanent redirect)
- 302 (Temporary redirect)
- 307 (Temporary redirect, preserve method)

## Related Documentation

- [Custom Domains Setup](/link-shortening/custom-domains)
- [DNS Configuration](/link-shortening/dns-configuration)
- [Link Analytics](/analytics/link-analytics)
- [QR Code Generation](/links/qr-codes)
- [Link Security](/links/password-protected)

## Need Help?

For assistance with link shortening or custom domain setup, please contact our support team.
