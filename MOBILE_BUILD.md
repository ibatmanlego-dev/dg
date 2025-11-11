# VibeTracker Mobile App Build Instructions

## 📱 Building Native Android & iOS Apps

VibeTracker has been configured to build native mobile apps using Capacitor. Follow these instructions to create APK and IPA files.

## 🛠️ Prerequisites

### For Android:
- Android Studio installed
- Android SDK configured
- Java Development Kit (JDK) 11 or higher
- An Android device or emulator for testing

### For iOS:
- macOS with Xcode installed
- Apple Developer Account (for distribution)
- iOS device for testing

## 🚀 Quick Build Commands

### Android Development Build:
```bash
# Build and run on connected device/emulator
npm run mobile:dev
```

### Android Production Build:
```bash
# Build for production
npm run mobile:build
```

### Manual Build Steps:

1. **Build the web app:**
```bash
npm run build
```

2. **Sync with Capacitor:**
```bash
npx cap sync
```

3. **Open Android Studio:**
```bash
npx cap open android
```

4. **In Android Studio:**
   - Wait for Gradle sync to complete
   - Build > Build Bundle(s) / APK(s) > Build APK(s)
   - Or Build > Build Bundle(s) / APK(s) > Build Bundle(s)

### iOS Build:
```bash
# Open Xcode
npx cap open ios

# In Xcode:
# 1. Select your team in Project Settings
# 2. Choose your target device/simulator
# 3. Product > Run (for testing)
# 4. Product > Archive (for distribution)
```

## 📋 Available Scripts

| Script | Description |
|--------|-------------|
| `npm run build` | Build Next.js app for production |
| `npm run build:mobile` | Build and sync for mobile |
| `npm run cap:sync` | Sync web assets with native platforms |
| `npm run cap:open:android` | Open Android Studio |
| `npm run cap:open:ios` | Open Xcode |
| `npm run cap:run:android` | Run on connected Android device |
| `npm run cap:run:ios` | Run on connected iOS device |
| `npm run cap:build:android` | Build Android APK/IPA |
| `npm run cap:build:ios` | Build iOS IPA |

## 🎨 App Assets

- **App Icon:** `/public/icon.png` (1024x1024)
- **Splash Screen:** `/public/splash.png` (1024x1024)
- **Logo:** `/public/logo.png` (1024x1024)

## 📱 Mobile Features Enabled

### ✅ Capacitor Plugins:
- **Camera:** Photo capture and gallery access
- **Filesystem:** Local file storage
- **Haptics:** Touch feedback
- **Local Notifications:** Push notifications
- **Preferences:** Native storage
- **Splash Screen:** Custom launch screen
- **Status Bar:** Custom status bar styling

### 🔧 Mobile Optimizations:
- Responsive design for mobile screens
- Touch-friendly interface
- Native navigation patterns
- Offline-first architecture
- Performance optimizations

## 🏗️ Project Structure

```
├── android/                 # Android native project
├── ios/                     # iOS native project
├── src/
│   ├── components/mobile/   # Mobile-specific components
│   ├── hooks/use-capacitor.ts # Capacitor hooks
│   └── ...
├── public/
│   ├── icon.png            # App icon
│   ├── splash.png          # Splash screen
│   └── ...
└── capacitor.config.ts     # Capacitor configuration
```

## 📝 Configuration

### App Configuration (`capacitor.config.ts`):
- **App ID:** `com.vibetracker.app`
- **App Name:** `VibeTracker`
- **Web Directory:** `out`
- **Plugins:** Camera, Notifications, Haptics, etc.

### Android Configuration:
- Target SDK: 34 (Android 14)
- Min SDK: 21 (Android 5.0)
- Permissions: Camera, Storage, Notifications

### iOS Configuration:
- Deployment Target: iOS 13.0
- Permissions: Camera, Photos, Notifications

## 🚀 Deployment

### Android (Google Play Store):
1. Build signed APK or AAB
2. Create Google Play Console account
3. Upload app bundle
4. Complete store listing
5. Submit for review

### iOS (App Store):
1. Archive app in Xcode
2. Upload to App Store Connect
3. Complete app information
4. Submit for review

## 🔍 Testing

### Android Testing:
```bash
# Run on connected device
npx cap run android

# Run on emulator
# Make sure emulator is running first
npx cap run android
```

### iOS Testing:
```bash
# Run on connected device
npx cap run ios

# Run on simulator
npx cap run ios
```

## 🐛 Troubleshooting

### Common Issues:

1. **Build fails with Gradle errors:**
   - Check Android SDK installation
   - Update Gradle wrapper
   - Clean and rebuild project

2. **Capacitor sync fails:**
   - Run `npm run build` first
   - Check `capacitor.config.ts` settings
   - Ensure `out` directory exists

3. **App crashes on launch:**
   - Check console logs in Android Studio/Xcode
   - Verify all Capacitor plugins are properly installed
   - Check for missing permissions

4. **Icons not showing:**
   - Regenerate icons with proper sizes
   - Run `npx cap sync` after updating assets
   - Check native project resources

## 📞 Support

For issues with:
- **Capacitor:** https://capacitorjs.com/docs
- **Android Studio:** https://developer.android.com/studio
- **Xcode:** https://developer.apple.com/xcode/

---

🎉 **Your VibeTracker mobile app is ready to build!**