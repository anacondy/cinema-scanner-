# Platform Builds Guide

## 📱 Mobile Applications (Android & iOS)

### Overview
Cinematic Archives can be packaged as native mobile applications for Android and iOS using Capacitor, which wraps the web application in a native container while maintaining 60+ FPS performance.

---

## 🤖 Android Build

### Prerequisites
- Node.js 18+
- Android Studio (latest stable version)
- JDK 11 or higher

### Quick Installation Steps

1. **Install Capacitor**
   ```bash
   npm install @capacitor/core @capacitor/cli
   npm install @capacitor/android
   ```

2. **Initialize Capacitor**
   ```bash
   npx cap init "Cinematic Archives" com.cinematicarchives.app
   ```

3. **Build the web assets**
   ```bash
   npm run build
   ```

4. **Add Android platform**
   ```bash
   npx cap add android
   ```

5. **Sync the web code**
   ```bash
   npx cap sync android
   ```

6. **Open in Android Studio**
   ```bash
   npx cap open android
   ```

7. **Build APK in Android Studio**
   - Click `Build` → `Build Bundle(s) / APK(s)` → `Build APK(s)`
   - APK will be located at: `android/app/build/outputs/apk/debug/app-debug.apk`

### Installing APK on Android Device

**Method 1: Direct Installation**
1. Transfer the APK to your Android device
2. Enable "Install from Unknown Sources" in Settings
3. Open the APK file and tap "Install"

**Method 2: ADB Installation**
```bash
adb install android/app/build/outputs/apk/debug/app-debug.apk
```

---

## 🍎 iOS Build

### Prerequisites
- macOS with Xcode 14+
- Apple Developer Account (for distribution)
- CocoaPods

### Quick Installation Steps

1. **Install Capacitor iOS**
   ```bash
   npm install @capacitor/ios
   ```

2. **Add iOS platform**
   ```bash
   npx cap add ios
   ```

3. **Sync the web code**
   ```bash
   npx cap sync ios
   ```

4. **Open in Xcode**
   ```bash
   npx cap open ios
   ```

5. **Build in Xcode**
   - Select your target device or simulator
   - Click Product → Build
   - For distribution, use Product → Archive

### Installing on iOS Device

**Method 1: TestFlight (Recommended)**
1. Archive the app in Xcode
2. Upload to App Store Connect
3. Add as TestFlight build
4. Share the TestFlight link

**Method 2: Direct Installation (Development)**
1. Connect your iOS device
2. Select it in Xcode
3. Click the Run button

---

## 🪟 Windows Desktop Build

### Using Electron

1. **Install Electron**
   ```bash
   npm install --save-dev electron electron-builder
   ```

2. **Create electron configuration**
   
   Create `electron.js`:
   ```javascript
   const { app, BrowserWindow } = require('electron')
   
   function createWindow() {
     const win = new BrowserWindow({
       width: 1280,
       height: 800,
       webPreferences: {
         nodeIntegration: false,
         contextIsolation: true
       }
     })
     
     win.loadFile('dist/index.html')
   }
   
   app.whenReady().then(createWindow)
   ```

3. **Update package.json**
   ```json
   {
     "main": "electron.js",
     "scripts": {
       "electron": "electron .",
       "pack": "electron-builder --dir",
       "dist": "electron-builder"
     },
     "build": {
       "appId": "com.cinematicarchives.app",
       "win": {
         "target": "nsis",
         "icon": "build/icon.ico"
       }
     }
   }
   ```

4. **Build**
   ```bash
   npm run build
   npm run dist
   ```

---

## 🍎 macOS Desktop Build

### Using Electron (same as Windows)

1. **Update build configuration**
   ```json
   {
     "build": {
       "mac": {
         "target": "dmg",
         "icon": "build/icon.icns"
       }
     }
   }
   ```

2. **Build**
   ```bash
   npm run dist
   ```

---

## 📦 Release Preparation

### Before Creating Release

1. ✅ Build all platform versions
2. ✅ Test each build on target platform
3. ✅ Create installation guides
4. ✅ Prepare screenshots and demo videos
5. ✅ Sign builds (for production)

### Creating GitHub Release

1. **Tag the version**
   ```bash
   git tag -a v1.0.0 -m "Release v1.0.0"
   git push origin v1.0.0
   ```

2. **Go to GitHub Releases**
   - Navigate to repository → Releases → Draft a new release

3. **Upload build files**
   - `cinematic-archives-v1.0.0.apk` (Android)
   - `cinematic-archives-v1.0.0.ipa` (iOS)
   - `cinematic-archives-v1.0.0-setup.exe` (Windows)
   - `cinematic-archives-v1.0.0.dmg` (macOS)

4. **Add installation instructions** (see below)

---

## 📖 Installation Instructions for Releases

### Android APK Installation
1. Download `cinematic-archives-v1.0.0.apk`
2. On your Android device, go to Settings → Security
3. Enable "Install from Unknown Sources"
4. Open the downloaded APK file
5. Tap "Install" and follow the prompts
6. Launch the app from your app drawer

**Estimated time:** ~2 minutes

### iOS Installation (TestFlight)
1. Install TestFlight from the App Store
2. Click the TestFlight invitation link
3. Tap "Accept" in TestFlight
4. Tap "Install"
5. Launch from your home screen

**Estimated time:** ~3 minutes

### Windows Installation
1. Download `cinematic-archives-v1.0.0-setup.exe`
2. Double-click the installer
3. Follow the installation wizard
4. Launch from Start Menu

**Estimated time:** ~1 minute

### macOS Installation
1. Download `cinematic-archives-v1.0.0.dmg`
2. Open the DMG file
3. Drag the app to Applications folder
4. Right-click and select "Open" (first time only)
5. Launch from Applications

**Estimated time:** ~1 minute

---

## 🔧 Performance Optimizations for Native Builds

### Mobile-Specific Optimizations

1. **Reduce particle count**
   ```javascript
   const particleCount = 30; // Optimized for mobile
   ```

2. **Disable shadows on low-end devices**
   ```javascript
   const useShadows = window.devicePixelRatio < 2;
   ```

3. **Use native scrolling**
   ```css
   -webkit-overflow-scrolling: touch;
   ```

4. **Enable hardware acceleration**
   ```css
   transform: translateZ(0);
   will-change: transform;
   ```

---

## ✅ Testing Checklist

- [ ] Android 10+ (16:9 and 20:9 screens)
- [ ] iOS 14+ (iPhone and iPad)
- [ ] Windows 10/11
- [ ] macOS Monterey+
- [ ] Performance: 60+ FPS verified
- [ ] Touch interactions working
- [ ] Offline functionality (if applicable)
- [ ] Install/uninstall process smooth

---

## 📊 Build Size Targets

| Platform | Target Size | Actual Size |
|----------|-------------|-------------|
| Android APK | < 50 MB | TBD |
| iOS IPA | < 60 MB | TBD |
| Windows | < 100 MB | TBD |
| macOS | < 100 MB | TBD |

---

## 🔐 Code Signing (Production)

### Android
- Generate keystore
- Sign APK with jarsigner or Android Studio

### iOS
- Requires Apple Developer Account ($99/year)
- Configure provisioning profiles in Xcode

### Windows
- Optional: Sign with Code Signing Certificate

### macOS
- Requires Apple Developer Account
- Sign and notarize with Xcode

---

## 📱 Quick Links

- [Capacitor Documentation](https://capacitorjs.com/)
- [Electron Documentation](https://www.electronjs.org/)
- [Android Studio](https://developer.android.com/studio)
- [Xcode](https://developer.apple.com/xcode/)

---

**Note:** Native builds are currently in development. Check the [Releases](https://github.com/anacondy/cinema-scanner-/releases) page for availability.
