# Team Collaboration Overview

Learn how to collaborate with your team effectively in LinkUTM.

## Overview

LinkUTM's team collaboration features allow you to work seamlessly with colleagues, manage permissions, track activity, and maintain organized workflows across your organization.

## Team Features

### Team Members

**Add and Manage Team Members:**
- Invite colleagues via email
- Assign roles and permissions
- Track member activity
- Manage member status
- Remove members when needed

**Member Information:**
- Name and email
- Profile picture
- Role and permissions
- Join date
- Last active
- Links created count

### Inviting Team Members

**How to Invite:**

1. **Navigate to Team Settings:**
   - Go to **Dashboard** → **Team**
   - Or **Settings** → **Team Members**

2. **Click Invite:**
   - Click **Invite Member** or **+ Add Member**
   - Enter email address
   - Assign role
   - Set permissions
   - Send invitation

3. **Member Receives Invitation:**
   - Email invitation sent
   - Click link to accept
   - Create account or log in
   - Join workspace

4. **Track Invitation Status:**
   - Pending: Invitation sent, not accepted
   - Active: Member joined and active
   - Declined: Member declined invitation
   - Inactive: Member deactivated

### Member Status

**Status Types:**

**Pending**
- Invitation sent but not accepted
- Cannot access workspace yet
- Resend invitation if needed
- Cancel invitation if needed

**Active**
- Full access to workspace
- Creating and managing links
- Contributing to campaigns
- Full collaboration

**Inactive**
- Temporarily disabled access
- Preserves historical data
- Can be reactivated
- No workspace access

**Declined**
- Member declined invitation
- Can be re-invited
- No access granted

## Roles and Permissions

### Role Types

**Admin**
- Full access to all features
- Manage team members
- Configure workspace settings
- Manage billing
- Delete links and campaigns
- Access all projects

**Manager**
- Create and manage links
- View all team links
- Manage templates and parameters
- View analytics
- Cannot manage team members
- Cannot access billing

**Member**
- Create and manage own links
- View shared links (based on settings)
- Use templates
- View own analytics
- Limited administrative access

**Viewer**
- View-only access
- See links and analytics
- Cannot create or edit links
- Cannot change settings
- Good for stakeholders and clients

### Custom Roles

Create custom roles with specific permissions:

**Permission Categories:**

**Link Management:**
- Create links
- Edit own links
- Edit any link
- Delete own links
- Delete any link
- View all links

**Template & Parameter Management:**
- Create templates
- Edit templates
- Delete templates
- Manage parameters

**Analytics:**
- View own link analytics
- View all link analytics
- Export data
- View real-time data

**Settings:**
- Manage workspace settings
- Manage integrations
- Configure UTM rules
- Manage link shorteners

**Team:**
- Invite members
- Edit member roles
- Remove members
- View activity log

**Example Custom Role:**
```
Role: Content Creator
Permissions:
- ✅ Create links
- ✅ Edit own links
- ✅ Use templates
- ✅ View own analytics
- ❌ Delete links
- ❌ Manage team
- ❌ Access settings
```

## Workspaces and Projects

### Workspaces

**What is a Workspace?**
- Top-level organization
- Contains multiple projects
- Team members belong to workspace
- Shared settings and billing

**Use Cases:**
- Company workspace
- Agency workspace (one per agency)
- Department workspace

**Workspace Features:**
- Multiple projects
- Team member management
- Centralized billing
- Shared resources

### Projects

**What is a Project?**
- Sub-level within workspace
- Campaign or client grouping
- Project-specific settings
- Links belong to projects

**Use Cases:**
- Client projects (for agencies)
- Campaign projects
- Product line projects
- Regional projects

**Project Features:**
- Project-specific links
- Custom UTM rules
- Default link shortener
- Folder organization
- Team member assignment

**Example Structure:**
```
Workspace: Acme Marketing Agency
├── Project: Client A - Fashion Brand
│   ├── Team: Designer, Content Manager
│   └── Links: Social media campaigns
├── Project: Client B - Tech Startup
│   ├── Team: Marketing Manager, Analyst
│   └── Links: Product launch campaigns
└── Project: Internal Marketing
    ├── Team: Full team
    └── Links: Agency promotion
```

### Switching Workspaces and Projects

**Workspace Switcher:**
- Located in sidebar or header
- Click to see available workspaces
- Select to switch
- View member count

**Project Switcher:**
- Dropdown in header or sidebar
- Shows all projects you have access to
- Switch between projects
- View project stats

## Team Activity Tracking

### Activity Log

**What's Tracked:**
- Link created
- Link edited
- Link deleted
- Template created/edited
- Parameter added
- Member invited
- Settings changed
- Integrations configured

**Activity Details:**
- Who performed the action
- What action was taken
- When it occurred
- Which link/resource affected
- Previous vs. new values (for edits)

**Viewing Activity:**

1. Navigate to **Team** → **Activity** or **Activity Log**
2. See chronological list of actions
3. Filter by:
   - Team member
   - Action type
   - Date range
   - Project
   - Resource type

**Use Cases:**
- Audit team actions
- Track changes to links
- Identify who created what
- Troubleshoot issues
- Compliance and accountability

### Member Performance

**Track Individual Contributions:**
- Links created by member
- Templates created
- Links edited
- Click performance of member's links
- Activity level

**Use For:**
- Performance reviews
- Workload balancing
- Recognizing top performers
- Training opportunities

## Team Best Practices

### Onboarding New Members

**Onboarding Checklist:**
1. ✅ Send invitation with welcome message
2. ✅ Assign appropriate role
3. ✅ Share team documentation and standards
4. ✅ Provide access to relevant projects
5. ✅ Introduce UTM naming conventions
6. ✅ Share templates library
7. ✅ Schedule training session
8. ✅ Assign onboarding buddy

### Communication

**Document Standards:**
- UTM naming conventions
- Folder organization strategy
- Tag usage guidelines
- Template usage guide
- Link creation workflow

**Regular Check-ins:**
- Weekly team syncs
- Monthly performance reviews
- Quarterly planning sessions
- Ad-hoc troubleshooting

### Organization

**Folder Strategy:**
- Clear folder hierarchy
- Consistent naming
- Archive old campaigns
- Document folder purposes

**Tag System:**
- Define tag meanings
- Consistent application
- Color code standards
- Team training

**Template Library:**
- Maintain template quality
- Regular template audits
- Document template usage
- Retire obsolete templates

### Access Control

**Principle of Least Privilege:**
- Grant minimum necessary permissions
- Use custom roles effectively
- Regular permission audits
- Remove access when no longer needed

**Security:**
- Strong password requirements
- Enable 2FA (if available)
- Regular security training
- Monitor suspicious activity

## Collaboration Workflows

### Campaign Creation Workflow

**Example Process:**

1. **Planning (Manager):**
   - Create project or folder
   - Define campaign goals
   - Set up UTM template

2. **Execution (Members):**
   - Create links using template
   - Add to designated folder
   - Tag appropriately
   - Add notes for context

3. **Review (Manager):**
   - Check link consistency
   - Verify UTM parameters
   - Approve links

4. **Launch (Members):**
   - Distribute links
   - Monitor performance
   - Report issues

5. **Analysis (Analyst/Manager):**
   - Review analytics
   - Generate reports
   - Share insights
   - Optimize

### Agency Client Management

**Per-Client Setup:**

1. **Create Client Project:**
   - New project per client
   - Client name in project name
   - Client-specific settings

2. **Assign Team:**
   - Account manager
   - Specialist (PPC, Social, etc.)
   - Analyst
   - Set permissions

3. **Organize Resources:**
   - Client-specific templates
   - Folder structure
   - UTM rules
   - Link shortener (client domain)

4. **Reporting:**
   - Scheduled reports
   - Client dashboard access (viewer role)
   - Regular check-ins

## Team Analytics

### Team Performance Metrics

**Collective Metrics:**
- Total links created by team
- Total clicks across team
- Conversion performance
- Team velocity (links/week)

**Individual Metrics:**
- Links created per member
- Click performance
- Template usage
- Activity level

**Project Metrics:**
- Performance by project
- Team efficiency by project
- Project ROI
- Resource allocation

### Leaderboards (If Available)

**Motivate and Recognize:**
- Top link creators
- Most clicks generated
- Best conversion rates
- Most active members

**Use For:**
- Friendly competition
- Recognition
- Identifying best practices
- Training opportunities

## Managing Team Size

### Small Teams (2-5 members)

**Structure:**
- Flat hierarchy
- Everyone has similar permissions
- Shared responsibility
- Informal communication

**Best Practices:**
- Simple folder structure
- Fewer templates
- Open collaboration
- Regular check-ins

### Medium Teams (6-20 members)

**Structure:**
- Defined roles (Admin, Managers, Members)
- Project-based organization
- Specialized responsibilities
- Structured communication

**Best Practices:**
- Clear folder hierarchy
- Well-maintained templates
- Regular team meetings
- Documentation important

### Large Teams (20+ members)

**Structure:**
- Multiple workspaces or projects
- Hierarchical roles
- Department-based organization
- Formal processes

**Best Practices:**
- Comprehensive documentation
- Extensive template library
- Strict UTM rules
- Regular training
- Dedicated administrators

## Removing Team Members

### Offboarding Process

**Steps:**

1. **Prepare for Removal:**
   - Identify links/resources owned by member
   - Reassign ownership if needed
   - Document their work
   - Export any necessary data

2. **Remove Access:**
   - Go to **Team** settings
   - Find team member
   - Click **Remove** or **Deactivate**
   - Confirm removal

3. **Options:**
   - **Delete:** Completely remove (not recommended)
   - **Deactivate:** Preserve data, remove access (recommended)

4. **After Removal:**
   - Links created remain (attributed to member)
   - Analytics data preserved
   - Activity log maintains history
   - Can reactivate if needed

**What Happens to Their Links:**
- Links remain active
- Analytics continue tracking
- Ownership can be transferred
- Historical data preserved

## Security and Privacy

### Data Access

**What Team Members Can See:**
- Links they have permission to view
- Project analytics (based on role)
- Team member info (limited)
- Activity relevant to them

**What They Cannot See (by default):**
- Billing information (unless admin)
- Other projects without access
- Personal data of other members
- Sensitive settings (unless admin)

### Audit Trail

**Comprehensive Logging:**
- All team actions logged
- Immutable activity history
- Compliance support
- Security monitoring

**Retention:**
- Activity log retention (varies by plan)
- Export logs for long-term storage
- Audit support

## Related Documentation

- [Roles and Permissions](/team-collaboration/roles-permissions)
- [Inviting Team Members](/team-collaboration/invite-members)
- [Activity Tracking](/team-collaboration/activity-log)
- [Workspaces and Projects](/team-collaboration/workspaces)
- [Team Settings](/settings/team-settings)

## Need Help?

For questions about team collaboration or member management, contact our support team or explore our comprehensive guides.
