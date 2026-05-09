<h1 align="center">Wither Launcher</h1>

<img src="https://github.com/Wither LauncherTeam/Wither Launcher/blob/v3_openjdk/app_witherlauncher/src/main/assets/witherlauncher.png" align="left" width="130" height="150" alt="Wither Launcher logo">

[![Android CI](https://github.com/Wither LauncherTeam/Wither Launcher/workflows/Android%20CI/badge.svg)](https://github.com/Wither LauncherTeam/Wither Launcher/actions)
[![GitHub commit activity](https://img.shields.io/github/commit-activity/m/Wither LauncherTeam/Wither Launcher)](https://github.com/Wither LauncherTeam/Wither Launcher/actions)
[![Crowdin](https://badges.crowdin.net/witherlauncher/localized.svg)](https://crowdin.com/project/witherlauncher)
[![Discord](https://img.shields.io/discord/724163890803638273.svg?label=&logo=discord&logoColor=ffffff&color=7389D8&labelColor=6A7EC2)](https://discord.com/invite/aenk3EUvER)
[![Twitter Follow](https://img.shields.io/twitter/follow/plaunchteam?color=blue&style=flat-square)](https://twitter.com/PLaunchTeam)

*From [Boardwalk](https://github.com/zhuowei/Boardwalk)'s ashes here comes Wither Launcher!*

Wither Launcher is a launcher that allows you to play Minecraft: Java Edition on your Android and [iOS](https://github.com/Wither LauncherTeam/Wither Launcher_iOS) devices.

For more details, check out our [wiki](https://witherlauncher.app/)!

## Important Notes

**Wither Launcher has been discontinued** and is no longer supported. Its successor is available [here](https://github.com/AngelAuraMC/Amethyst-Android).

## Table of Contents

* [Introduction](#introduction)
* [Getting Wither Launcher](#getting-witherlauncher)
* [Building](#building)
    * [Quick Build (Recommended)](#quick-build-recommended)
    * [Detailed Build](#detailed-build)
* [Current Status](#current-status)
* [Known Issues](#known-issues)
* [FAQ](#faq)
* [Contributing](#contributing)
* [Support](#support)
* [License](#license)
* [Credits & Dependencies](#credits--dependencies)
* [Roadmap](#roadmap)

## Introduction

* Wither Launcher is a Minecraft: Java Edition launcher for Android and iOS based on [Boardwalk](https://github.com/zhuowei/Boardwalk)
* This launcher can launch almost all available Minecraft versions ranging from rd-132211 to 1.21 snapshots (including Combat Test versions)
* Modding via Forge and Fabric are also supported.
* This repository contains source code for Android. For iOS/iPadOS, check out [Wither Launcher_iOS](https://github.com/Wither LauncherTeam/Wither Launcher_iOS).

## Getting Wither Launcher

You can get Wither Launcher via three methods:

1. **Releases:** Download the prebuilt app from our [stable releases](https://github.com/Wither LauncherTeam/Wither Launcher/releases) or [automatic builds](https://github.com/Wither LauncherTeam/Wither Launcher/actions).
2. **Google Play:** Get it from Google Play by clicking on this badge: [![Google Play](https://play.google.com/intl/en_us/badges/static/images/badges/en_badge_web_generic.png)](https://play.google.com/store/apps/details?id=net.kdt.pojavlaunch)
3. **Build from Source:** Follow the [building instructions](#building) below.

## Building

### Quick Build (Recommended)

The easiest way to build Wither Launcher is to use the pre-built JREs provided by our CI.

1. Clone the repository: `git clone https://github.com/Wither LauncherTeam/Wither Launcher.git`
2. Build the launcher: `./gradlew :app_witherlauncher:assembleDebug` (Use `gradlew.bat` on Windows)

The built APK will be located in `app_witherlauncher/build/outputs/apk/debug/`.

### Detailed Build

If you need more control over the build process, follow these steps:

1. **Java Runtime Environment (JRE):** Download the `jre8-pojav` artifact from our [CI auto builds](https://github.com/Wither LauncherTeam/android-openjdk-build-multiarch/actions).  This package contains pre-built JREs for all supported architectures.  If you need to build the JRE yourself, follow the instructions in the [android-openjdk-build-multiarch](https://github.com/Wither LauncherTeam/android-openjdk-build-multiarch) repository.

2. **LWJGL:** The build instructions for the custom LWJGL are available over the [LWJGL repository](https://github.com/Wither LauncherTeam/lwjgl3).

3. **Language List:** Because languages are auto-added by Crowdin, you need to run the language list generator before building. In the project directory, run:
   * Linux/macOS:
     ```bash
     chmod +x scripts/languagelist_updater.sh
     bash scripts/languagelist_updater.sh
     ```
   * Windows:
     ```batch
     scripts\languagelist_updater.bat
     ```

4. **Build GLFW stub:** `./gradlew :jre_lwjgl3glfw:build`

5. **Build the launcher:** `./gradlew :app_witherlauncher:assembleDebug` (Replace `gradlew` with `gradlew.bat` on Windows).

## Current Status

* [x] OpenJDK 8 Mobile port: ARM32, ARM64, x86, x86_64
* [x] OpenJDK 17 Mobile port: ARM32, ARM64, x86, x86_64
* [x] OpenJDK 21 Mobile port: ARM32, ARM64, x86, x86_64
* [x] Headless mod installer
* [x] Mod installer with GUI
* [x] OpenGL in OpenJDK environment
* [x] OpenAL (works on most devices)
* [x] Support for Minecraft 1.12.2 and below
* [x] Support for Minecraft 1.13 and above
* [x] Support for Minecraft 1.17 (22w13a) and above
* [x] Game surface zooming
* [x] New input pipe rewritten to native code
* [x] Rewritten entire controls system
* [ ] More to come!

## Known Issues

See our [issue tracker](https://github.com/Wither LauncherTeam/Wither Launcher/issues) for a list of known issues and their current status.

## FAQ

See our [wiki](https://witherlauncherteam.github.io/) for more information.

## Contributing

Contributions are welcome! We welcome any type of contribution, not only code. For example, you can help improve the [wiki](https://witherlauncherteam.github.io/), contribute to the [translations](https://crowdin.com/project/witherlauncher), or submit bug reports and feature requests.

Any code change should be submitted as a pull request. The description should explain what the code does and give steps to execute it.

## Support

For support, please join our [Discord server](https://discord.com/invite/aenk3EUvER).

## License

Wither Launcher is licensed under [GNU LGPLv3](https://github.com/Wither LauncherTeam/Wither Launcher/blob/v3_openjdk/LICENSE).

## Credits & Dependencies

* [Boardwalk](https://github.com/zhuowei/Boardwalk) (JVM Launcher): Unknown License/[Apache License 2.0](https://github.com/zhuowei/Boardwalk/blob/master/LICENSE) or GNU GPLv2.
* Android Support Libraries: [Apache License 2.0](https://android.googlesource.com/platform/prebuilts/maven_repo/android/+/master/NOTICE.txt).
* [GL4ES](https://github.com/Wither LauncherTeam/gl4es): [MIT License](https://github.com/ptitSeb/gl4es/blob/master/LICENSE).
* [OpenJDK](https://github.com/Wither LauncherTeam/openjdk-multiarch-jdk8u): [GNU GPLv2 License](https://openjdk.java.net/legal/gplv2+ce.html).
* [LWJGL3](https://github.com/Wither LauncherTeam/lwjgl3): [BSD-3 License](https://github.com/LWJGL/lwjgl3/blob/master/LICENSE.md).
* [LWJGLX](https://github.com/Wither LauncherTeam/lwjglx) (LWJGL2 API compatibility layer for LWJGL3): unknown license.
* [Mesa 3D Graphics Library](https://gitlab.freedesktop.org/mesa/mesa): [MIT License](https://docs.mesa3d.org/license.html).
* [pro-grade](https://github.com/pro-grade/pro-grade) (Java sandboxing security manager): [Apache License 2.0](https://github.com/pro-grade/pro-grade/blob/master/LICENSE.txt).
* [bhook](https://github.com/bytedance/bhook) (Used for exit code trapping): [MIT license](https://github.com/bytedance/bhook/blob/main/LICENSE).
* [libepoxy](https://github.com/anholt/libepoxy): [MIT License](https://github.com/anholt/libepoxy/blob/master/COPYING).
* [virglrenderer](https://github.com/Wither LauncherTeam/virglrenderer): [MIT License](https://gitlab.freedesktop.org/virgl/virglrenderer/-/blob/master/COPYING).
* Thanks to [MCHeads](https://mc-heads.net) for providing Minecraft avatars.

## Roadmap

We are currently focusing on:

* Exploring new rendering technologies.

Future plans include:

* Improving stability and performance.
* Enhancing the mod installation experience.

We welcome community feedback and suggestions for our roadmap.  Please feel free to open a feature request in our [issue tracker](https://github.com/Wither LauncherTeam/Wither Launcher/issues).
