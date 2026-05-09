# Wither Launcher

## Project Overview

Wither Launcher is a Minecraft: Java Edition launcher for Android devices. It is an Android app (APK) built with Gradle, based on [Boardwalk](https://github.com/zhuowei/Boardwalk), and supports nearly all Minecraft versions from rd-132211 to 1.21 snapshots.

## Project Structure

- `app_pojavlauncher/` — Main Android application module (Java + JNI/C/C++)
- `jre_lwjgl3glfw/` — LWJGL3 GLFW stub for the JRE
- `arc_dns_injector/` — DNS injection helper library
- `forge_installer/` — Headless Forge mod installer
- `scripts/` — Build helper scripts (language list updater, patch scripts)
- `gradle/` — Gradle wrapper
- `build.gradle` — Root Gradle build file
- `settings.gradle` — Gradle settings (multi-module project)

## Build System

- **Language:** Java + C/C++ (JNI/NDK)
- **Build Tool:** Gradle (via `./gradlew`)
- **Android SDK:** compileSdk 34, minSdk 21
- **NDK Version:** 25.2.9519653
- **Java Source Compatibility:** Java 8

## Building the APK

This project requires Android SDK and NDK to build. It **cannot** be built or run in the Replit environment because Android SDK/NDK/emulator are not available here.

To build locally or in CI:

1. Clone the repository
2. Run the language list generator:
   ```bash
   chmod +x scripts/languagelist_updater.sh
   bash scripts/languagelist_updater.sh
   ```
3. Build the debug APK:
   ```bash
   ./gradlew :app_pojavlauncher:assembleDebug
   ```
4. The APK will be at: `app_pojavlauncher/build/outputs/apk/debug/`

## Environment

- Replit modules: `java-graalvm22.3`, `bash`
- This is a **code editing and version control** environment for the Android project
- Building/running the app requires Android SDK, NDK, and an Android device or emulator

## User Preferences

- Follow existing project conventions and Gradle structure
