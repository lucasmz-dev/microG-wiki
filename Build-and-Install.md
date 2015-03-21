# Building

It is possible to build the µg-version of Google's `GmsCore` in many different ways. First of all, one should get the source code and all required dependencies:

```bash
git clone git@github.com:microg/android_packages_apps_GmsCore.git
git submodule update --recursive --init
```

## 1. Gradle
The repository contains all required build scripts for gradle and the wrapper, which is needed to start the build process. First of all, create a new `local.properties`, which contains a `sdk.dir=<path to sdk>` directive. After executing `./gradlew` in the repository directory, the debug and release apks can be found in the directory `play-services-core/build/outputs/apk/`.

In case you want to sign the apk, execute the following commands in the `apk` directory with your specific configuration:
```bash
jarsigner -verbose -sigalg SHA1withRSA -digestalg SHA1 -keystore <keystore> play-services-core-release-unsigned.apk <key name>
<sdk directory>/build-tools/22.0.0/zipalign -v 4 play-services-core-release-unsigned.apk play-services-core-release.apk
```

## 2. AOSP
In case, you want to integrate `GmsCore` into an [AOSP-based ROM build](https://source.android.com/source/initializing.html), you can place the downloaded directory in the subdirectory `/external` of the `repo sync`ed android sources. It is recommended to [patch](https://raw.githubusercontent.com/microg/android_packages_apps_GmsCore/master/android_frameworks_base%2BFAKE_PACKAGE_SIGNATURE.patch) the android distribution to support the "faking" of the original Google Play Services apk signatures. The default android build process will respect `GmsCore` and automatically create an APK on the `/system` partition image.

# Installation

The following steps are only required when building `GmsCore` using gradle. In case you had the Google Play Services previously installed, remove all updates and the packages in `/system/priv-app` of the Google Services `GmsCore`, `GoogleBackupTransport`, `GoogleFeedback`, `GoogleLoginService`, `GoogleOneTimeInitializer`, `GooglePartnerSetup`, `GoogleServicesFramework`, `Phonesky`, `SetupWizard` and `Velvet`. In case you forgot to remove the `GmsCore` updates, you can manually remove these using `adb uninstall com.google.android.gms`. After that, reboot your android device - all privileged GAPPS should be removed. Eventually, you can install the `GmsCore` replacement with `adb install <path to apk>`. In contrast to Google's version, no system privileges are required.