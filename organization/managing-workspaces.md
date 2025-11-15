# Managing Workspaces

Learn how to create, configure, and manage workspaces in linkutm.

## What is a Workspace?

A workspace is the middle tier of linkutm's organizational structure. It represents your company, agency, or department and contains all your projects, team members, and shared resources.

**Key Features:**
- Contains multiple projects
- Team member management
- Shared templates and parameters
- Workspace-specific settings
- Centralized analytics

## Creating a Workspace

### Step 1: Access Workspace Creation

**From Dashboard:**
1. Click the **Workspace Switcher** in the top navigation
2. Click **Create New Workspace** or **+ Add Workspace**

**From Settings:**
1. Go to **Settings** → **Workspaces**
2. Click **Create Workspace** button

### Step 2: Enter Workspace Details

**Workspace Name** (Required)
- Use your company or department name
- Keep it professional and clear
- Examples:
  - ✅ "Acme Corporation"
  - ✅ "Digital Marketing Agency"
  - ✅ "E-commerce Division"
  - ❌ "My Workspace"
  - ❌ "Test123"

**Workspace Description** (Optional)
- Brief description of workspace purpose
- Helps team understand workspace scope
- Example: "Main marketing workspace for all company campaigns"

**Default Settings:**
- **Timezone**: Select your primary timezone
- **Date Format**: Choose date format preference
- **Default Link Shortener**: Set workspace default (can be overridden per project)

### Step 3: Configure Initial Settings

**Team Settings:**
- Who can invite members?
- Default role for new members
- Require approval for new members

**Link Settings:**
- Default link expiration period
- Default click tracking settings
- QR code generation preferences

**Analytics Settings:**
- Default analytics date range
- Retention period
- Export format preferences

### Step 4: Create Initial Project

After creating workspace, you'll be prompted to create your first project:

1. Enter project name
2. Set project description
3. Configure basic settings
4. Click **Create Project**

**Or skip and create projects later.**

### Step 5: Invite Team Members

Add team members to your workspace:

1. Click **Invite Team Members**
2. Enter email addresses (comma-separated for multiple)
3. Assign roles:
   - Admin
   - Manager
   - Member
   - Viewer
4. Add welcome message (optional)
5. Send invitations

## Workspace Dashboard

### Overview Section

**Key Metrics Displayed:**
- **Total Projects**: Number of projects in workspace
- **Total Links**: All links across all projects
- **Total Clicks**: Aggregate clicks across workspace
- **Team Members**: Number of active members
- **Active Projects**: Projects with recent activity

**Charts and Graphs:**
- Click trends over time
- Projects by performance
- Top sources and mediums
- Geographic distribution

### Quick Actions

**From Workspace Dashboard:**
- Create new project
- Invite team member
- View workspace analytics
- Access workspace settings
- Switch to different workspace

### Recent Activity

See latest activity across all workspace projects:
- Links created
- Projects added
- Team members joined
- Settings changed
- Milestones reached

## Workspace Settings

### General Settings

**Access:**
1. Select workspace
2. Go to **Settings** → **Workspace Settings**
3. Click **General** tab

**Configurable Options:**

**Workspace Information:**
- Workspace name
- Description
- Company logo (if available)
- Industry/category

**Regional Settings:**
- Primary timezone
- Date format (MM/DD/YYYY or DD/MM/YYYY)
- Time format (12-hour or 24-hour)
- Language preference

**Workspace Defaults:**
- Default project settings
- Default UTM rules
- Default link shortener
- Default folder structure

### Team Management

**Access:**
1. Go to **Settings** → **Team**
2. View all workspace members

**Team Overview Shows:**
- Member name and email
- Profile picture
- Role in workspace
- Date joined
- Last active
- Projects assigned
- Links created

**Team Actions:**
- Invite new members
- Edit member roles
- Remove members
- Resend invitations
- View member activity

**Bulk Actions:**
- Select multiple members
- Assign to project
- Change roles
- Remove from workspace

[Learn more about team management →](/team-collaboration/overview)

### Permission Settings

**Workspace-Level Permissions:**

**Admin Permissions:**
- ✅ Full workspace access
- ✅ Create/delete projects
- ✅ Manage all team members
- ✅ Configure workspace settings
- ✅ View billing
- ✅ Manage integrations

**Manager Permissions:**
- ✅ Create projects
- ✅ Manage assigned projects
- ✅ Invite team members (limited)
- ✅ View workspace analytics
- ❌ Delete workspace
- ❌ Manage billing

**Member Permissions:**
- ✅ Access assigned projects
- ✅ Create links
- ✅ Use templates
- ✅ View analytics (limited)
- ❌ Create projects
- ❌ Manage team

**Viewer Permissions:**
- ✅ View workspace (read-only)
- ✅ View analytics
- ❌ Create or edit anything
- ❌ Access settings

**Custom Roles:**
Create custom roles with specific permissions:
1. Go to **Settings** → **Roles**
2. Click **Create Custom Role**
3. Name the role
4. Select permissions
5. Save role

### Integrations

**Available Integrations:**

**Google Analytics 4:**
- Connect GA4 account
- Select property and stream
- Automatic data sync
- View GA4 data in linkutm

**Third-Party Tools:**
- Zapier integration
- Slack notifications
- Webhook configuration
- API access

**Configure Integration:**
1. Go to **Settings** → **Integrations**
2. Find integration to configure
3. Click **Connect** or **Configure**
4. Follow authorization flow
5. Configure settings
6. Save integration

### Billing (If Applicable)

**Workspace Billing:**
1. Go to **Settings** → **Billing**
2. View current plan
3. See usage statistics
4. Manage subscription
5. Update payment method

**Billing Information:**
- Current plan details
- Monthly/annual billing
- Next billing date
- Payment method
- Invoice history

## Managing Multiple Workspaces

### Workspace Switcher

**Quick Switch:**
1. Click workspace name in top navigation
2. Dropdown shows all workspaces you have access to
3. Click desired workspace
4. Dashboard reloads with workspace data

**Workspace List Shows:**
- Workspace name
- Your role
- Project count
- Member count
- Last accessed

### Workspace Comparison

**Compare Performance:**
1. Go to **Analytics** → **Workspace Comparison**
2. Select workspaces to compare
3. Choose metrics
4. Select date range
5. View comparison charts

**Comparable Metrics:**
- Total clicks
- Total links
- Conversion rates
- Top sources
- Geographic distribution
- Team productivity

### Default Workspace

**Set Default Workspace:**
1. Go to **Settings** → **Preferences**
2. Find **Default Workspace** setting
3. Select workspace
4. Save

**Benefits:**
- Opens to this workspace on login
- Quick access to most-used workspace
- Saves time

## Workspace Templates & Resources

### Shared Templates

**Workspace-Level Templates:**
- Available to all projects in workspace
- Maintain consistency across projects
- Easier template management

**Creating Shared Templates:**
1. Go to **Templates** in workspace view
2. Click **Create Template**
3. Configure template
4. Toggle **Share with all projects**
5. Save template

**Template Inheritance:**
- Projects can use workspace templates
- Projects can create project-specific templates
- Project templates don't affect other projects

### Shared Parameters

**Workspace Parameter Library:**
- Centralized UTM parameters
- Consistent across all projects
- Auto-complete suggestions

**Managing Shared Parameters:**
1. Go to **Parameters** in workspace view
2. Add parameters at workspace level
3. Available to all projects
4. Standardize naming conventions

### Shared Link Shorteners

**Workspace-Level Shorteners:**
- Configure once, use across all projects
- Branded domain for entire workspace
- Simplified management

**Setup:**
1. Go to **Settings** → **Link Shortening**
2. Add custom domain
3. Configure DNS
4. Set as workspace default
5. All projects can use

## Collaboration Features

### Workspace Activity Feed

**View All Activity:**
1. Go to **Activity** tab in workspace
2. See chronological activity log
3. Filter by:
   - Member
   - Project
   - Action type
   - Date range

**Activity Types:**
- Project created
- Link created/edited
- Team member joined
- Template created
- Settings changed

### Workspace Notes & Documentation

**Shared Documentation:**
- Workspace-level notes
- Best practices
- UTM naming conventions
- Template usage guidelines
- Contact information

**Creating Workspace Docs:**
1. Go to **Settings** → **Documentation**
2. Create new document
3. Write content (supports markdown)
4. Save and share with team

### Workspace Announcements

**Communicate with Team:**
1. Go to **Workspace** → **Announcements**
2. Click **Create Announcement**
3. Write message
4. Select visibility (all members or specific roles)
5. Post announcement

**Use Cases:**
- New feature rollouts
- Workspace changes
- Best practice updates
- Team events
- Policy changes

## Workspace Analytics

### Aggregate Metrics

**View Workspace-Wide Performance:**
1. Select workspace
2. Go to **Analytics**
3. View aggregate dashboard

**Available Metrics:**
- Total clicks (all projects)
- Unique visitors
- Conversion rates
- Top-performing projects
- Top sources and mediums
- Geographic distribution
- Device breakdown
- Time-based trends

### Project Performance Comparison

**Compare Projects:**
- Side-by-side comparison
- Identify best performers
- Optimize budget allocation
- Spot trends

**How to Compare:**
1. Go to **Analytics** → **Projects**
2. Select projects to compare
3. Choose metrics
4. View comparison charts

### Team Performance

**Team Metrics:**
- Links created per member
- Click performance by creator
- Template usage
- Activity levels
- Project contributions

**Use For:**
- Performance reviews
- Workload balancing
- Identifying training needs
- Recognizing top performers

## Workspace Maintenance

### Regular Audits

**Monthly Checklist:**
- ✅ Review team member access
- ✅ Archive inactive projects
- ✅ Clean up old templates
- ✅ Review UTM parameters
- ✅ Check integration status
- ✅ Review usage statistics

**Quarterly Checklist:**
- ✅ Comprehensive template audit
- ✅ Team permissions review
- ✅ Workspace settings optimization
- ✅ Performance analysis
- ✅ Strategic planning

### Archiving Projects

**When to Archive:**
- Campaign completed
- Project no longer active
- Seasonal campaigns ended
- Client work finished

**How to Archive:**
1. Go to project settings
2. Toggle **Archive Project**
3. Project moves to archived section
4. Links still work
5. Can be restored anytime

**Archived Projects:**
- Not shown in main project list
- Accessible via **Archived Projects** section
- Analytics still available
- Links remain functional

### Workspace Cleanup

**Regular Cleanup Tasks:**

**Templates:**
- Remove unused templates
- Update outdated templates
- Consolidate similar templates
- Document template purposes

**Parameters:**
- Remove obsolete parameter values
- Standardize naming
- Merge duplicates
- Update documentation

**Team:**
- Remove inactive members
- Update roles as needed
- Re-verify permissions
- Update contact information

**Links:**
- Archive old campaign links
- Remove test links
- Update expired links
- Organize into folders

## Workspace Migration

### Exporting Workspace Data

**Export Options:**
1. Go to **Settings** → **Export**
2. Select data to export:
   - All links
   - Templates
   - Parameters
   - Team members
   - Analytics
3. Choose format (CSV, JSON)
4. Click **Export**
5. Download file

**Use Cases:**
- Backup workspace data
- Migrate to another platform
- Data analysis
- Compliance requirements

### Importing Data

**Import to Workspace:**
1. Go to **Settings** → **Import**
2. Select import type
3. Upload file (CSV or JSON)
4. Map fields
5. Preview import
6. Confirm import

**Importable Data:**
- Links from CSV
- Templates
- Parameters
- Team members (bulk invite)

### Transferring Workspace Ownership

**Transfer to Another User:**
1. Go to **Settings** → **Workspace Settings**
2. Find **Ownership** section
3. Click **Transfer Ownership**
4. Select new owner (must be workspace member)
5. Confirm transfer
6. New owner accepts transfer

**What Changes:**
- Billing responsibility transfers
- Full admin access for new owner
- Original owner can be removed or changed to different role

## Best Practices

### Workspace Naming

**DO:**
- ✅ Use official company name
- ✅ Be professional
- ✅ Make it easily identifiable
- ✅ Keep it concise

**DON'T:**
- ❌ Use temporary names
- ❌ Use abbreviations only
- ❌ Include dates or versions
- ❌ Use generic names

### Team Management

**Best Practices:**
- Add members with clear roles
- Regular permission audits
- Remove inactive members promptly
- Document team structure
- Communicate changes

### Resource Organization

**Templates:**
- Maintain up-to-date template library
- Clear naming conventions
- Document template purposes
- Regular audits

**Parameters:**
- Standardized parameter values
- Documented naming standards
- Regular cleanup
- Team training

### Security

**Security Best Practices:**
- Regular access reviews
- Strong password policies
- Enable 2FA (if available)
- Monitor activity logs
- Immediate access removal for departing members

## Troubleshooting

### Can't Create Workspace

**Possible Reasons:**
- Organization plan limit reached
- Insufficient permissions
- Account issues

**Solutions:**
- Check organization plan
- Contact organization admin
- Upgrade plan if needed

### Workspace Not Showing

**Check:**
- Correct organization selected
- You have workspace access
- Workspace wasn't deleted
- No filters applied

**Solutions:**
- Refresh page
- Clear browser cache
- Contact workspace admin
- Check with organization owner

### Team Members Can't Access

**Common Issues:**
- Not invited to workspace
- Invitation not accepted
- Wrong email address
- Access revoked

**Solutions:**
- Resend invitation
- Verify email address
- Check member status
- Grant appropriate permissions

### Integration Not Working

**Troubleshoot:**
- Re-authorize integration
- Check permissions
- Verify credentials
- Test connection
- Contact support

## Related Documentation

- [Organization Overview](/organization/overview)
- [Managing Projects](/organization/managing-projects)
- [Team Collaboration](/team-collaboration/overview)
- [Workspace Settings](/settings/workspace-settings)

## Need Help?

For questions about workspace management, contact our support team or explore our comprehensive guides.
