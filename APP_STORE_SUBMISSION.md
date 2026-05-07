# App Store Submission Guide

## Pre-Submission Verification (48 Hours Before)

### ✅ Final Testing Checklist
- [ ] App works on iPhone 12 mini (5.4")
- [ ] App works on iPhone 14 Pro Max (6.7")
- [ ] App works on iPad (if applicable)
- [ ] All interactive elements are tappable (minimum 44x44pt)
- [ ] No hardcoded URLs for testing
- [ ] All API endpoints point to production
- [ ] No console errors or warnings
- [ ] App doesn't request unnecessary permissions
- [ ] All links work (Support URL, Privacy Policy)
- [ ] App doesn't crash during normal use

### 📱 Device Testing
```
Required testing:
✓ Latest iOS version (iOS 17.x)
✓ Minimum supported iOS version (e.g., iOS 13.0)
✓ Multiple device sizes (small, medium, large)
✓ Portrait and landscape orientations
✓ Wifi and cellular networks
```

## Step 1: Create App Store Connect Record

1. Go to [appstoreconnect.apple.com](https://appstoreconnect.apple.com)
2. Sign in with Apple ID
3. Click **Apps** > **+** (New App)
4. Select **iOS**
5. Fill in:
   - **App Name**: `Contractor Connect` (50 characters max)
   - **Bundle ID**: Select from dropdown (must match Xcode)
   - **SKU**: Unique identifier (e.g., `CC-2026-001`)
   - **User Access**: Select availability

```
App Name: Contractor Connect
Bundle ID: com.yourcompany.contractorconnect
SKU: CC-001 (never changes after submission)
```

## Step 2: App Information

Navigate to **App Information** tab:

### Bundled App (Decide)
- [ ] Not bundled (most common)
- [ ] Bundled with other apps (if reselling existing app)

### Category
- Select **Primary Category**: 
  - Business (if contractor/professional tool)
  - Productivity (if organizational)
  - Lifestyle (if general)
- Optional **Secondary Category** (not required)

### App Icon
- [ ] Upload 1024×1024 PNG (App Store display)
- [ ] No rounded corners (system adds them)
- [ ] No transparency required
- [ ] No text on icon
- [ ] Colors should be vibrant and distinguishable

### App Logo (Optional)
- 1200×628 PNG
- Used for marketing materials

## Step 3: Pricing & Availability

1. Click **Pricing and Availability**
2. Select **Pricing Tier**:
   - **Free** (no payment required)
   - **Paid** ($0.99 - $999.99)
   - **Subscription** (recurring billing)

3. Select **Countries/Regions** where app is available
   - Start with all regions if possible
   - Can remove later

4. Release Date:
   - **Manual Release** (release after approval, good for first launch)
   - **Automatic Release** (release immediately after approval)

```
Recommendation for first app: Manual Release
This lets you prepare marketing materials before going live
```

## Step 4: Screenshots & Preview

### Screenshots
Required for each device type. Prepare:

| Device | Dimensions | Count |
|--------|-----------|-------|
| iPhone 6.7" | 1284×2778 | 2-10 |
| iPhone 5.5" | 1242×2208 | 2-10 |
| iPad Pro | 2048×2732 | Optional |

**Best Practices:**
- Show key features first
- Add text overlay describing feature (e.g., "Manage Contractors")
- Use consistent branding
- No watermarks or logos only
- Make them visually compelling

**Tools for creating screenshots:**
- Figma (free design)
- Sketch (paid but professional)
- Screenshot on device + annotation

### Preview Video (Optional)
- 15-30 seconds max
- MP4 format
- Shows app in action
- No audio watermark required

## Step 5: Description & Keywords

Navigate to **App Description**:

### Description (4,000 characters max)
```
Write compelling description covering:
1. What the app does (first 2 sentences)
2. Key features (3-5 bullet points)
3. Who it's for
4. Any requirements or setup

Example:
Contractor Connect makes managing your contractor team easy.
- Schedule assignments in minutes
- Track progress in real-time
- Invoice directly through the app
- Built for small business owners

Perfect for general contractors, landscapers, and trades professionals.
```

### Keywords (100 characters max, comma-separated)
```
Examples:
contractor, scheduling, management, business, team, crew, tracking, 
fieldwork, construction, labor, assignments
```

**Pro Tips:**
- Use high-volume keywords (research with ASO tools)
- Include long-tail keywords (less competitive)
- Don't repeat keywords
- Think like a user searching for this app

### Support URL
- Must be HTTPS
- Should have app support contact info
- Example: `https://yourcompany.com/support`

### Privacy Policy URL
- **REQUIRED by Apple**
- Must be HTTPS
- Should clearly state:
  - What data you collect
  - How you use it
  - How users can delete their data
  - Third-party SDKs used

## Step 6: Age Rating

1. Click **Age Rating**
2. Complete questionnaire
3. Answer about app content:
   - Violence
   - Sexual content
   - Drugs/alcohol
   - Horror/fear themes
   - Gameplay modes
   - etc.

```
Recommended: Rate honestly for broader appeal
Most productivity apps get: 4+
```

## Step 7: Content Rights

1. Check **Content Rights**
2. Certify that:
   - [ ] You own/have rights to all content
   - [ ] You have rights to all SDKs used
   - [ ] You have rights to all APIs used

## Step 8: Build Upload

### Prepare Build
1. Open Xcode project
2. **Product** > **Archive**
3. Wait for archive to complete
4. **Organizer** opens automatically

### Validate Archive
1. Select your archive
2. Click **Validate**
3. Choose team
4. Check for errors

### Upload Build
1. Select archive in Organizer
2. Click **Distribute App**
3. Select **App Store Connect**
4. Click **Upload**
5. Select signing options
6. Wait for upload to complete (5-10 minutes)

## Step 9: Version Information

Once build uploads, return to App Store Connect:

### Version Release
1. Click **App Review Information** section
2. Fill in:
   - **Version Number**: Must match Xcode (e.g., 1.0.0)
   - **Build**: Select your uploaded build
   - **Release Type**: New app, update, etc.

### Demo Account (if needed)
If app requires login:
```
Test Account Email: demo@testapp.com
Test Account Password: [secure password]
```
Provide working demo account for Apple reviewers

### Notes for Reviewer
Optional but helpful:
```
"First version of Contractor Connect app. 
Demonstrates contractor scheduling and time tracking. 
No special hardware required. Demo account above."
```

### Routing Information
- [ ] **First Contact** - Who should Apple contact with issues
- [ ] **Reviewer Contact** - Sometimes separate from first
- [ ] Both: name, email, phone

## Step 10: Attachments (Optional)
- Screenshots of onboarding (if complex)
- Demo videos
- Marketing materials
- Architecture diagrams

## Step 11: Review Information

### App Review Information
Fill in all sections:
- [ ] **Primary Category**: Select accurate category
- [ ] **Secondary Category**: Optional
- [ ] **Questions & Answers**: 
  - Does your app provide access to protected health information?
  - Does your app provide features for managing a household?
  - etc.

## Step 12: Submit for Review

1. Review all sections in App Store Connect
2. Ensure nothing is red/incomplete
3. Click **Submit for Review**
4. Confirm submission

```
✅ App submitted for review!
Expected timeline: 24-48 hours
```

## What to Do While Waiting for Review

- [ ] Prepare App Store listing (banner, social media)
- [ ] Create press release
- [ ] Set up social media promotion
- [ ] Prepare launch email
- [ ] Create welcome guide/FAQ
- [ ] Set up customer support channel
- [ ] Monitor App Store Connect for status updates

## Common Rejection Reasons & Fixes

### ❌ "App functionality is not accurate"
**Cause:** App description doesn't match functionality
**Fix:** Ensure app does exactly what description says

### ❌ "Guideline 1.1 - Safety - Objectionable Content"
**Cause:** Content violates Apple guidelines
**Fix:** Remove offensive content, moderate user-generated content

### ❌ "Guideline 2.1 - Information Needed"
**Cause:** Apple reviewer couldn't test certain features
**Fix:** Provide demo account, explain how to test

### ❌ "Guideline 4.3 - Design - Minimum Functionality"
**Cause:** App is too simple or incomplete
**Fix:** Add meaningful features, ensure full functionality

### ❌ "Guideline 5.1 - Legal - Privacy"
**Cause:** Missing or incomplete privacy policy
**Fix:** Create detailed, accessible privacy policy

### ❌ "Guideline 3.1.1 - Business - Payments"
**Cause:** Asking users to pay outside the app
**Fix:** Use In-App Purchase for all payments (required by Apple)

## Approval Timeline

| Status | Timeline | Action |
|--------|----------|--------|
| Waiting for Review | Queued | Monitor for changes |
| In Review | 1-2 days | Prepare for launch |
| Rejected | 24-48 hours after | Fix issues, resubmit |
| Approved | 24 hours | Set release date |
| Ready for Sale | After 24 hours | Congratulations! 🎉 |

## After Approval

### 🚀 Launch Day
1. Set manual release date/time
2. Send press release
3. Post on social media
4. Email newsletter
5. Start marketing campaign

### 📊 Post-Launch
- Monitor app reviews and ratings
- Respond to user feedback
- Track analytics
- Plan first update (usually 2-4 weeks)

## Resubmission Process

If rejected, Apple will provide detailed feedback:

1. **Read rejection reason carefully**
2. **Make required changes**
3. **Increment Build number** (e.g., 1 → 2)
4. **Increment Version if significant update** (e.g., 1.0.0 → 1.0.1)
5. **Archive and upload new build**
6. **Resubmit for review**

```
Average resubmission: 1-2 attempts
Don't argue with Apple - just fix the issues
```

## Resources

- [App Store Review Guidelines](https://developer.apple.com/app-store/review/guidelines/)
- [App Store Connect Help](https://help.apple.com/app-store-connect/)
- [App Store Optimization Guide](https://help.apple.com/app-store-connect/en.lproj/static.html?#/dev7087a56ce)
- [Apple Human Interface Guidelines](https://developer.apple.com/design/human-interface-guidelines/)

## Success Checklist

Before you submit:
- [ ] All sections complete (no red warnings)
- [ ] Screenshots look professional
- [ ] Description is compelling
- [ ] Keywords are relevant
- [ ] Privacy policy URL works
- [ ] Support URL works
- [ ] Pricing/availability selected
- [ ] Build uploaded and selected
- [ ] Age rating completed
- [ ] Content rights certified
- [ ] Tested on real device
- [ ] No test data in production

**Good luck with your app launch! 🎊**
