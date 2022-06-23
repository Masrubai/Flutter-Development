# Flutter-Development
Flutter Development

## Installation

### Linux

#### Requirements

- Operating Systems: Linux (64-bit)
- Disk Space: 600 MB (does not include disk space for IDE/tools).
- Tools: Flutter depends on these command-line tools being available in your environment.

```
bash
curl
file
git 2.x
mkdir
rm
unzip
which
xz-utils
zip
```

##### 1. Install Git

```bash
> sudo apt install git
```

##### 2. Install Flutter SDK

```bash
> git clone https://github.com/flutter/flutter.git -b stable
```

##### 3. Install Android SDK

- [Command Line Tools](https://developer.android.com/studio?gclid=CjwKCAjwybyJBhBwEiwAvz4G76zydyTkCUdOPOn2OQJUiUjdWrs4YD2T4ZNJLxwyqumZrlWz-Z-kxhoCIb4QAvD_BwE&gclsrc=aw.ds#downloads)

- [Android Studio](https://developer.android.com/studio)

Notes: If you use Andraoid Studio, don't forget to checklist: `More Actions` > `SDK Tools` > `Android Command Tools SDK (Latest)` in Installation

##### 4. Install Java 8 Open JDK

```bash
> sudo apt install openjdk-8-jdk
```

#### 5. Set Environment Variable

- Debian or Ubuntu

```bash
> nano ~/.bashrc
```
- Arch Linux

```bash
> nano ~/.zshrc
```

#### 6. Edit Bashrc/Zshrc File

- CMDLine Tools

```bash
FLUTTER_ROOT=$HOME/code/development/mobiledev/sdk/flutter-sdk/bin # INSTALL FROM GIT
CMDLINE_TOOLS_ROOT=$HOME/cmdline-tools/bin # apkanalyzer, avdmanager, lint, profgen, retrace, screenshot2, sdkmanager
JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64
```

- Android:

```bash
FLUTTER_ROOT=$HOME/code/development/mobiledev/sdk/flutter-sdk/bin # INSTALL FROM GIT
ANDROID_SDK_ROOT=$HOME/Android/Sdk # INSTALL FROM ANDROID STUDIO
JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64

export PATH=$PATH:$FLUTTER_ROOT
export PATH=$PATH:$ANDROID_SDK_ROOT/tools # android, emulator, emulator-check, mksdcard, monitor
export PATH=$PATH:$ANDROID_SDK_ROOT/tools/bin # apkanalyzer, archquery, avdmanager, jobb, lint, monkeyrunner, screenshot2, sdkmanager, uiautomatorviewer
export PATH=$PATH:$ANDROID_SDK_ROOT/platform-tools # adb, dmtracedump, e2fsdroid, etc1tool, fastboot, hprof-conv
export PATH=$PATH:$JAVA_HOME
```

#### 7. Restart Bashrc/Zshrc File

- Debian or Ubuntu

```bash
> source ~/.bashrc
```
- Arch Linux

```bash
> source ~/.zshrc
```

#### 8. Check All Path Env Variables

```bash
> echo $PATH
```

#### 9. Run Flutter Doctor

```bash
> flutter doctor
```

Result:

```bash
[-] Android toolchain - develop for Android devices
    • Android SDK at /Users/obiwan/Library/Android/sdk
    ✗ Android SDK is missing command line tools; download from https://goo.gl/XxQghQ
    run path/to/sdkmanager --install "cmdline-tools;latest"
    ✗ Android license status unknown.
    run flutter doctor --android-licenses
    • Try re-installing or updating your Android SDK,
      visit https://flutter.dev/setup/#android-setup for detailed instructions.
```

#### 10. Fixing Android SDK Missing

Note: This problem occurs because you pass the point above, which is checklist on `SDK Tools` > `Android Command Tools SDK (Latest)`

#### 11. Update Commandline Tools

```bash
> sdkmanager --install "cmdline-tools;latest"
```

Note: `sdkmanager` command is available if you have created an Environment Variable with Path `$Path:$Android_SDK_ROOT/Tools/Bin`

If not and don't want to do a checklist you can follow this way:

```bash
> which sdkmanager # /home/fintek/Android/Sdk/tools/bin/sdkmanager

> cd /home/fintek/Android/Sdk/tools/bin

> ./sdkmanager --install "cmdline-tools;latest"
```

referance [sdkmanager command](https://developer.android.com/studio/command-line/sdkmanager)

waiting for download...

#### 12. Run Flutter Doctor Android Licenses

```bash
> flutter doctor --android-licenses
```

#### 13. Run Flutter Doctor Again

```bash
> flutter doctor
```

Result: 

```bash
Doctor summary (to see all details, run flutter doctor -v):
[✓] Flutter (Channel master, 2.6.0-1.0.pre.152, on Ubuntu 20.04.2 LTS 5.11.0-27-generic, locale en_US.UTF-8)
[✓] Android toolchain - develop for Android devices (Android SDK version 31.0.0)
[✓] Chrome - develop for the web
[✓] Android Studio (version 2020.3)
[✓] VS Code (version 1.57.1)
[✓] Connected device (1 available)

• No issues found!
```

## Run Flutter

```bash
> flutter run 
```

## Run Flutter Without Unsound Null Safety

```bash
> flutter run --no-sound-null-safety
```

## Run Flutter With Flavor

```bash
> flutter run --flavor <product-name> lib/products/something/index.dart
```

## FLutter Upgrade/Downgrade

```bash
> git tag --list
> git checkout <tag>
> flutter doctor
```
