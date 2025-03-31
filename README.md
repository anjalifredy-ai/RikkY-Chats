<div align="center">

Client based on [Telegram-X](https://github.com/TGX-Android/Telegram-X), [bocchiGramX](https://github.com/moeCrafters/bocchiGramX) and [TDLib](https://core.telegram.org/tdlib) ~
</div>

## Features
-All from [bocchiGramX](https://github.com/moeCrafters/bocchiGramX)
## Installation

### Prerequisites

* At least **5,34GB** of free disk space: **487,10MB** for source codes and around **4,85GB** for files generated after building all variants
* **4GB** of RAM
* **macOS** or **Linux**-based operating system. **Windows** platform is supported by using [MSYS](https://www.msys2.org/) (e.g., [Git Bash](https://gitforwindows.org/)).

#### macOS

* [Homebrew](https://brew.sh)
* git with LFS, wget and sed: `$ brew install git git-lfs wget gsed && git lfs install`

#### Linux

* git with LFS: Install with your package manager, e.g. `# apt install git git-lfs` for any Debian-based distribution
* Run `$ git lfs install` for the current user, if you didn't have `git-lfs` previously installed

#### Windows

* Shell with `git`, `wget`, and `make` utilities:
  * **MSYS**: `$ pacman -S make git mingw-w64-x86_64-git-lfs`
  * **Git Bash**:
    1. Download [wget](https://eternallybored.org/misc/wget/), unzip `wget.exe` and move to your `Git\mingw64\bin\`
    2. Download [make](https://sourceforge.net/projects/ezwinports/files/make-4.3-without-guile-w32-bin.zip), unzip and copy the contents to your `Git\mingw64\` merging the folders, but do **NOT** overwrite any existing files
* Run `$ git lfs install` for the current user, if you didn't have `git lfs` previously initialized
---

## Build

-  moeGramX can be built with **Android Studio** <a href="#"><img src="https://i.imgur.com/cPvvFDP.png" align="center" width="20" height="23"/></a> or from the command line with **Gradle**:
1. `$ git clone --recursive --depth=1 --shallow-submodules https://github.com/moeGramX/moeGramX bocgx` — clone **moeGramX** with submodules
2. In case you forgot the `--recursive` flag, `cd` into `bocgx` directory and: `$ git submodule init && git submodule update --init --recursive --depth=1`
3. Create `keystore.properties` file outside of source tree with the following properties:<br/>`keystore.file`: absolute path to the keystore file<br/>`keystore.password`: password for the keystore<br/>`key.alias`: key alias that will be used to sign the app<br/>`key.password`: key password.<br/>**Warning**: keep this file safe and make sure nobody, except you, has access to it. For production builds one could use a separate user with home folder encryption to avoid harm from physical theft
4. `$ cd bocgx`
5. Run `$ scripts/./setup.sh` and follow up the instructions
6. If you plan to use GCM push messages, [setup Firebase](https://firebase.google.com/docs/android/setup) and replace `google-services.json` with the one that's suitable for the `app.id` you need
7. Now you can open the project using **[Android Studio](https://developer.android.com/studio/)** <a href="#"><img src="https://i.imgur.com/cPvvFDP.png" align="center" width="20" height="23"/></a> or build manually from the command line: `./gradlew assembleUniversalRelease`.

#### Available flavors <img src="https://developer.android.com/static/images/logos/android.svg" align="center" width="20" height="20"/>

* `arm64`: **arm64-v8a** build with `minSdkVersion` set to `21` (**Lollipop**)
* `arm32`: **armeabi-v7a** build
* `x64`: **x86_64** build with `minSdkVersion` set to `21` (**Lollipop**)
* `x86`: **x86** build
* `universal`: universal build that includes native bundles for all platforms.
---

## Contributing
Not now, later.


## License

`moeGramX` is licensed under the terms of the GNU General Public License v3.0.

License of components and third-party dependencies it relies on might differ, check `LICENSE` file in the corresponding folder.

[![License: GPLv3](https://img.shields.io/badge/License-GPL%20v3-red.svg?style=for-the-badge&color=E87777)](https://github.com/moeGramX/moeGramX/blob/bocchi/LICENSE)
