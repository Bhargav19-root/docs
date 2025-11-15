# Managing Projects

Learn how to create, configure, and manage projects in linkutm.

## What is a Project?

A project is the lowest tier of linkutm's organizational structure. It represents a specific campaign, client, product line, or initiative and contains all related links, templates, and settings.

**Key Features:**
- Contains links and tracking codes
- Project-specific UTM rules
- Dedicated team members
- Individual analytics
- Custom configurations

## Creating a Project

### Step 1: Access Project Creation

**From Dashboard:**
1. Click the **Project Switcher** in navigation
2. Click **Create New Project** or **+ Add Project**

**From Settings:**
1. Go to **Settings** → **Projects**
2. Click **Create Project** button

**From Workspace:**
1. Select workspace
2. Click **New Project**

### Step 2: Enter Project Details

**Project Name** (Required)
- Clear, descriptive name
- Include timeframe if relevant
- Include client name for agencies

**Examples:**
- ✅ "Q1 2024 Email Campaigns"
- ✅ "Client: Fashion Brand - Spring Launch"
- ✅ "Black Friday 2024 Sale"
- ✅ "Product Launch - Widget Pro"
- ❌ "Project 1"
- ❌ "Links"
- ❌ "Test"

**Project Description** (Optional)
- Purpose and scope
- Campaign objectives
- Key information
- Team notes

**Example Description:**
```
Spring 2024 product launch campaign for Widget Pro.
Includes email, social media, and paid search.
Target: 10,000 signups by March 31.
Budget: $50,000
Team: Marketing Manager, PPC Specialist, Content Writer
```

### Step 3: Configure Project Settings

**Default Link Shortener:**
- Select shortener for this project
- Custom domain (if configured)
- Workspace default
- No shortening

**Default Folder:**
- Create initial folder structure
- Or skip and create later

**UTM Rules:**
- Apply workspace rules
- Create project-specific rules
- Set standardization rules
- Configure required fields

**Team Assignment:**
- Add team members to project
- Assign roles
- Set permissions

### Step 4: Create Initial Folders (Optional)

Set up folder structure:

**Common Folder Structures:**

**By Channel:**
```
├── Email Marketing
├── Social Media
├── Paid Advertising
└── Content Marketing
```

**By Campaign Phase:**
```
├── Pre-Launch
├── Launch
├── Post-Launch
└── Retargeting
```

**By Content Type:**
```
├── Blog Posts
├── Landing Pages
├── Product Pages
└── Events
```

### Step 5: Review and Create

1. Review all settings
2. Click **Create Project**
3. Project is created and selected
4. Ready to create first link

## Project Dashboard

### Overview Section

**Key Metrics:**
- **Total Links**: Number of links in project
- **Total Clicks**: Aggregate clicks
- **Unique Visitors**: Distinct visitors
- **Conversions**: Goal completions
- **Click-Through Rate**: Average CTR
- **Top Source**: Best performing source
- **Top Medium**: Best performing medium

**Visual Analytics:**
- Click trends graph
- Source/medium breakdown
- Geographic heat map
- Device distribution
- Time-based patterns

### Quick Actions

**From Project Dashboard:**
- Create new link
- Create from template
- Bulk import links
- View analytics
- Manage folders
- Configure settings

### Recent Links

See latest links created in project:
- Link name
- Destination URL
- Short URL
- Created by
- Creation date
- Click count

### Project Activity

Recent activity in project:
- Links created/edited
- Templates used
- Team member actions
- Milestones reached

## Project Settings

### General Settings

**Access:**
1. Select project
2. Go to **Settings** → **Project Settings**
3. Configure options

**General Information:**
- Project name
- Description
- Status (Active/Archived)
- Created date
- Project owner

**Default Settings:**
- Default folder for new links
- Default tags
- Default link expiration
- Default shortener
- QR code defaults

### UTM Rules Configuration

**Project-Level UTM Rules:**

**Project Rules:**
- Space character replacement
- Force lowercase
- Default link shortener
- Prohibited values

**Example Project Rules:**
```
Space Replacement: Underscore
Force Lowercase: Enabled
Default Shortener: go.yourbrand.com
Prohibited: test, temp, delete, xxx
```

**Standardization Rules:**
- Auto-transform parameter values
- Fix common typos
- Standardize variations
- Active/inactive toggle

**Example Standardization:**
```
Rule 1: fb, Facebook → facebook
Rule 2: email, e-mail → newsletter
Rule 3: paid, ppc → cpc
```

**Required Field Rules:**
- Minimum/maximum characters
- Regex validation
- Required parameters
- Conditional requirements

**Example Requirements:**
```
utm_campaign: Min 5 chars, Max 50 chars
utm_source: Regex ^[a-z_]+$
If utm_medium = "cpc": utm_term required
```

[Learn more about UTM rules →](/utm-rules/overview)

### Link Shortening Settings

**Configure Shorteners:**
1. Go to **Settings** → **Link Shortening**
2. Select default shortener for project
3. Options:
   - Custom branded domain
   - Workspace default
   - No shortening

**Custom Domain (Project-Specific):**
- Add project-specific domain
- Configure DNS
- Set as project default
- All links use this domain

**Example Use Case:**
```
Agency Project: Client A
Custom Domain: go.clienta.com
All Client A links use their branded domain
```

[Learn more about custom domains →](/link-shortening/custom-domains)

### Team Management

**Project Team:**
- View team members assigned to project
- Add/remove members
- Change member roles
- Set permissions

**Project Roles:**

**Project Admin:**
- Full project access
- Manage settings
- Manage team
- Delete project

**Project Manager:**
- Create/edit links
- Use templates
- View analytics
- Cannot change settings

**Project Member:**
- Create own links
- Use templates
- View limited analytics
- Cannot edit others' links

**Project Viewer:**
- View-only access
- See links and analytics
- Cannot create or edit
- Good for clients or stakeholders

**Adding Team Members:**
1. Go to **Settings** → **Team**
2. Click **Add Member**
3. Select from workspace members
4. Assign role
5. Save

**Removing Team Members:**
1. Find member in list
2. Click **Remove**
3. Confirm removal
4. Their links remain in project

### Folder Management

**Project Folders:**
- Organize links within project
- Nested folder support (if available)
- Folder-level analytics
- Easy filtering

**Creating Folders:**
1. Go to **Folders** tab
2. Click **Create Folder**
3. Enter folder name
4. Optional: Add description
5. Save folder

**Folder Settings:**
- Set default folder for new links
- Folder color coding (if available)
- Folder permissions (if available)

[Learn more about folders →](/links/folders)

## Project Templates

### Project-Specific Templates

**Create Templates for Project:**
1. Go to **Templates** within project
2. Click **Create Template**
3. Configure template
4. Set scope:
   - **This project only**: Private to project
   - **Share with workspace**: Available to all projects
5. Save template

**Example Project Templates:**

**For Email Campaign Project:**
```
Template: Weekly Newsletter
utm_source: newsletter
utm_medium: email
utm_campaign: weekly_[week_number]_2024
utm_content: [variable]
```

**For Paid Ads Project:**
```
Template: Facebook Ad
utm_source: facebook
utm_medium: cpc
utm_campaign: [campaign_name]
utm_term: [audience]
utm_content: [ad_variant]
```

**For Client Project (Agency):**
```
Template: Client A - Social
utm_source: [platform]
utm_medium: social
utm_campaign: clienta_[campaign_name]
utm_content: [placement]
```

### Using Workspace Templates

**Access Shared Templates:**
- Use workspace-level templates in project
- Consistent across all projects
- No need to recreate

**Template Priority:**
1. Project-specific templates (shown first)
2. Workspace templates (available to all)

## Project Analytics

### Link-Level Analytics

**View Individual Link Performance:**
1. Go to **Links** in project
2. Click link to view details
3. See comprehensive metrics

**Metrics Available:**
- Total clicks
- Unique visitors
- Click timeline
- Geographic data
- Device breakdown
- Browser information
- Referrer sources
- UTM parameter breakdown

### Project-Level Analytics

**Aggregate Project Metrics:**
1. Go to **Analytics** in project
2. View project dashboard

**Available Reports:**
- Total performance metrics
- UTM parameter analysis
- Source/medium breakdown
- Campaign comparison
- Time-based trends
- Geographic distribution
- Device and browser stats
- Conversion tracking

### Custom Reports

**Create Project Reports:**
1. Go to **Analytics** → **Reports**
2. Click **Create Report**
3. Select metrics and dimensions
4. Choose date range
5. Apply filters
6. Save report

**Report Types:**
- Executive summary
- Campaign performance
- Channel effectiveness
- ROI analysis
- Team performance

**Export Options:**
- CSV format
- Excel
- PDF
- Scheduled email delivery

## Project Workflows

### Campaign Creation Workflow

**Standard Process:**

1. **Planning Phase:**
   - Create project
   - Set up folders
   - Create templates
   - Assign team

2. **Link Creation:**
   - Use templates
   - Create campaign links
   - Add to folders
   - Tag appropriately

3. **Review:**
   - Check UTM parameters
   - Verify destinations
   - Test links
   - Generate QR codes (if needed)

4. **Launch:**
   - Distribute links
   - Monitor real-time
   - Track performance
   - Respond to issues

5. **Optimize:**
   - Analyze data
   - Adjust campaigns
   - A/B test
   - Report results

### Client Project Workflow (Agencies)

**Agency Best Practices:**

1. **Client Onboarding:**
   - Create dedicated project
   - Set up custom domain (client's)
   - Create client templates
   - Add team members

2. **Campaign Setup:**
   - Client-specific folders
   - Branded short links
   - Custom UTM rules
   - Approval workflow

3. **Execution:**
   - Create campaign links
   - Client preview/approval
   - Launch campaigns
   - Monitor performance

4. **Reporting:**
   - Generate client reports
   - Schedule automated reports
   - Client dashboard access (viewer role)
   - Regular check-ins

### Seasonal Campaign Projects

**E-commerce Example:**

```
Project: Black Friday 2024

Folders:
├── Pre-Launch Teasers
├── Early Access (VIP)
├── Black Friday Day
├── Cyber Monday
└── Extended Sale

Timeline:
- Oct 1: Create project
- Oct 15: Pre-launch links
- Nov 15: Early access links
- Nov 29: Black Friday links
- Dec 2: Cyber Monday links
- Dec 5: Archive project
```

## Project Organization Strategies

### By Campaign Type

**Separate Projects for:**
- Email marketing campaigns
- Social media campaigns
- Paid advertising campaigns
- Content marketing campaigns
- Event promotions

**Benefits:**
- Clear separation
- Specialized settings
- Focused analytics
- Team specialization

### By Time Period

**Quarterly or Monthly Projects:**
```
- Q1 2024 Campaigns
- Q2 2024 Campaigns
- Q3 2024 Campaigns
- Q4 2024 Campaigns
```

**Benefits:**
- Easy period comparison
- Clean archives
- Clear timelines
- Simplified reporting

### By Client (Agencies)

**One Project Per Client:**
```
- Client A - Fashion Brand
- Client B - Tech Startup
- Client C - Restaurant Chain
```

**Benefits:**
- Client isolation
- Custom settings per client
- Individual reporting
- Clear ownership

### By Product Line

**E-commerce/Multi-Product Companies:**
```
- Product Line A Marketing
- Product Line B Marketing
- Cross-Product Campaigns
```

**Benefits:**
- Product-specific tracking
- Separate budgets
- Performance comparison
- Resource allocation

## Archiving Projects

### When to Archive

**Archive Projects When:**
- ✅ Campaign completed
- ✅ Client work finished
- ✅ Seasonal campaign ended
- ✅ Testing phase complete
- ✅ Project replaced by new version

**Don't Archive If:**
- ❌ Links still actively used
- ❌ Ongoing campaign
- ❌ Need to create more links
- ❌ Current analytics review

### How to Archive

**Archive Process:**
1. Go to **Settings** → **Project Settings**
2. Find **Status** section
3. Change status to **Archived**
4. Add archive note (optional)
5. Save changes

**What Happens:**
- Project hidden from main list
- All links continue working
- Analytics still accessible
- Can be restored anytime
- Moved to **Archived Projects** section

### Accessing Archived Projects

**View Archived:**
1. Go to **Projects** page
2. Click **Show Archived**
3. See all archived projects
4. Click to view details

**Restore Archived Project:**
1. Open archived project
2. Go to **Settings**
3. Change status to **Active**
4. Save
5. Project returns to main list

## Deleting Projects

### When to Delete

**Only Delete If:**
- ⚠️ Test project no longer needed
- ⚠️ Created by mistake
- ⚠️ Completely obsolete
- ⚠️ After exporting data

**Important Warnings:**
- ❌ Deletes ALL links permanently
- ❌ Deletes ALL analytics data
- ❌ All short links stop working
- ❌ Cannot be undone

### How to Delete

**Deletion Process:**
1. Go to **Settings** → **Project Settings**
2. Scroll to **Danger Zone**
3. Click **Delete Project**
4. Type project name to confirm
5. Click **Permanently Delete**

**Before Deleting:**
- ✅ Export all data
- ✅ Notify team members
- ✅ Verify no active campaigns
- ✅ Check for linked resources
- ✅ Archive instead if unsure

## Project Best Practices

### Naming Conventions

**Include Key Information:**
- Client name (for agencies)
- Campaign type
- Time period
- Product/service

**Examples:**
- "Client: Acme Corp - Q1 2024"
- "Email Marketing - Summer 2024"
- "Product Launch - Widget Pro"
- "Black Friday Sale 2024"

### Team Collaboration

**Clear Roles:**
- Define who can do what
- Document responsibilities
- Regular team syncs
- Clear communication

**Documentation:**
- Project objectives in description
- UTM naming standards
- Folder organization
- Contact information

### Regular Maintenance

**Weekly:**
- Review new links
- Check UTM compliance
- Monitor performance
- Address issues

**Monthly:**
- Team review meeting
- Analytics deep dive
- Template updates
- Folder cleanup

**Project End:**
- Final report
- Archive project
- Export data
- Lessons learned

## Troubleshooting

### Can't Create Project

**Possible Reasons:**
- Workspace plan limit
- Insufficient permissions
- Not workspace member

**Solutions:**
- Check workspace plan
- Request admin access
- Contact workspace admin
- Upgrade plan

### Project Links Not Working

**Check:**
- Project not deleted
- Links not expired
- Shortener configured
- Domain DNS correct

**Solutions:**
- Verify project status
- Check link settings
- Test shortener
- Review DNS configuration

### Analytics Not Showing

**Possible Issues:**
- No clicks yet
- Data sync delay
- Filter applied
- Date range incorrect

**Solutions:**
- Wait for clicks
- Allow 5-10 minutes for sync
- Clear filters
- Check date range

### Team Member Can't Access

**Verify:**
- Added to workspace
- Added to project
- Correct role assigned
- Invitation accepted

**Solutions:**
- Add to project team
- Check permissions
- Resend invitation
- Verify email address

## Related Documentation

- [Organization Overview](/organization/overview)
- [Managing Workspaces](/organization/managing-workspaces)
- [Creating Links](/links/create-link)
- [UTM Rules](/utm-rules/overview)
- [Project Analytics](/analytics/overview)

## Need Help?

For questions about project management, contact our support team or explore our comprehensive guides.
