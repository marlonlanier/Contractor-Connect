# Xcode Setup for App Store Submission

## Prerequisites
- Xcode 14.0 or later
- Macbook with latest OS
- Apple Developer Account ($99/year)
- iOS app project ready to build

## Step 1: Configure Bundle ID

1. Open your project in Xcode
2. Select **Targets** > **General**
3. Set **Bundle Identifier**:
   ```
   Example: com.yourcompany.contractorconnect
   Format: com.<company>.<appname> (no spaces, lowercase)
   ```
4. Verify it matches what you'll use in App Store Connect

## Step 2: Set Version & Build Numbers

1. In **Targets** > **General** tab:
   - **Version** (Marketing Version): `1.0.0`
   - **Build** (Build Version): `1` (increment for each submission)
   
2. Follow semantic versioning:
   - `1.0.0` = Major.Minor.Patch
   - `1.0.1` = Bug fix
   - `1.1.0` = New feature (backward compatible)
   - `2.0.0` = Major breaking changes

3. Each App Store submission needs unique Build number

## Step 3: Create Distribution Certificate

1. Go to [developer.apple.com](https://developer.apple.com)
2. Sign in with Apple ID
3. Navigate to **Certificates, Identifiers & Profiles** > **Certificates**
4. Click **+** to create new certificate
5. Select **iOS Distribution (App Store and Ad Hoc)**
6. Follow certificate signing request (CSR) process:
   - Open **Keychain Access** on Mac
   - **Keychain Access** > **Certificate Assistant** > **Request a Certificate from a Certificate Authority**
   - Email: Your Apple ID email
   - Common Name: Your name
   - Uncheck "Email to"
   - Save to disk
7. Upload CSR file to Apple Developer
8. Download certificate (`.cer` file)
9. Double-click to install in Keychain

## Step 4: Create App Store Provisioning Profile

1. In **Certificates, Identifiers & Profiles** > **Identifiers**
2. Click **+** to create App ID:
   - Description: "Contractor Connect"
   - Bundle ID: `com.yourcompany.contractorconnect` (match Xcode)
   - Select capabilities needed (Push Notifications, Sign In with Apple, etc.)
   - Click **Continue** > **Register**

3. Now create provisioning profile:
   - Go to **Profiles** > **+**
   - Select **App Store**
   - Select your App ID
   - Select Distribution Certificate
   - Name it: `Contractor Connect App Store`
   - Download profile (`.mobileprovision` file)
   - Double-click to install

## Step 5: Configure Signing in Xcode

1. Select your **Project** (not Target)
2. Go to **Signing & Capabilities**
3. Select your target
4. Set **Team** to your Apple Developer team
5. Ensure **Provisioning Profile** shows your distribution profile
6. Check **Signing Certificate** is correct

```
Team: Your Team Name
Signing Certificate: iOS Distribution (...)
Provisioning Profile: Contractor Connect App Store
```

## Step 6: Build Settings Verification

1. Select **Build Settings** tab
2. Search for these values and verify:

| Setting | Value |
|---------|-------|
| Code Sign Identity | Apple Distribution |
| Provisioning Profile | Contractor Connect App Store |
| Team ID | Your Team ID |
| Bundle Identifier | com.yourcompany.contractorconnect |
| Deployment Target | iOS 13.0+ (or your minimum) |

## Step 7: Prepare for App Store Build

### Remove Debug Settings
```swift
// Remove or comment out:
#if DEBUG
print("Debug logging")
#endif
```

### Remove Test Code
- Delete test endpoints or feature flags
- Remove mock data hardcoding
- Use production API endpoints

### Check Deployment Target
1. In **Build Settings** > search "Deployment Target"
2. Ensure it matches your minimum iOS version
3. Test on that iOS version

## Step 8: Archive Your App

1. **Product** > **Scheme** > **Edit Scheme**
2. Select **Run** tab > ensure **Build Configuration** is "Release"
3. Close scheme editor
4. **Product** > **Archive**

```
Wait for Xcode to build and archive...
Organizer window opens automatically
```

### Troubleshooting Archive Issues

| Error | Solution |
|-------|----------|
| "No provisioning profiles found" | Download profile from Apple Developer, restart Xcode |
| "Code Sign Error" | Check certificate is installed in Keychain Access |
| "Unable to validate entitlements" | Verify capabilities match your provisioning profile |
| "Missing required entitlements" | Add missing capabilities in Xcode |

## Step 9: Validate Archive

1. In **Organizer** window, select your archive
2. Click **Validate**
3. Select team and signing credentials
4. Wait for validation to complete

```
✅ Validation successful = Ready to upload
❌ Validation failed = Fix errors before uploading
```

## Step 10: Upload to App Store

### Option A: Using Xcode
1. In **Organizer**, select archive
2. Click **Distribute App**
3. Select **App Store Connect**
4. Select **Upload**
5. Choose signing options and upload

### Option B: Using Transporter (Recommended for large apps)
```bash
# Download Transporter from Mac App Store
# Or use:
xcrun altool --upload-app -f path/to/app.ipa \
  -t ios -u apple_id@example.com -p app-specific-password
```

## Useful Xcode Commands

```bash
# Build for App Store
xcodebuild -scheme YourApp -configuration Release \
  -archivePath build/YourApp.xcarchive archive

# Create IPA from archive
xcodebuild -exportArchive -archivePath build/YourApp.xcarchive \
  -exportPath build/YourApp.ipa \
  -exportOptionsPlist exportOptions.plist

# List signing identities
security find-identity -v -p codesigning

# Check provisioning profiles
security cms -D -i ~/Library/MobileDevice/Provisioning\ Profiles/PROFILE_UUID.mobileprovision
```

## Common Issues & Solutions

### "Code Sign Error: The identity used to sign the executable is no longer valid"
**Fix:**
1. Delete derived data: `rm -rf ~/Library/Developer/Xcode/DerivedData/*`
2. Restart Xcode
3. Verify certificate in Keychain Access

### "No code signing identities found"
**Fix:**
1. Download distribution certificate from Apple Developer
2. Double-click `.cer` file to install
3. Restart Xcode
4. Check **Signing & Capabilities** settings

### "Provisioning profile doesn't include signing certificate"
**Fix:**
1. Delete old provisioning profile
2. Create new one in Apple Developer
3. Download and install new profile
4. Update Xcode project settings

### "The specified item could not be found in the keychain"
**Fix:**
```bash
# Restart Xcode and try again
# If persists: open Keychain Access > check certificate exists
# Re-download certificate from Apple Developer
```

## Deployment Target Guidance

Choose based on your target audience:

| Target | Usage | App Size Impact |
|--------|-------|-----------------|
| iOS 13.0+ | Oldest devices (iPhone 6s, 2015 iPad Air 2) | Smaller |
| iOS 14.0+ | Most users, better security | Small |
| iOS 15.0+ | Latest features, high security | Better performance |
| iOS 16.0+ | Newest features only | Smallest |

**Recommendation:** iOS 14.0+ covers ~90% of active devices

## Pre-Submission Checklist

- [ ] Version number updated (e.g., 1.0.0)
- [ ] Build number incremented
- [ ] All certificates and profiles installed
- [ ] Xcode shows correct signing team
- [ ] Archive builds successfully
- [ ] Validation passes without errors
- [ ] No debug code or test endpoints
- [ ] App runs on physical device (not just simulator)
- [ ] All links verified (privacy policy, support)
- [ ] Screenshots prepared and accurate

## Resources

- [Apple Code Signing Guide](https://developer.apple.com/support/code-signing/)
- [Xcode Build System](https://help.apple.com/xcode/mac/current/#/devc8c2a6be1)
- [Provisioning Profiles](https://developer.apple.com/account/resources/profiles/list)
- [Certificates](https://developer.apple.com/account/resources/certificates/list)
