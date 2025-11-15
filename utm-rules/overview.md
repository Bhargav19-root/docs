# UTM Rules Overview

Learn how to automate and enforce UTM parameter standards with LinkUTM's powerful rules engine.

## What are UTM Rules?

UTM Rules allow you to automatically standardize, validate, and enforce consistency across all your UTM parameters. Instead of manually checking every link for compliance, set up rules once and let LinkUTM ensure quality automatically.

## Why Use UTM Rules?

### Benefits

**Automatic Standardization**
- Enforce lowercase or specific formatting
- Replace spaces automatically
- Consistent parameter values
- Clean analytics data

**Data Quality**
- Prevent common errors
- Catch typos before links are created
- Validate parameter formats
- Ensure completeness

**Team Alignment**
- Everyone follows same standards
- No need to memorize rules
- New members automatically compliant
- Reduced training time

**Time Savings**
- No manual checking required
- Automatic corrections
- Fewer link edits needed
- Focus on strategy, not syntax

**Better Analytics**
- Cleaner data in analytics
- Easier reporting
- More accurate attribution
- Better insights

## Types of UTM Rules

### 1. Project Rules

Global settings that apply to all links in a project.

**Space Character Replacement**
Replace spaces in UTM parameters with:
- Nothing (remove spaces): `summer sale` → `summersale`
- Hyphen: `summer sale` → `summer-sale`
- Underscore: `summer sale` → `summer_sale` (recommended)
- Plus: `summer sale` → `summer+sale`
- URL Encoded: `summer sale` → `summer%20sale`

**Force Lowercase**
- Convert all UTM parameters to lowercase
- Prevents: `Facebook` vs `facebook` discrepancies
- Result: Consistent `facebook` always

**Default Link Shortener**
- Set default shortener for all links
- Can be overridden per link
- Ensures consistency

**Prohibited Values**
- Block specific parameter values
- Prevent common mistakes
- Example: Block `test`, `asdf`, `xxx`
- Shows error if user tries to use

**Example Project Rules:**
```
Space Replacement: Underscore
Force Lowercase: Enabled
Default Shortener: go.company.com
Prohibited Values: test, asdf, temp, xxx, delete
```

[Learn about Project Rules →](/utm-rules/project-rules)

### 2. Standardization Rules

Transform parameter values based on conditions.

**What They Do:**
- If parameter contains X, replace with Y
- Pattern-based replacements
- Multiple rules can apply
- Applied in order

**Example Standardization Rules:**

**Rule 1: Standardize Facebook variations**
```
If utm_source contains: facebook, fb, Facebook, FACEBOOK
Replace with: facebook
```

**Rule 2: Standardize email variations**
```
If utm_source contains: email, e-mail, newsletter
Replace with: newsletter
```

**Rule 3: Fix common typos**
```
If utm_source contains: gogle, googl
Replace with: google
```

**Rule 4: Standardize mediums**
```
If utm_medium contains: paid, ppc, paid-search
Replace with: cpc
```

**Active/Inactive Toggle:**
- Enable or disable rules without deleting
- Test rules before full rollout
- Temporarily disable for special cases

[Learn about Standardization Rules →](/utm-rules/standardization-rules)

### 3. Required Field Rules

Validation rules that must be satisfied before creating a link.

**Validation Types:**

**Minimum Characters (minChar)**
- Ensure parameter has at least X characters
- Example: utm_campaign must be at least 5 characters
- Prevents: `fb`, `x`, `a` (too short)

**Maximum Characters (maxChar)**
- Limit parameter to X characters
- Example: utm_campaign max 50 characters
- Prevents overly long values

**Regex Pattern**
- Advanced pattern matching
- Complex validation rules
- Example: `^[a-z0-9_]+$` (only lowercase, numbers, underscores)
- Flexible and powerful

**Required Parameters**
- Force specific parameters to be filled
- Example: Require utm_term for all paid campaigns
- Context-aware requirements

**Example Required Field Rules:**

**Rule 1: Campaign name length**
```
Parameter: utm_campaign
Validation: minChar: 5, maxChar: 50
Error Message: "Campaign name must be 5-50 characters"
```

**Rule 2: Source format**
```
Parameter: utm_source
Validation: regex: ^[a-z_]+$
Error Message: "Source must be lowercase letters and underscores only"
```

**Rule 3: Require term for paid campaigns**
```
Condition: If utm_medium = "cpc"
Required: utm_term must be filled
Error Message: "Paid campaigns require utm_term (keyword)"
```

[Learn about Required Field Rules →](/utm-rules/required-fields)

## Setting Up UTM Rules

### Access UTM Rules

1. Navigate to **Dashboard** → **UTM Rules**
2. Or **Settings** → **UTM Rules**
3. Select your project
4. View existing rules or create new

### Create Project Rules

1. Go to **UTM Rules** → **Project Rules** tab
2. Configure space replacement
3. Toggle force lowercase
4. Set default shortener
5. Add prohibited values (comma-separated)
6. Save settings

### Create Standardization Rules

1. Go to **UTM Rules** → **Standardization Rules** tab
2. Click **Create Rule** or **+ Add Rule**
3. Enter rule details:
   - Rule name
   - Apply to parameter (source, medium, campaign, etc.)
   - Condition (contains, equals, starts with, etc.)
   - Value to match
   - Replacement value
4. Toggle active/inactive
5. Save rule

**Rule Order Matters:**
- Rules applied top to bottom
- First match may prevent other matches
- Drag to reorder if available

### Create Required Field Rules

1. Go to **UTM Rules** → **Required Fields** tab
2. Click **Create Rule** or **+ Add Rule**
3. Configure rule:
   - Parameter to validate
   - Validation type (minChar, maxChar, regex)
   - Validation value
   - Error message (user-facing)
   - Conditional logic (optional)
4. Save rule

## How Rules Work

### When Rules Apply

**During Link Creation:**
1. User enters UTM parameters
2. Project rules apply first (lowercase, spaces)
3. Standardization rules transform values
4. Required field rules validate
5. If all pass: Link created
6. If validation fails: Error shown

**Real-Time Feedback:**
- See transformations as you type (if supported)
- Immediate validation errors
- Clear error messages
- Suggestions for fixes

**Example Flow:**
```
User enters: "Summer Sale 2024" for utm_campaign

Project Rules Apply:
- Force lowercase → "summer sale 2024"
- Replace spaces with underscore → "summer_sale_2024"

Standardization Rules Apply:
- (No matching rules)

Required Field Rules Validate:
- minChar (5): ✅ Pass (15 characters)
- maxChar (50): ✅ Pass (15 characters)
- Pattern: ✅ Pass (if any)

Result: "summer_sale_2024" ✅ Link created
```

### What Rules Don't Affect

**Existing Links:**
- Rules don't retroactively change existing links
- Only apply to new links or edited links
- Historical data preserved

**Templates:**
- Templates created before rules still work
- New templates follow rules
- Editing template applies current rules

## UTM Rules Best Practices

### Start Simple

**Phase 1: Project Rules Only**
- Enable force lowercase
- Set space replacement
- Add a few prohibited values

**Phase 2: Add Basic Standardization**
- 2-3 rules for common variations
- Focus on high-impact standardizations

**Phase 3: Required Fields**
- Minimum length requirements
- Simple regex patterns

**Phase 4: Advanced Rules**
- Complex conditional logic
- Comprehensive standardization
- Strict validation

### Common Rule Sets

**Basic Rules (Good for Most Teams):**
```
Project Rules:
- Force lowercase: ON
- Space replacement: Underscore
- Prohibited: test, asdf, temp, delete

Standardization:
- fb, Facebook → facebook
- google ads, adwords → google
- email, e-mail → newsletter

Required Fields:
- utm_campaign: minChar 3, maxChar 50
```

**Advanced Rules (For Large Teams):**
```
Project Rules:
- Force lowercase: ON
- Space replacement: Underscore
- Prohibited: test, asdf, temp, delete, xxx, foo, bar

Standardization:
- All social platform variations → standard names
- All medium variations → standard mediums
- Common typos → correct values
- Department prefixes → standardized

Required Fields:
- utm_source: regex ^[a-z_]+$
- utm_medium: Must be from approved list
- utm_campaign: minChar 5, maxChar 50, specific format
- utm_term: Required if utm_medium = cpc
```

### Documentation

**Document Your Rules:**
```
UTM Rules - Company Standards

Automatic Transformations:
- All parameters converted to lowercase
- Spaces replaced with underscores
- Ex: "Facebook Ads" becomes "facebook_ads"

Standard Values:
- utm_source: facebook, instagram, google, linkedin, newsletter
- utm_medium: social, email, cpc, display, referral
- utm_campaign: [campaign_name]_[quarter]_[year]

Required:
- All three core parameters (source, medium, campaign)
- Campaign must be 5-50 characters
- Paid campaigns must include utm_term

Prohibited:
- test, temp, delete, asdf, xxx (use proper values)
```

**Share with Team:**
- Include in onboarding docs
- Post in team wiki
- Review in training
- Regular reminders

### Testing Rules

**Before Rolling Out:**

1. **Create Test Project:**
   - Set up rules in test environment
   - Try various parameter combinations
   - Verify transformations work correctly

2. **Test Edge Cases:**
   - Very long values
   - Special characters
   - Mixed case
   - Empty values
   - Unusual combinations

3. **Team Testing:**
   - Have team members create test links
   - Gather feedback
   - Adjust rules based on input

4. **Gradual Rollout:**
   - Start with one project
   - Monitor for issues
   - Expand to all projects

## Managing Rules

### Editing Rules

**Standardization and Required Field Rules:**
1. Find rule in list
2. Click **Edit**
3. Modify settings
4. Save changes
5. Applies to future links immediately

**Project Rules:**
1. Go to Project Rules tab
2. Update settings
3. Save
4. Applies to all new links in project

### Disabling Rules Temporarily

**Standardization Rules:**
- Toggle **Active** switch to OFF
- Rule stops applying
- Don't need to delete
- Re-enable anytime

**Use Cases:**
- Testing without rule
- Special campaign exception
- Troubleshooting
- Gradual migration

### Deleting Rules

1. Find rule
2. Click **Delete** or trash icon
3. Confirm deletion
4. Rule removed permanently
5. Future links no longer affected

**Note:** Doesn't change existing links

### Rule Priority and Order

**If Multiple Rules Match:**
- Applied in order shown
- First transformation applies
- May affect subsequent rules
- Reorder for different results

**Example:**
```
Rule 1: If contains "fb" → replace with "facebook"
Rule 2: If contains "facebook ads" → replace with "facebook_paid"

Input: "fb ads"
After Rule 1: "facebook ads"
After Rule 2: "facebook_paid"

Final: "facebook_paid"
```

## Troubleshooting

### Rule Not Working

**Check:**
- Is rule active/enabled?
- Does parameter match exactly?
- Is rule order affecting it?
- Are project rules overriding?
- Test with simple case first

### Too Many Transformations

**Problem:** Parameters changed unexpectedly

**Solutions:**
- Review all active rules
- Check rule order
- Disable rules one by one to identify culprit
- Simplify rule logic

### Validation Too Strict

**Problem:** Can't create links due to validation errors

**Solutions:**
- Review required field rules
- Relax character limits
- Simplify regex patterns
- Add exceptions for special cases

### Team Confusion

**Problem:** Team doesn't understand rule errors

**Solutions:**
- Improve error messages
- Document rules clearly
- Provide examples
- Training session
- Create quick reference guide

## Advanced Features

### Conditional Rules

Apply rules only in certain conditions:

```
If utm_medium = "cpc"
Then require utm_term

If utm_campaign starts with "partner_"
Then require custom parameter partner_id

If utm_source = "facebook"
Then utm_content must follow pattern: [ad_type]_[creative_id]
```

### Rule Templates

Save rule sets for reuse:
- Create standard rule set
- Apply to new projects
- Consistent across organization
- Easy setup for new projects

### Bulk Rule Import

Import rules from CSV:
- Migrate rules between projects
- Share rules across team
- Backup and restore
- Standardize enterprise-wide

## Related Documentation

- [Project Rules](/utm-rules/project-rules)
- [Standardization Rules](/utm-rules/standardization-rules)
- [Required Field Rules](/utm-rules/required-fields)
- [UTM Parameters](/utm-parameters/overview)
- [Creating Links](/links/create-link)

## Need Help?

For questions about UTM rules or parameter validation, contact our support team or explore our comprehensive guides.
