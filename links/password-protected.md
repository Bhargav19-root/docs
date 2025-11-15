# Password Protected Links

Learn how to secure your links with password protection in LinkUTM.

## Overview

Password protection adds an extra layer of security to your links by requiring users to enter a password before accessing the destination URL. This feature is perfect for protecting pre-launch campaigns, internal resources, confidential content, or limiting access to specific audiences.

## Why Use Password Protection?

### Common Use Cases

**Pre-Launch Campaigns**
- Protect campaign links before official launch
- Allow team review without public access
- Prevent accidental early sharing

**Internal Resources**
- Secure employee-only content
- Protect internal documentation
- Restrict team-specific materials

**Client Previews**
- Share work-in-progress with clients
- Secure approval process
- Controlled access to drafts

**Exclusive Content**
- VIP access for special customers
- Premium member content
- Invite-only events or resources

**Testing & QA**
- Secure test links from public
- Control who accesses staging environments
- Limit exposure during testing phase

**Limited Audience Campaigns**
- Partner-exclusive offers
- Employee benefits
- Restricted promotions

## Setting Up Password Protection

### During Link Creation

1. Create a new link or edit existing link
2. Scroll to **Advanced Settings** or **Security Settings**
3. Toggle **Password Protection** ON
4. Configure password options:
   - **Auto-generate**: Let system create secure password
   - **Custom password**: Enter your own password
5. Save your link

### For Existing Links

1. Navigate to your **Links** page
2. Find the link to protect
3. Click **Edit**
4. Enable **Password Protection**
5. Set or generate password
6. Save changes

## Password Options

### Auto-Generated Passwords

**Benefits:**
- Cryptographically secure
- Hard to guess
- Unique for each link
- Immediate availability

**Example:** `K7mP9xN2qR5t`

**Best for:**
- Maximum security
- Short-term access
- One-time use scenarios

### Custom Passwords

**Benefits:**
- Easy to remember
- Easy to share verbally
- Can be thematic or branded
- User-friendly

**Example:** `SummerSale2024`

**Best for:**
- Team sharing
- Extended access periods
- Easy recall needed

**Tips for Custom Passwords:**
- Use combination of letters and numbers
- Avoid common words
- Make it memorable but not obvious
- Consider your audience's technical level

## How Password Protection Works

### User Experience

1. **User clicks your link**
2. **Password prompt appears** with your branding
3. **User enters password**
4. **If correct**: Redirected to destination URL
5. **If incorrect**: Error message, try again option

### Password Entry Page

The password page includes:
- Your project/brand name (if configured)
- Password input field
- Submit button
- Optional custom message or instructions
- Secure, branded interface

### Session Handling

**After Successful Entry:**
- User is redirected immediately
- (Optional) Session cookie may be set
- Future clicks may not require re-entry (depending on configuration)

**Failed Attempts:**
- Clear error messaging
- Option to try again
- (Optional) Rate limiting after multiple failures

## Managing Password-Protected Links

### Viewing Protected Links

On your links page, password-protected links are indicated by:
- 🔒 Lock icon
- "Password Protected" badge or label
- Special indicator in link details

### Copying Password-Protected Links

1. Find your protected link
2. Click **Copy Link**
3. Share link AND password separately (recommended)

**Security Tip:** Send the link and password through different channels (e.g., link via email, password via Slack or SMS).

### Sharing Passwords Securely

**Best Practices:**
- Use different communication channels
- Share password verbally when possible
- Use temporary passwords
- Change passwords periodically
- Limit password distribution

**Example Workflow:**
```
1. Email link: "Here's the preview link: https://brand.link/abc123"
2. Slack message: "Password for the preview: K7mP9x"
3. After review period: Change or remove password
```

### Changing Passwords

1. Edit the protected link
2. In **Password Protection** settings
3. Choose **Generate New** or enter new custom password
4. Save changes
5. Notify users of password change

**When to Change:**
- After review period ends
- If password may be compromised
- When access group changes
- Regularly for long-term links

### Removing Password Protection

1. Edit the link
2. Toggle **Password Protection** OFF
3. Save changes
4. Link is now publicly accessible

**Use Case:** After campaign launches or when content becomes public.

## Advanced Password Features

### Password Expiration (If Available)

Set passwords to expire automatically:
- After specific date/time
- After certain number of uses
- Combined with link expiration

**Example:** Preview link password expires on launch date.

### Multiple Passwords (If Available)

Create different passwords for different user groups:
- Team A: password1
- Clients: password2
- VIPs: password3

**Benefits:**
- Track which group accessed
- Revoke access by group
- Different access levels

### Password Strength Requirements

Enforce strong custom passwords:
- Minimum 8 characters
- Mix of letters and numbers
- Special characters (optional)
- No common passwords

## Combining with Other Security Features

### Password + Link Expiration

**Ultimate Time-Limited Security:**
1. Enable password protection
2. Set expiration date/time
3. Link automatically becomes inactive after date
4. Perfect for time-sensitive previews

**Example:**
```
Pre-launch landing page
- Password: team2024
- Expires: Launch date at 9 AM
- After expiration: Redirects to public site
```

[Learn about link expiration →](/links/link-expiration)

### Password + Click Limits

**Limited Access Control:**
1. Enable password protection
2. Set maximum click limit
3. Link stops working after X clicks
4. Useful for exclusive content

**Example:**
```
VIP offer link
- Password: vip500
- Click limit: 500
- After 500 clicks: Link inactive
```

[Learn about click limits →](/links/click-limits)

### Password + Device Targeting

**Device-Specific Security:**
1. Enable password protection
2. Set device-specific URLs
3. Different destinations for iOS/Android
4. Same password for all devices

**Example:**
```
App download link
- iOS: App Store with password
- Android: Google Play with password
- Web: Landing page with password
```

[Learn about device targeting →](/links/device-targeting)

## Real-World Examples

### Example 1: Pre-Launch Campaign

```
Scenario: New product launching in 2 weeks

Link Setup:
- Destination: https://brand.com/new-product-landing
- Password Protection: ON
- Password: PreviewTeam24 (shared with team and stakeholders)
- Expiration: Launch date
- After expiration: Redirect to public landing page

Workflow:
1. Week 1-2: Team reviews with password
2. Launch day: Password auto-disabled
3. Public can access freely
```

### Example 2: Client Approval Process

```
Scenario: Agency needs client approval on campaign

Link Setup:
- Destination: https://client-campaign.example.com
- Password Protection: ON
- Password: ClientA_Review (auto-generated, secure)
- Folder: Client A - Pending Approval
- Tag: Yellow (Needs Review)
- Notes: "Sent to client for approval on May 1"

Workflow:
1. Create link with password
2. Email link to client
3. Text password separately
4. Client reviews and approves
5. Remove password and launch campaign
```

### Example 3: Internal Training Materials

```
Scenario: Employee training resources

Link Setup:
- Destination: https://company.com/training/module1
- Password Protection: ON
- Password: EmployeeTraining2024
- Click Limit: None (unlimited for employees)
- Expiration: End of training period

Workflow:
1. Share link and password in employee handbook
2. Employees access as needed
3. After training period: Archive or remove
```

### Example 4: Partner Exclusive Offer

```
Scenario: Special offer for business partners only

Link Setup:
- Destination: https://store.com/partner-discount
- Password Protection: ON
- Password: PartnerDeal2024
- Expiration: End of quarter
- Click Limit: 100 (estimated partner count)

Workflow:
1. Share link at partner event
2. Password announced verbally
3. Limited to 100 uses
4. Expires end of quarter
```

### Example 5: Event Registration (VIP)

```
Scenario: VIP early registration for conference

Link Setup:
- Destination: https://events.com/conference-2024/register
- Password Protection: ON
- Password: VIP_Early_Access
- Expiration: 48 hours before public registration
- After expiration: Remove password for public access
- Click Limit: 200 VIP invites

Workflow:
1. Email VIP list with exclusive link
2. 48-hour early access window
3. After 48 hours: Public registration opens (no password)
```

## Best Practices

### Security

✅ **Do:**
- Use strong, unique passwords
- Share link and password separately
- Change passwords periodically
- Remove protection when no longer needed
- Use auto-generated passwords for high security

❌ **Avoid:**
- Using obvious passwords (password123, company name)
- Sharing link and password in same message
- Reusing passwords across multiple links
- Leaving protection enabled indefinitely
- Posting passwords publicly

### Communication

**When Sharing Protected Links:**

1. **Clear Instructions**
   ```
   Subject: Campaign Preview Link

   Please find the preview link below. Password will be sent separately.

   Link: https://brand.link/campaign-preview
   ```

2. **Separate Password**
   ```
   Subject: Password for Campaign Preview

   Password: PreviewTeam24

   Please keep this confidential.
   ```

3. **Provide Context**
   - Explain why password is needed
   - Specify who should have access
   - Include expiration information
   - Offer support contact

### Management

**Regular Review:**
- Audit password-protected links monthly
- Remove protection from outdated links
- Update passwords for long-term links
- Document password changes

**Team Coordination:**
- Centralized password management
- Clear ownership of protected links
- Document who has access
- [Use team features](/team-collaboration/overview) for accountability

## Troubleshooting

### User Can't Access Link

**Problem:** Password isn't working

**Possible Causes & Solutions:**

1. **Incorrect Password**
   - Verify password is correct (case-sensitive)
   - Check for extra spaces
   - Confirm you're sharing latest password

2. **Link Expired**
   - Check expiration settings
   - Extend expiration if needed
   - Create new link if expired

3. **Click Limit Reached**
   - Check click count
   - Increase or remove limit
   - Create new link if needed

4. **Browser Issues**
   - Try incognito/private mode
   - Clear browser cache
   - Try different browser

### Password Not Saving

**Problem:** Password protection doesn't activate

**Solutions:**
- Ensure you clicked "Save" after enabling
- Refresh the link list
- Check for error messages
- Verify you have permission to set passwords
- Try regenerating password

### Lost Password

**Problem:** Forgot the password for a link

**Solutions:**
- Edit the link to view password (if allowed)
- Generate new password
- Check team notes or documentation
- Contact link creator (if team member)

## Analytics for Protected Links

Track password-protected link performance:

- **Access attempts**: How many tried to access
- **Successful entries**: How many entered correct password
- **Failed attempts**: Blocked incorrect entries
- **Standard metrics**: Clicks, visitors, geographic data

**Insights:**
- How many people have the password
- If password is being shared widely
- User engagement with protected content

[Learn more about analytics →](/analytics/link-analytics)

## Related Documentation

- [Link Expiration](/links/link-expiration)
- [Click Limits](/links/click-limits)
- [Link Security Best Practices](/advanced-features/security)
- [Team Collaboration](/team-collaboration/overview)
- [Creating Links](/links/create-link)

## Need Help?

For questions about password protection or link security, contact our support team.
