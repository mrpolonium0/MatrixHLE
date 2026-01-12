## SoraHLE: High-level emulator for iPhone OS apps

<img width="997" height="757" alt="image" src="https://github.com/user-attachments/assets/2d02327b-acf7-4b22-bab9-ce75042d22ed" />

---------------------------------------------------------------------------------------------------------------------------------------------------------------------

SoraHLE is a high-level emulator for iPhone OS apps. It runs on modern desktop operating systems and Android, and is written in Rust.

--SoraHLE uses a high-level emulation (HLE) approach, which differs from traditional low-level emulation (LLE). Instead of simulating iPhone/iPod touch hardware directly, SoraHLE replaces iPhone OS itself by providing its own implementations of system frameworks such as Foundation, UIKit, OpenGL ES, OpenAL, and more. The only code executed by the emulated CPU is the app binary and a small number of essential libraries.

The primary goal of SoraHLE is to run games from the early days of iOS:

  * Currently supported: iPhone and iPod touch apps for iPhone OS 2.x and 3.x.

  * Future plans: Support for iPhone OS 3.1, iPad apps (iPhone OS 3.2), iOS 4.x, and others.

  * [In the long run]: 64-bit iOS apps.

Not all apps for these OS versions are compatible. The majority of working apps are games, as other apps are more complex to emulate and less of a focus. Compatibility improves over time through contributions from developers. A crowdsourced app compatibility database tracks which apps run in SoraHLE. Please note that the project does not accept individual app requests.
For more information about the project’s history and technical details, you can read the original announcement or explore SoraHLE in depth.

---------------------------------------------------------------------------------------------------------------------------------------------------------------------

## Platform support

  * Officially supported: x64 Windows, x64 macOS, AArch64 Android.

  * On Apple Silicon Macs, the x64 build works under Rosetta.

  * Community builds: AArch64 macOS, x64 Linux, AArch64 Linux.

  * Not supported: Other architectures.

--------------------------------------------------------------------------------------------------------------------------------------------------------------------

## Input methods

## Touch Input:

   * Mouse/trackpad (tap, hold, drag via left mouse button)

   * Virtual cursor using a game controller

   * Game controller button mapping to screen locations

   * Real touchscreen input on compatible devices

## Accelerometer input

   * Tilt simulation using game controller or mouse

   * Real accelerometer input on phones or tablets

-------------------------------------------------------------------------------------------------------------------------------------------------------------------

## Developement status

SoraHLE has been in development since [insert start date]. It began as a passion project and now benefits from contributions by multiple volunteers.


Support completeness varies depending on which apps contributors are focusing on. For instance:

  * UIKit implementations are partial and hacky, sufficient for many early games.

  * OpenGL ES and OpenAL implementations are more complete, as games heavily rely on these frameworks.

-------------------------------------------------------------------------------------------------------------------------------------------------------------------

## Usage

 1. Obtain SoraHLE: Use a binary release or build it yourself.

 2. Prepare an app: Only decrypted iPhone/iPod touch app binaries (IPA or .app) are usable.

 3. Run the app:

     * Desktop: Drag and drop or use the command line interface.

     * Android: Place app files in the SoraHLE_apps directory. Use the built-in app picker to launch apps.

## Local multiplayer support

SoraHLE provides limited Wi-Fi multiplayer support for certain games.

 * Install SoraHLE on multiple devices connected to the same network.

 * Enable network access via Quick Options or --allow-network-access.

 * Start/join the multiplayer session in the game.

------------------------------------------------------------------------------------------------------------------------------------------------------------------

## Known issues

 * Overlays like Discord, Steam, or RivaTuner may cause crashes.

 * On macOS, launch from Terminal to enable network access.

 * Android file access can be tricky due to OS restrictions.

-----------------------------------------------------------------------------------------------------------------------------------------------------------------

## File storage

All app data (e.g., saved games) is stored in the SoraHLE_sandbox folder.

----------------------------------------------------------------------------------------------------------------------------------------------------------------

## Building and contributing

See CONTRIBUTING.md for how to contribute, and dev-docs/building.md for instructions on building SoraHLE yourself.

----------------------------------------------------------------------------------------------------------------------------------------------------------------

## License

SoraHLE © 2023–2026 SoraHLE project contributors.

Source code: Mozilla Public License 2.0

Binaries: GNU GPL v3 or later

Licenses for dependencies, fonts, and dynamic libraries may vary.

---------------------------------------------------------------------------------------------------------------------------------------------------------------

## SoraHLE ACD (App comptibility database)

(find out what does and doesn't work!)


 * If you are interested to see wich apps are compatible with SoraHLE, feel free to check out our GitHub page right here:

   --https://github.com/mrpolonium0/SoraHLE-App-comptibility-database-/tree/main

---------------------------------------------------------------------------------------------------------------------------------------------------------------

## Acknowledgments

SoraHLE stands on the shoulders of giants. Thanks to:


* The entire team behind [touchHLE]: @Ciciplusplus, @hikari-no-yume, @apexad and so much more...
* Everyone who has contributed to the project or supported any of its contributors financially.
* The authors of and contributors to the many libraries used by this project: [dynarmic](https://github.com/merryhime/dynarmic), [rust-macho](https://github.com/flier/rust-macho), [SDL](https://libsdl.org/), [rust-sdl2](https://github.com/Rust-SDL2/rust-sdl2), [stb\_image](https://github.com/nothings/stb), Imagination Technologies' [PVRTC decompressor](https://github.com/powervr-graphics/Native_SDK/blob/master/framework/PVRCore/texture/PVRTDecompress.cpp), [openal-soft](https://github.com/kcat/openal-soft), [hound](https://github.com/ruuda/hound), [caf](https://github.com/rustaudio/caf), [Symphonia](https://github.com/pdeljanov/Symphonia), [RustType](https://gitlab.redox-os.org/redox-os/rusttype), [the Liberation fonts](https://github.com/liberationfonts/liberation-fonts), [the Noto CJK fonts](https://github.com/googlefonts/noto-cjk), [rust-plist](https://github.com/ebarnard/rust-plist), [quick-xml](https://github.com/tafia/quick-xml), [gl-rs](https://github.com/brendanzab/gl-rs), [cargo-license](https://github.com/onur/cargo-license), [cc-rs](https://github.com/rust-lang/cc-rs), [cmake-rs](https://github.com/rust-lang/cmake-rs), [cargo-ndk](https://github.com/bbqsrc/cargo-ndk), [cargo-ndk-android-gradle](https://github.com/willir/cargo-ndk-android-gradle), [md5](https://github.com/stainless-steel/md5), [yore](https://github.com/bonega/yore), [encoding_rs](https://github.com/hsivonen/encoding_rs), and the Rust standard library.
* The Skyline emulator project (RIP), for [writing the tedious boilerplate needed to replace file management on newer Android versions](https://github.com/skyline-emu/skyline/blob/dc20a615275f66bee20a4fd851ef0231daca4f14/app/src/main/java/emu/skyline/provider/DocumentsProvider.kt).
* The [Rust project](https://www.rust-lang.org/) generally.
* The various people out there who've documented the iPhone OS platform, officially or otherwise. Much of this documentation is linked to within this codebase!
* The iOS hacking/jailbreaking community.
* The Free Software Foundation, for making libgcc and libstdc++ copyleft and therefore saving this project from ABI hell.
* The National Security Agency of the United States of America, for [Ghidra](https://ghidra-sre.org/).
* [GerritForge](http://www.gerritforge.com/) for providing free Gerrit hosting to the general public, including us.
* The many contributors to [Gerrit](https://www.gerritcodereview.com/).
* Many friends who took an interest in the project and gave suggestions and encouragement.
* Developers of early iPhone OS apps. What treasures you created!
* Apple, and NeXT before them, for creating such fantastic platforms.
