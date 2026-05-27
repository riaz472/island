# Island - Android App

## Project Overview

Island is an Android application that leverages Android's "Managed Profile" (Work Profile) and "Device Owner" features to sandbox applications. Developed by Oasisfeng (also known for Greenify).

## Tech Stack

- **Languages:** Java, Kotlin, AIDL
- **Platform:** Android (minSdkVersion 24 / Android 7.0)
- **Build System:** Gradle (Android Gradle Plugin 4.1.3)
- **Key Libraries:** AndroidX, Firebase/Crashlytics, OkHttp, libsuperuser

## Project Structure

- `assembly/` — Build portal; uses Gradle product flavors (`complete`, `engine`, `mobile`, `fileprovider`) to produce different APK variants
- `engine/` — Core DPC (Device Policy Controller) logic, managed profile provisioning and sandboxing
- `mobile/` — User-facing Android UI (main activity, settings, app management)
- `shared/` — Shared code, utilities, models, and AIDL IPC definitions
- `fileprovider/` — Cross-profile/cross-app file sharing
- `installer/` — In-sandbox app installation
- `watcher/` — App state/installation monitoring
- `open/` — Open API implementations for 3rd-party app integration

## Build Instructions

This project requires:
1. **Android SDK** (not available in Replit)
2. The **deagle** companion library cloned alongside this repo:
   ```
   -- (parent dir)
     - island/   ← this repo
     - deagle/   ← https://github.com/oasisfeng/deagle
   ```
3. Build via: `./gradlew :assembly:assembleComplete`

## Important Note

**This project cannot be previewed or run in Replit.** It is a native Android app that must be compiled with the Android SDK and run on an Android device or emulator. Use Android Studio or a CI/CD service like Codemagic (see `codemagic.yaml`) to build APKs.

## User Preferences

- Follow existing Gradle/Android project conventions
