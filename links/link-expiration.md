# Link Expiration

Learn how to set automatic expiration dates for your links in linkutm.

## Overview

Link expiration allows you to automatically deactivate links after a specific date and time. This feature is perfect for time-sensitive campaigns, limited offers, event registrations, and any scenario where you need links to stop working after a certain period.

## Why Use Link Expiration?

### Common Use Cases

**Limited-Time Offers**
- Flash sales with specific end times
- Early bird pricing deadlines
- Seasonal promotions
- Weekend-only deals

**Event Management**
- Registration deadlines
- RSVP cut-off dates
- Ticket sales end dates
- Pre-event access windows

**Content Control**
- Temporary access to resources
- Beta testing periods
- Preview content windows
- Embargo releases

**Campaign Management**
- Quarter-end campaigns
- Monthly promotions
- Holiday marketing
- Timed product launches

**Security & Compliance**
- Sensitive information expiration
- Temporary partner access
- Limited review periods
- Compliance requirements

## Setting Up Link Expiration

### During Link Creation

1. Create or edit a link
2. Find **Advanced Settings** or **Link Expiration** section
3. Toggle **Set Expiration** ON
4. Configure expiration settings:
   - **Expiration Date**: Select end date
   - **Expiration Time**: Set specific time
   - **Timezone**: Confirm timezone
   - **Redirect URL**: (Optional) Where to send users after expiration
5. Save your link

### For Existing Links

1. Navigate to **Links** page
2. Find the link
3. Click **Edit**
4. Enable **Link Expiration**
5. Set date, time, and redirect
6. Save changes

## Expiration Settings

### Date and Time

**Selecting Date:**
- Use date picker for convenience
- Can set expiration days, weeks, or months ahead
- Consider your campaign timeline

**Setting Time:**
- Specify exact hour and minute
- Use 24-hour or 12-hour format
- Set to campaign end time (e.g., 11:59 PM for "today only" offers)

**Timezone Considerations:**
- Verify timezone setting
- Match your target audience's timezone
- Common choice: Your business timezone
- For global campaigns: Consider UTC

**Examples:**
```
Flash Sale ending tonight:
Date: June 15, 2024
Time: 11:59 PM
Timezone: EST

Webinar registration closes:
Date: July 1, 2024
Time: 2:00 PM
Timezone: PST

Event ticket sales end:
Date: September 30, 2024
Time: 11:59 PM
Timezone: Local business timezone
```

### Redirect URL (After Expiration)

When link expires, redirect users to a specified URL instead of showing an error.

**Why Use Redirects:**
- Better user experience
- Maintain brand image
- Offer alternatives
- Provide context about expiration

**Redirect URL Options:**

**1. Homepage**
```
Redirect to: https://yoursite.com
Use for: General expired links
```

**2. Similar Offer Page**
```
Redirect to: https://yoursite.com/current-promotions
Use for: Expired sales, show current offers
```

**3. "Campaign Ended" Page**
```
Redirect to: https://yoursite.com/sale-ended
Use for: Specific explanation, email signup for future offers
```

**4. Product Page**
```
Redirect to: https://yoursite.com/products
Use for: Expired promo, still show products at regular price
```

**5. Waitlist or Notification Page**
```
Redirect to: https://yoursite.com/notify-me
Use for: Sold out or ended, capture interest for next time
```

### No Redirect (Error Page)

If no redirect URL is set:
- Users see default expiration message
- "This link has expired" or similar
- May include your branding
- Less ideal user experience

**When to use:**
- Testing purposes
- Internal links
- When no alternative exists

## Managing Expired Links

### Viewing Expiration Status

On your links page, see expiration information:
- ⏰ **Expiration indicator**: Icon or badge
- **Expiring soon**: Warning for links expiring within 24-48 hours
- **Expired**: Clear indicator for expired links
- **Days remaining**: Countdown to expiration

### Extending Expiration

Need more time? Extend the expiration date:

1. Edit the expired or soon-to-expire link
2. Change expiration date to new date
3. Optionally update time
4. Save changes
5. Link becomes active again (if it was expired)

**Use Cases:**
- Campaign performing well, extend duration
- Event postponed
- Deadline extended
- Testing period needs more time

### Removing Expiration

Make a temporary link permanent:

1. Edit the link
2. Toggle **Link Expiration** OFF
3. Save changes
4. Link no longer has expiration

**Use Cases:**
- Evergreen content
- Ongoing campaigns
- Permanent resources
- No longer time-sensitive

### Reactivating Expired Links

**Option 1: Extend Date**
- Edit link
- Set new future expiration date
- Link reactivates immediately

**Option 2: Remove Expiration**
- Edit link
- Disable expiration
- Link becomes permanent

**Option 3: Duplicate**
- Duplicate expired link
- Set new expiration date
- Keeps old link archived

## Link Expiration + Other Features

### Expiration + Password Protection

**Double Security:**
1. Require password to access
2. Automatically expire after date
3. Perfect for pre-launch + time-limited access

**Example:**
```
Beta testing link
- Password: BetaTester2024
- Expires: End of beta period
- Redirect: Public product page

Workflow:
1. Beta testers access with password
2. Beta ends automatically on date
3. Public redirected to launch page
```

[Learn about password protection →](/links/password-protected)

### Expiration + Click Limits

**Dual Limiting:**
1. Link expires on date OR after X clicks
2. Whichever comes first
3. Great for limited inventory

**Example:**
```
Limited offer link
- Click Limit: 500 (inventory count)
- Expiration: End of month
- Redirect: Waitlist page

Result: Stops at 500 clicks or month end
```

[Learn about click limits →](/links/click-limits)

### Expiration + Link Shortening

**Professional Time-Limited Links:**
1. Create short, branded link
2. Set expiration
3. Share easy-to-remember URL
4. Auto-deactivates on schedule

**Example:**
```
Flash sale short link
- Short URL: https://brand.link/flash24
- Expires: Tonight at midnight
- Redirect: Tomorrow's sale page
```

[Learn about link shortening →](/links/short-link)

### Expiration + QR Codes

**Time-Limited QR Codes:**
1. Generate QR code for link
2. Set expiration
3. Use in print/offline marketing
4. QR becomes inactive automatically

**Example:**
```
Event QR code on flyers
- Expires: Day before event
- Redirect: Event info page (non-registration)

Prevents late registrations automatically
```

[Learn about QR codes →](/links/qr-codes)

## Real-World Examples

### Example 1: 24-Hour Flash Sale

```
Campaign: Flash sale ending tonight

Link Setup:
- Destination: https://shop.example.com/flash-sale
- Expiration Date: Today
- Expiration Time: 11:59 PM EST
- Redirect URL: https://shop.example.com/new-arrivals
- Short Link: https://brand.link/flash24
- Tag: Red (Urgent)

Customer Experience:
- Before 11:59 PM: Access flash sale page
- After 11:59 PM: Redirected to new arrivals
- Clear, automated cutoff
```

### Example 2: Webinar Registration

```
Campaign: Live webinar on May 15

Link Setup:
- Destination: https://events.example.com/webinar-signup
- Expiration Date: May 15, 2024
- Expiration Time: 2:00 PM EST (webinar start time)
- Redirect URL: https://events.example.com/webinar-replay-waitlist
- Password: EarlyBird (for VIP early access)
- Remove password: 7 days before
- Tag: Purple (Event)

Customer Experience:
- VIPs: Early registration with password
- Public: Registration opens 7 days before
- Registration closes at webinar start
- Late arrivals: Join replay waitlist
```

### Example 3: Seasonal Campaign

```
Campaign: Summer sale (June-August)

Link Setup:
- Destination: https://shop.example.com/summer-collection
- Expiration Date: August 31, 2024
- Expiration Time: 11:59 PM PST
- Redirect URL: https://shop.example.com/fall-collection
- Folder: Summer 2024
- Tag: Purple (Seasonal)

Workflow:
- Summer: Active summer collection sale
- September 1: Automatically switches to fall collection
- Seamless seasonal transition
```

### Example 4: Early Bird Tickets

```
Campaign: Conference early bird pricing

Link Setup:
- Destination: https://conference.example.com/register?tier=early-bird
- Expiration Date: March 31, 2024
- Expiration Time: 11:59 PM
- Redirect URL: https://conference.example.com/register?tier=regular
- Click Limit: 500 (early bird capacity)
- Tag: Green (Active)

Result:
- First 500 registrants OR March 31 deadline
- Automatic switch to regular pricing
- No manual intervention needed
```

### Example 5: Product Launch Preview

```
Campaign: New product pre-launch access

Link Setup:
- Destination: https://brand.example.com/new-product-preview
- Password: LaunchTeam2024
- Expiration Date: Launch day
- Expiration Time: 9:00 AM
- Redirect URL: https://brand.example.com/new-product (public)
- Tag: Blue (Product Launch)

Workflow:
- Pre-launch: Team and stakeholders preview with password
- Launch day 9 AM: Password requirement removed, link expires
- Public redirected to live product page
```

## Best Practices

### Timing Strategy

**Give Appropriate Notice:**
- ✅ Announce expiration clearly in marketing
- ✅ Send reminders as deadline approaches
- ✅ Consider timezone of target audience
- ✅ Set time to end of business day when appropriate

**Avoid:**
- ❌ Surprise expirations without warning
- ❌ Confusing timezone mismatches
- ❌ Expiring during peak traffic times (unless intentional)

### Redirect Planning

**Always Provide a Redirect:**
- ✅ Never leave users at error page
- ✅ Offer relevant alternative
- ✅ Maintain brand experience
- ✅ Consider next logical step

**Redirect Destination Ideas:**
- Similar current offer
- Product catalog
- Email signup for next promotion
- Company homepage
- "Thank you for your interest" page

### Communication

**Tell Users About Expiration:**
- Display countdown on landing page
- Include in link text/copy ("Ends midnight tonight!")
- Email reminders before expiration
- Social media updates

**Example Messaging:**
```
Email: "Last Chance! Sale ends tonight at midnight"
Social: "⏰ 6 hours left! Get 50% off: [link]"
Landing Page: Banner with countdown timer
```

### Testing

**Before Launch:**
- ✅ Verify expiration date and time are correct
- ✅ Double-check timezone setting
- ✅ Test redirect URL works
- ✅ Confirm expiration actually triggers
- ✅ Test from user perspective

**During Campaign:**
- Monitor performance
- Check analytics
- Be ready to extend if needed
- Watch for support questions

### Link Organization

**Track Expiring Links:**
- Use folders for time-based campaigns
- Tag with expiration info
- Regular review of upcoming expirations
- Calendar reminders for key expirations

## Troubleshooting

### Link Expired Too Early/Late

**Problem:** Link expired at wrong time

**Possible Causes:**
- Incorrect timezone setting
- Wrong date/time entered
- System clock discrepancy

**Prevention:**
- Always verify timezone
- Use 24-hour format to avoid AM/PM confusion
- Test with near-future expiration first
- Set expiration with buffer time

### Redirect Not Working

**Problem:** Expired link shows error instead of redirecting

**Solutions:**
- Verify redirect URL is correct and accessible
- Check for typos in redirect URL
- Ensure redirect URL includes https://
- Test redirect URL independently
- Save changes after editing

### Need to Extend Expired Link

**Problem:** Link already expired, need to reactivate

**Solution:**
- Edit the link
- Set new future expiration date
- Or remove expiration entirely
- Save and test
- Link reactivates immediately

### Users Reporting Link Doesn't Work

**Problem:** Link expired but campaign is still running

**Solutions:**
- Check expiration date/time setting
- Extend expiration if needed
- Verify timezone is correct
- Update marketing materials if expiration changed
- Send update to users if necessary

## Analytics for Expired Links

### Tracking Performance

**Metrics to Review:**
- Total clicks before expiration
- Clicks by day (see if urgency drove end-of-campaign spike)
- Conversions within expiration window
- Redirect clicks after expiration

**Insights:**
- Did urgency create last-minute rush?
- Should expiration window be longer/shorter?
- How many tried to access after expiration?
- Effectiveness of redirect destination

[Learn more about analytics →](/analytics/link-analytics)

### Post-Campaign Analysis

After link expires:
- Review full campaign performance
- Compare to similar campaigns
- Analyze timing effectiveness
- Optimize for future time-limited campaigns

## Related Documentation

- [Password Protection](/links/password-protected)
- [Click Limits](/links/click-limits)
- [Link Shortening](/links/short-link)
- [QR Codes](/links/qr-codes)
- [Creating Links](/links/create-link)
- [Link Analytics](/analytics/link-analytics)

## Need Help?

For questions about link expiration or time-limited campaigns, contact our support team.
