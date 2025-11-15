# Link Shortening Overview

Learn how LinkUTM's link shortening feature helps you create clean, professional, trackable URLs.

## What is Link Shortening?

Link shortening converts long URLs with UTM parameters into short, memorable links that are easier to share and track. LinkUTM provides built-in link shortening with support for custom branded domains.

## Why Use Link Shortening?

### Benefits

**Professional Appearance**
- Clean, branded URLs
- Builds trust with your audience
- Reinforces brand identity
- Better for marketing materials

**Easier Sharing**
- Fits character limits (Twitter, SMS)
- Easier to type and remember
- Better for print materials
- Cleaner in presentations

**Better Click-Through Rates**
- Short links appear more trustworthy
- Less intimidating than long parameter URLs
- Mobile-friendly
- Improved user experience

**Full Tracking**
- All UTM parameters preserved
- Complete analytics tracking
- Link performance metrics
- Geographic and device data

## How It Works

### The Process

1. **Create Link with UTM Parameters**
   ```
   Original: https://yoursite.com/product?utm_source=facebook&utm_medium=cpc&utm_campaign=summer_sale&utm_content=ad1
   ```

2. **Enable Link Shortening**
   - Select your shortener service
   - Short code generated automatically

3. **Get Short Link**
   ```
   Shortened: https://yourbrand.link/abc123
   ```

4. **User Clicks**
   - User clicks short link
   - Redirects to original URL with all UTM parameters
   - All tracking data captured

5. **View Analytics**
   - Track clicks, visitors, conversions
   - Geographic and device data
   - Full campaign attribution

## Shortener Options

### Custom Branded Domains

Use your own domain for link shortening:

**Examples:**
- `go.yourcompany.com/abc123`
- `link.yourbrand.io/summer`
- `track.yoursite.com/promo`

**Advantages:**
- Full brand control
- Maximum trust
- Professional appearance
- Custom domain ownership

**Setup Required:**
- Own a domain
- Configure DNS records
- Verify domain ownership

[Learn how to set up custom domains →](/link-shortening/custom-domains)

### Default Project Shortener

Use the shortener configured at project level:

**Advantages:**
- No setup required
- Instant availability
- Consistent across project
- Shared across team

**Best For:**
- Quick testing
- Internal links
- Getting started
- Small campaigns

### No Shortening

Keep the full URL visible:

**When to Use:**
- Email marketing (some filters flag shortened URLs)
- Transparency required
- Partners need full URL visibility
- Internal documentation

## Setting Up Link Shortening

### Quick Start

1. Navigate to **Link Shortening** in settings or sidebar
2. Add your custom domain OR use default
3. Configure DNS (for custom domains)
4. Verify domain
5. Set as default (optional)
6. Start creating short links

### Configuration Options

**Domain Settings:**
- Domain name
- Protocol (HTTP/HTTPS)
- Default domain toggle
- Active/inactive status

**DNS Configuration:**
- A Record or CNAME
- Target server address
- TTL settings
- Verification

[Learn about DNS configuration →](/link-shortening/dns-configuration)

## Managing Short Links

### View Short Links

- All links display short URL if enabled
- Copy short link to clipboard
- QR code generation
- Link performance tracking

### Edit Short Links

- Change destination URL (redirect updates)
- Update UTM parameters
- Change shortener service
- Short code remains permanent

### Deactivate Short Links

- Disable link shortening
- Short URL becomes inactive
- Return to full URL
- Or redirect to different page

## Short Link Analytics

Track complete performance:

**Metrics:**
- Total clicks
- Unique visitors
- Click timeline
- Geographic distribution
- Device breakdown (mobile, desktop, tablet)
- Browser information
- Referrer sources

**Insights:**
- Best-performing channels
- Peak traffic times
- Audience locations
- Device preferences

[Learn more about analytics →](/analytics/link-analytics)

## Best Practices

### Domain Selection

**Custom Branded Domain:**
- ✅ Use for customer-facing campaigns
- ✅ Use for social media
- ✅ Use for print materials
- ✅ Builds brand trust

**Default Shortener:**
- ✅ Use for internal sharing
- ✅ Use for testing
- ✅ Use for draft campaigns
- ✅ Quick setup needed

### Security Considerations

**Link Protection:**
- Use password protection for sensitive links
- Set expiration dates for time-limited offers
- Enable click limits for exclusive content
- Monitor for suspicious activity

**Domain Security:**
- Use HTTPS for custom domains
- Keep DNS records secure
- Monitor domain health
- Renew domain regularly

### Link Management

**Organization:**
- Use folders to organize short links
- Tag by campaign or platform
- Document link purposes
- Regular cleanup of expired links

**Testing:**
- Test short links before sharing
- Verify redirect works correctly
- Check on multiple devices
- Ensure analytics tracking

## Advanced Features

### Custom Short Codes

Create memorable short codes:
- `https://brand.link/summer-sale`
- `https://brand.link/signup`
- `https://brand.link/special-offer`

**Benefits:**
- Easier to remember
- Better for verbal sharing
- Professional appearance
- Brand-specific

### Link Aliases

Multiple short URLs for same destination:
- A/B test different short URLs
- Platform-specific links
- Campaign variations
- Geographic routing

### Domain Rotation

Use multiple custom domains:
- Distribute links across domains
- Reduce single domain dependency
- Better for high-volume campaigns
- Risk mitigation

## Integration with Other Features

### Short Links + QR Codes

Generate QR codes from short links:
- Simpler QR pattern
- Easier to scan
- More reliable
- Better for print

[Learn about QR codes →](/links/qr-codes)

### Short Links + UTM Parameters

Full tracking with clean URLs:
- All UTM parameters preserved
- Clean appearance
- Complete analytics
- Campaign attribution

[Learn about UTM parameters →](/utm-parameters/overview)

### Short Links + Templates

Template-based shortening:
- Include shortener in templates
- Automatic short link creation
- Consistent link format
- Team standardization

[Learn about templates →](/utm-templates/overview)

## Troubleshooting

### Short Link Not Working

**Possible Issues:**
- DNS not configured correctly
- Domain not verified
- Link expired
- Click limit reached

**Solutions:**
- Check DNS configuration
- Verify domain status
- Check link settings
- Review analytics for issues

### Custom Domain Not Resolving

**Solutions:**
- Verify DNS records are correct
- Allow 24-48 hours for propagation
- Check domain registrar settings
- Use DNS checker tools
- Contact support

### Analytics Not Tracking

**Solutions:**
- Verify tracking is enabled
- Check analytics integration
- Wait for data sync (a few minutes)
- Test with different link

## Comparing Options

| Feature | Custom Domain | Default Shortener | No Shortening |
|---------|--------------|-------------------|---------------|
| Brand Control | Full | Limited | Full URL visible |
| Setup Required | Yes (DNS) | No | No |
| Trust Factor | High | Medium | Varies |
| Cost | Domain cost | Included | Free |
| Best For | External campaigns | Testing, internal | Email, transparency |
| Analytics | Full | Full | Full |
| Customization | High | Low | N/A |

## Related Documentation

- [Custom Domains Setup](/link-shortening/custom-domains)
- [DNS Configuration](/link-shortening/dns-configuration)
- [Short Links](/links/short-link)
- [QR Codes](/links/qr-codes)
- [Link Analytics](/analytics/link-analytics)

## Need Help?

For questions about link shortening or custom domain setup, contact our support team.
