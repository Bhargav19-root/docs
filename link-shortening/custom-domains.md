# Custom Domains for Link Shortening

Learn how to set up and manage custom branded domains for link shortening in linkutm.

## Overview

Custom branded domains allow you to use your own domain (e.g., `go.yourbrand.com`, `link.yourcompany.io`) for link shortening instead of a generic shortening service. This builds trust, reinforces your brand, and provides full control over your short links.

## Why Use Custom Domains?

### Benefits

**Brand Trust**
- Users recognize your domain
- Appears more trustworthy
- Reduces link hesitation
- Professional appearance

**Brand Consistency**
- Reinforces brand at every touchpoint
- Consistent with your other properties
- Custom branding in all campaigns
- Memorable links

**Full Control**
- Own your domain
- Control DNS settings
- No dependency on third-party services
- Permanent ownership

**Better Analytics**
- All data stays with you
- Complete tracking control
- Integration flexibility
- Historical data preservation

**Customization**
- Custom short codes
- Branded appearance
- Flexible configuration
- Your rules

## Prerequisites

### What You Need

**1. Domain Ownership**
- Own a domain (or subdomain)
- Access to domain registrar
- Ability to modify DNS records

**2. Domain Options**

**Use a Subdomain (Recommended):**
- `go.yourcompany.com`
- `link.yourbrand.io`
- `track.yoursite.com`
- `get.yourproduct.com`

**Use a Separate Domain:**
- `yourbrand.link`
- `yourcompany.click`
- `getproduct.io`

**Why Subdomain is Recommended:**
- Keeps main domain separate
- Easier DNS management
- Less risk to main domain
- More flexible

### Domain Registrars

Works with all major registrars:
- GoDaddy
- Namecheap
- Google Domains
- Cloudflare
- AWS Route 53
- Name.com
- And others

## Setting Up Custom Domain

### Step 1: Choose Your Domain

**Decision Points:**

**Subdomain vs. Root Domain:**
- ✅ Subdomain: `go.yourbrand.com` (recommended)
- ⚠️ Root Domain: `yourbrand.link` (requires full domain)

**Subdomain Suggestions:**
- `go.` - Common, intuitive
- `link.` - Clear purpose
- `track.` - Obvious tracking
- `get.` - Action-oriented
- `l.` - Very short (e.g., `l.yourbrand.com`)

**Keep it Short:**
- Shorter is better
- Easy to type
- Memorable
- Professional

### Step 2: Add Domain to linkutm

1. **Navigate to Link Shortening Settings:**
   - Go to **Dashboard** → **Link Shortening**
   - Or **Settings** → **Link Shortening**

2. **Add New Domain:**
   - Click **Add Custom Domain** or **+ New Domain**
   - Enter your domain (e.g., `go.yourbrand.com`)
   - Click **Add** or **Save**

3. **View DNS Instructions:**
   - System displays required DNS records
   - Copy DNS configuration details
   - Keep this page open for reference

### Step 3: Configure DNS Records

**What You'll Configure:**

**Option A: CNAME Record (Recommended for Subdomains)**
```
Type: CNAME
Host/Name: go (or your chosen subdomain)
Value/Points to: [linkutm provides this - e.g., links.linkutm.io]
TTL: 3600 (or automatic)
```

**Option B: A Record (For Root Domains)**
```
Type: A
Host/Name: @ (or leave blank)
Value/IP Address: [linkutm provides this - e.g., 192.0.2.1]
TTL: 3600 (or automatic)
```

### Step 4: Add DNS Record at Your Registrar

**General Steps (varies by registrar):**

1. **Log into Domain Registrar:**
   - GoDaddy, Namecheap, Cloudflare, etc.

2. **Find DNS Management:**
   - Look for "DNS Settings", "DNS Management", or "Domain Settings"
   - May be under "Advanced Settings"

3. **Add New Record:**
   - Click "Add Record" or "Add DNS Record"
   - Select record type (CNAME or A)
   - Fill in details from linkutm

4. **Save DNS Record:**
   - Click "Save", "Add", or "Update"
   - Record is now configured

### Step 5: Verify Domain

**Back in linkutm:**

1. **Wait for DNS Propagation:**
   - Usually 5-15 minutes
   - Can take up to 48 hours (rare)
   - Most complete within 1 hour

2. **Verify Domain:**
   - Click **Verify** or **Check DNS** button
   - System checks DNS configuration
   - Shows verification status

3. **Status Indicators:**
   - ✅ **Verified**: Domain is ready to use
   - ⏳ **Pending**: DNS propagating, check again soon
   - ❌ **Failed**: DNS configuration issue

### Step 6: Set as Default (Optional)

Make this domain your default shortener:

1. Find domain in list
2. Click **Set as Default** or toggle default option
3. All new links use this domain automatically
4. Can override per-link if needed

## DNS Configuration by Registrar

### GoDaddy

1. Log into GoDaddy account
2. Go to **My Products** → **Domains**
3. Click on domain
4. Click **DNS** or **Manage DNS**
5. Scroll to **Records** section
6. Click **Add** button
7. Select **CNAME** type
8. Enter **Host**: `go` (your subdomain)
9. Enter **Points to**: (from linkutm)
10. TTL: Default or 1 Hour
11. Click **Save**

### Namecheap

1. Log into Namecheap
2. Go to **Domain List**
3. Click **Manage** next to domain
4. Click **Advanced DNS** tab
5. Click **Add New Record**
6. Type: **CNAME Record**
7. Host: `go` (your subdomain)
8. Value: (from linkutm)
9. TTL: Automatic
10. Click ✓ to save

### Cloudflare

1. Log into Cloudflare
2. Select your domain
3. Click **DNS** in menu
4. Click **Add record**
5. Type: **CNAME**
6. Name: `go` (your subdomain)
7. Target: (from linkutm)
8. Proxy status: DNS only (gray cloud) - Important!
9. Click **Save**

**Important for Cloudflare:** Disable proxy (use DNS only, gray cloud) for the shortening subdomain.

### Google Domains

1. Log into Google Domains
2. Click on your domain
3. Click **DNS** in left menu
4. Scroll to **Custom resource records**
5. Name: `go` (your subdomain)
6. Type: **CNAME**
7. TTL: 1H
8. Data: (from linkutm)
9. Click **Add**

### AWS Route 53

1. Open Route 53 console
2. Click **Hosted zones**
3. Select your domain
4. Click **Create record**
5. Record name: `go` (your subdomain)
6. Record type: **CNAME**
7. Value: (from linkutm)
8. TTL: 300
9. Routing policy: Simple
10. Click **Create records**

## SSL/HTTPS Configuration

### Automatic SSL

**linkutm handles SSL:**
- Automatic SSL certificate generation
- HTTPS enabled by default
- No additional configuration needed
- Certificates auto-renew

### Verification

Check SSL is working:
1. Wait 24-48 hours after DNS verification
2. Visit `https://go.yourbrand.com` in browser
3. Should show secure padlock icon
4. Certificate should be valid

## Managing Custom Domains

### View Domains

**Domain List Shows:**
- Domain name
- Status (Active, Pending, Inactive)
- Default indicator
- Verification status
- Links created count
- Date added

### Edit Domain

**What You Can Change:**
- Active/inactive status
- Default domain setting
- Notes or description

**What You Cannot Change:**
- Domain name itself (delete and re-add instead)
- DNS records (change at registrar)

### Set Default Domain

1. Go to Link Shortening settings
2. Find domain in list
3. Click **Set as Default**
4. New links automatically use this domain
5. Can still override per-link

### Deactivate Domain

Temporarily disable without deleting:

1. Find domain in list
2. Toggle **Active** status to OFF
3. Existing short links stop working
4. Can reactivate anytime

**Use Cases:**
- Domain renewal issues
- Temporary testing
- Security concerns
- Maintenance

### Delete Domain

Permanently remove domain:

1. Find domain in list
2. Click **Delete** or trash icon
3. Confirm deletion
4. All short links with this domain stop working
5. Cannot be undone

**⚠️ Warning:** Deleting domain breaks all existing short links using it!

## Multiple Custom Domains

### Why Use Multiple Domains?

**Different Brands:**
- Multiple products or brands
- Client-specific domains (agencies)
- Regional variations

**Campaign Segregation:**
- Different campaigns use different domains
- Better organization
- Clearer attribution

**Risk Distribution:**
- Avoid dependency on single domain
- Backup domains
- Load distribution

### Managing Multiple Domains

**Strategy:**
1. Designate primary domain (default)
2. Use secondary domains for specific purposes
3. Document which domain for what purpose
4. Train team on domain usage

**Example:**
```
Primary: go.company.com (main marketing)
Secondary: track.company.com (email campaigns)
Tertiary: promo.company.com (special offers)
```

## Best Practices

### Domain Selection

**DO:**
- ✅ Use subdomain of your main domain
- ✅ Keep it short and memorable
- ✅ Make it obvious it's a link shortener
- ✅ Use HTTPS always

**DON'T:**
- ❌ Use your main domain root
- ❌ Use confusing or long subdomains
- ❌ Use domains you don't own
- ❌ Forget about mobile typing

### DNS Configuration

**DO:**
- ✅ Double-check DNS records before saving
- ✅ Use recommended TTL values
- ✅ Allow time for propagation
- ✅ Keep DNS credentials secure

**DON'T:**
- ❌ Rush verification (allow propagation time)
- ❌ Edit records unnecessarily
- ❌ Use extremely low TTL (performance impact)
- ❌ Share DNS access unnecessarily

### Domain Security

**DO:**
- ✅ Enable domain registrar 2FA
- ✅ Use strong registrar passwords
- ✅ Keep registrar contact info updated
- ✅ Set domain auto-renewal
- ✅ Monitor domain expiration

**DON'T:**
- ❌ Let domain expire
- ❌ Share registrar credentials
- ❌ Ignore renewal notices
- ❌ Use weak DNS security

### Link Management

**DO:**
- ✅ Test domain before mass use
- ✅ Monitor domain health
- ✅ Have backup domain ready
- ✅ Document domain purposes

**DON'T:**
- ❌ Use new domain immediately for critical campaigns
- ❌ Create confusion with too many domains
- ❌ Forget to communicate changes to team
- ❌ Delete domains with active links

## Troubleshooting

### DNS Not Propagating

**Problem:** Domain verification stuck on pending

**Solutions:**
1. **Wait Longer:** Can take up to 48 hours
2. **Check DNS Records:**
   - Use DNS checker tool (whatsmydns.net)
   - Verify records are correct
   - Ensure no typos
3. **Check TTL:** May need to wait for TTL to expire
4. **Clear DNS Cache:** Flush local DNS cache
5. **Contact Registrar:** Verify DNS changes saved

### Domain Verification Fails

**Problem:** Verification fails or shows error

**Possible Issues & Solutions:**

1. **Incorrect DNS Record:**
   - Verify CNAME/A record is correct
   - Check for typos
   - Ensure pointing to correct target

2. **Wrong Record Type:**
   - Subdomain: Use CNAME
   - Root domain: Use A record
   - Don't mix types

3. **Cloudflare Proxy Enabled:**
   - Disable proxy (gray cloud)
   - Must be DNS only
   - Save and retry verification

4. **Multiple Records:**
   - Ensure only one record for subdomain
   - Remove conflicting records
   - Save and retry

### Short Links Not Working

**Problem:** Short links redirect incorrectly or not at all

**Solutions:**
1. Check domain is verified and active
2. Verify DNS records still correct
3. Check link hasn't expired
4. Verify link destination URL is correct
5. Test in different browser or incognito
6. Check domain hasn't expired

### SSL Certificate Issues

**Problem:** HTTPS not working or certificate errors

**Solutions:**
1. Wait 24-48 hours after DNS verification
2. Check domain DNS is correct
3. Verify CNAME points to correct target
4. Contact linkutm support for certificate issues
5. Don't use Cloudflare proxy (causes cert issues)

## Advanced Configuration

### Subdomain Delegation

For advanced users:

1. Create subdomain at registrar
2. Delegate DNS to linkutm nameservers (if provided)
3. Full control to linkutm for that subdomain
4. Easier management for multiple domains

### Custom SSL Certificates

If you want to use your own SSL certificate:

1. Generate SSL certificate for your domain
2. Contact linkutm support
3. Provide certificate and private key
4. linkutm configures on your behalf

**Note:** Usually not necessary; automatic SSL works great.

## Related Documentation

- [Link Shortening Overview](/link-shortening/overview)
- [DNS Configuration](/link-shortening/dns-configuration)
- [Short Links](/links/short-link)
- [Link Analytics](/analytics/link-analytics)

## Need Help?

For questions about custom domain setup or DNS configuration, contact our support team or check our troubleshooting guide.
