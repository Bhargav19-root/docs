# QR Codes

Learn how to generate and customize QR codes for your links in LinkUTM.

## Overview

QR (Quick Response) codes bridge the gap between offline and online marketing. LinkUTM allows you to generate scannable QR codes for any link, making it easy to track offline campaigns and provide instant mobile access to your content.

## Why Use QR Codes?

### Benefits

**Bridge Offline to Online**
- Connect print materials to digital content
- Track offline marketing effectiveness
- Seamless mobile experience

**Easy Mobile Access**
- No typing required
- Instant access via phone camera
- Works on all modern smartphones

**Versatile Applications**
- Print advertising
- Product packaging
- Event materials
- Business cards
- Retail displays

**Trackable Offline Marketing**
- Measure print ad performance
- Track event engagement
- Analyze location-based campaigns
- Full analytics like regular links

## Generating QR Codes

### During Link Creation

1. Create a new link with UTM parameters
2. Save the link
3. Find the QR code icon or **Generate QR Code** button
4. QR code is automatically created
5. Download or copy for use

### For Existing Links

1. Go to your **Links** page
2. Find the link you want a QR code for
3. Click **QR Code** icon or option
4. QR code generates instantly
5. Download in preferred format

### QR Code Generation Options

**Automatic:**
- Every link can have a QR code
- Generated on-demand
- Encodes your short link (recommended) or full URL
- Instant availability

**Customization (if available):**
- Size adjustment
- Color selection
- Logo embedding
- Error correction level
- File format (PNG, SVG, PDF)

## QR Code Best Practices

### Technical Specifications

**Size Recommendations:**
- **Minimum print size**: 1 x 1 inch (2.5 x 2.5 cm)
- **Recommended**: 1.5 x 1.5 inches or larger
- **Rule of thumb**: Scanning distance ÷ 10 = minimum size
- **Example**: Viewable from 10 feet away = 1-inch QR code minimum

**Resolution:**
- **Print**: 300 DPI minimum
- **Digital screens**: High resolution PNG
- **Large format (billboards)**: Vector (SVG) format

**Contrast:**
- Dark QR code on light background (traditional)
- High contrast for easy scanning
- Avoid low contrast combinations

### Design Considerations

**Placement:**
- Eye-level when possible
- Flat surface (not curved or wrinkled)
- Well-lit areas
- Accessible without obstruction

**Clear Call-to-Action:**
- Don't assume people know what to do
- Add text: "Scan to learn more"
- Include brief description of destination
- Consider adding instructions for first-time users

**White Space:**
- Include "quiet zone" around QR code
- Minimum 4 modules width of white space
- Prevents scanning errors
- Improves reliability

**Testing:**
- Test with multiple devices
- Test in actual placement location
- Test under expected lighting
- Test from expected distance

## Common Use Cases

### 1. Print Advertising

**Magazine Ads:**
```
Setup:
- Destination: Product landing page
- utm_source: magazine_name
- utm_medium: print
- utm_campaign: spring_2024
- QR Code: 1.5" x 1.5" in ad corner

Call-to-Action: "Scan to shop the collection"
```

**Newspaper Ads:**
```
Setup:
- Destination: Special offer page
- utm_source: local_newspaper
- utm_medium: print
- utm_campaign: weekend_ad
- QR Code: Prominent placement

Call-to-Action: "Scan for exclusive 20% off"
```

**Billboards:**
```
Setup:
- Destination: Simple landing page
- utm_source: billboard_location
- utm_medium: outdoor
- utm_campaign: highway_101
- QR Code: Very large (visible from car)

Call-to-Action: "Scan at stoplight" or "Scan for more info"
Note: Keep destination simple for safety
```

### 2. Product Packaging

```
Setup:
- Destination: Product information, manuals, or tutorials
- utm_source: product_packaging
- utm_medium: qr_code
- utm_campaign: product_name
- QR Code: On packaging, label, or tag

Purpose:
- User manuals
- Assembly instructions
- Recipe ideas
- Product registration
- Warranty information
```

### 3. Business Cards

```
Setup:
- Destination: Digital business card or portfolio
- utm_source: business_card
- utm_medium: qr_code
- utm_campaign: networking
- QR Code: Back of card

Benefits:
- Instant contact info save
- Link to portfolio or LinkedIn
- Trackable networking
- Eco-friendly alternative
```

### 4. Event Marketing

**Event Check-In:**
```
Setup:
- Destination: Event registration or check-in
- utm_source: event_name
- utm_medium: qr_code
- utm_campaign: event_2024
- QR Code: On badges, posters, signage

Use: Quick check-in, schedule access, networking
```

**Event Promotion:**
```
Setup:
- Destination: Event registration page
- utm_source: event_flyer
- utm_medium: print
- utm_campaign: conference_2024
- QR Code: On promotional materials

Use: Easy registration, ticket purchases
```

**Booth Materials:**
```
Setup:
- Destination: Lead capture or demo request
- utm_source: trade_show_name
- utm_medium: booth_qr
- utm_campaign: booth_123
- QR Code: At booth, on swag

Use: Collect leads, schedule demos
```

### 5. Retail & Point of Sale

**In-Store Displays:**
```
Setup:
- Destination: Product details or reviews
- utm_source: retail_display
- utm_medium: qr_code
- utm_campaign: store_location
- QR Code: On shelf talkers, displays

Purpose: Additional product info, reviews, comparisons
```

**Window Displays:**
```
Setup:
- Destination: Online shop or appointment booking
- utm_source: window_display
- utm_medium: qr_code
- utm_campaign: store_front
- QR Code: Visible from street

Purpose: 24/7 shopping access, appointments
```

**Receipt/Packaging:**
```
Setup:
- Destination: Review request, loyalty program
- utm_source: receipt
- utm_medium: qr_code
- utm_campaign: post_purchase
- QR Code: On receipt or thank you card

Purpose: Reviews, loyalty signup, repeat business
```

### 6. Restaurant & Hospitality

**Digital Menus:**
```
Setup:
- Destination: Online menu
- utm_source: table_qr
- utm_medium: qr_code
- utm_campaign: contactless_menu
- QR Code: On table tents, coasters

Purpose: Contactless menus, ordering, payment
```

**Ordering Systems:**
```
Setup:
- Destination: Online ordering system
- utm_source: restaurant_table
- utm_medium: qr_code
- utm_campaign: table_number
- QR Code: Unique per table

Purpose: Self-service ordering and payment
```

### 7. Real Estate

```
Setup:
- Destination: Property details, virtual tour
- utm_source: yard_sign
- utm_medium: qr_code
- utm_campaign: property_address
- QR Code: On yard sign, flyer

Purpose: 24/7 property information access
Call-to-Action: "Scan for virtual tour"
```

### 8. Education

```
Setup:
- Destination: Course materials, resources
- utm_source: textbook
- utm_medium: qr_code
- utm_campaign: chapter_3
- QR Code: In textbooks, worksheets

Purpose: Supplemental content, videos, quizzes
```

## QR Code + LinkUTM Features

### QR Codes + Short Links

**Best Practice:**
- Always generate QR code from short link
- Simpler QR pattern
- Easier to scan
- More reliable

**Comparison:**
```
Full URL QR: Complex, dense pattern
Short URL QR: Simple, cleaner pattern
Result: Better scan success rate
```

[Learn about link shortening →](/links/short-link)

### QR Codes + UTM Parameters

**Tracking Power:**
- All UTM parameters tracked even from QR scans
- Identify offline source precisely
- Measure offline campaign ROI
- Compare offline vs online channels

**Example:**
```
Billboard QR code:
utm_source: billboard
utm_medium: outdoor
utm_campaign: highway_101_north
utm_content: location_mile_marker_45

Track: Which billboard locations perform best
```

[Learn about UTM parameters →](/links/utm-builder)

### QR Codes + Link Expiration

**Time-Limited QR Campaigns:**
- QR codes for limited-time offers
- Event-specific QR codes that expire
- Automatic deactivation

**Example:**
```
Event registration QR:
- Expires: Day before event
- Redirect: Event information page
- Prevents late registrations
```

[Learn about link expiration →](/links/link-expiration)

### QR Codes + Password Protection

**Secure QR Access:**
- Generate QR code for protected link
- User scans, then enters password
- Perfect for exclusive access

**Example:**
```
VIP event QR:
- QR on VIP invitation
- Password required after scan
- Restricts access to invited only
```

[Learn about password protection →](/links/password-protected)

### QR Codes + Analytics

**Track Everything:**
- Total scans
- Scan location (geographic)
- Device types (iOS vs Android)
- Time of day patterns
- Scan-to-conversion rate

**Insights:**
- Which print materials drive most scans
- Best times for offline engagement
- Location-based performance
- Mobile device preferences

[Learn about analytics →](/analytics/link-analytics)

## Downloading QR Codes

### File Formats

**PNG (Raster)**
- Best for: Digital use, social media, web
- Resolution: 300+ DPI for print
- Pros: Universal compatibility
- Cons: Pixelated if enlarged too much

**SVG (Vector)**
- Best for: Print, scalable designs, billboards
- Resolution: Scales infinitely
- Pros: Perfect for any size
- Cons: May need design software to edit

**PDF**
- Best for: Sending to printers, professional printing
- High quality
- Easy to share
- Print-ready

**JPG**
- Best for: Digital use where file size matters
- Compressed format
- Smaller file size
- Slightly lower quality than PNG

### Size Selection

**Small (300x300px):**
- Digital use only
- Emails, social media
- Not recommended for print

**Medium (600x600px to 1000x1000px):**
- Business cards
- Small print materials
- Digital displays

**Large (1500x1500px to 3000x3000px):**
- Large print materials
- Posters, banners
- Professional printing

**Vector (SVG):**
- Any size needed
- Billboards, large format
- Maximum flexibility

## QR Code Customization

### Basic Customization

**Size:**
- Adjust dimensions for your use case
- Maintain square aspect ratio
- Consider viewing distance

**Color:**
- Traditional: Black on white
- Brand colors: Dark on light
- Ensure high contrast
- Test before printing

**Logo Embedding (if available):**
- Add your logo to QR center
- Increases brand recognition
- Maintains scannability with error correction
- Keep logo small (10-30% of QR area)

### Advanced Customization

**Error Correction Levels:**
- L (Low): 7% recovery
- M (Medium): 15% recovery
- Q (Quartile): 25% recovery
- H (High): 30% recovery

Higher error correction = more data redundancy = more complex pattern

**When to Use High Error Correction:**
- Logo embedding
- Potential damage or wear
- Curved or irregular surfaces
- Critical use cases

## QR Code Best Practices Summary

✅ **DO:**
- Use short links for simpler QR patterns
- Include clear call-to-action
- Test on multiple devices before printing
- Ensure adequate size for viewing distance
- Use high contrast colors
- Include white space (quiet zone)
- Track with UTM parameters
- Download high resolution for print

❌ **DON'T:**
- Make QR codes too small
- Use low contrast colors
- Place on curved or wrinkled surfaces
- Assume everyone knows how to scan
- Skip testing before mass printing
- Use full URLs when short links available
- Forget about lighting conditions
- Place in hard-to-reach locations

## Troubleshooting

### QR Code Won't Scan

**Possible Issues:**

1. **Too Small**
   - Solution: Increase size, minimum 1" x 1"

2. **Low Contrast**
   - Solution: Use darker QR on lighter background

3. **Poor Printing Quality**
   - Solution: Use higher resolution file (300 DPI+)

4. **Damaged or Dirty**
   - Solution: Reprint, protect from wear

5. **Poor Lighting**
   - Solution: Improve lighting, use flash

6. **Curved Surface**
   - Solution: Place on flat surface when possible

7. **Wrong Format**
   - Solution: Use standard QR format, not custom

### Low Scan Rates

**Possible Reasons:**

1. **No Call-to-Action**
   - Solution: Add "Scan me" text and benefit

2. **Poor Placement**
   - Solution: Move to eye level, high-traffic area

3. **No Context**
   - Solution: Explain what happens after scan

4. **Not Mobile-Optimized Destination**
   - Solution: Ensure landing page is mobile-friendly

5. **Dead/Expired Link**
   - Solution: Check link status, extend expiration

### QR Code Works But No Analytics Data

**Possible Issues:**

1. **Analytics Not Enabled**
   - Solution: Verify tracking is active

2. **Wrong Link Used**
   - Solution: Ensure using LinkUTM generated link

3. **Data Delay**
   - Solution: Wait 24 hours for data processing

## Related Documentation

- [Creating Links](/links/create-link)
- [Link Shortening](/links/short-link)
- [UTM Parameters](/links/utm-builder)
- [Link Analytics](/analytics/link-analytics)
- [Link Expiration](/links/link-expiration)
- [Password Protection](/links/password-protected)

## Need Help?

For questions about QR codes or offline tracking, contact our support team.
