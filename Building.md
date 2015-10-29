# Dependencies
You need the following prerequisites to build *GmsCore*:

1. Due to the use of symlinks, a unix-based operating system is required to build the application. Please notice, that building with other operating systems is not supported.
2. Your Android-ROM should integrate the `FAKE_PACKAGE_SIGNATURE`-patch, which is required to fully use the features of *GmsCore*.
3. The build process requires a full-working Android SDK and Java installation.

# Building

It is possible to build the µg-version of Google's *GmsCore* in many different ways:

## 1. Script
You can use this small bash script, which automates all required steps to build *GmsCore*:

```shell
#!/bin/bash

mkdir microg
cd microg
mkdir outputs
mkdir keystores

ANDROID_SDK_PATH="/opt/android-sdk-update-manager"
KEYSTORES_PATH="keystores"

# Generate keystore
echo "We need to create a keystore for GmsCore:"
keytool -genkey -v -keystore $KEYSTORES_PATH/playservices.jks -alias playservices -keyalg RSA -keysize 4096 -validity 10000


# GMSCore
git clone https://github.com/microg/android_packages_apps_GmsCore.git
cd android_packages_apps_GmsCore
git submodule update --init --recursive
echo "sdk.dir=$ANDROID_SDK_PATH" > local.properties
echo "sdk-location=$ANDROID_SDK_PATH" >> local.properties
./gradlew build
cp play-services-core/build/outputs/apk/play-services-core-release-unsigned.apk ../outputs/play-services-core-release.apk


# Sign APK
cd ../outputs
jarsigner -verbose -sigalg SHA1withRSA -digestalg SHA1 -keystore $KEYSTORES_PATH/playservices.jks play-services-core-release.apk playservices
$ANDROID_SDK_PATH/build-tools/22.0.1/zipalign -v 4 play-services-core-release.apk com.google.android.gms.apk
```

## 2. Gradle
First of all, one should get the source code and all required dependencies:

```bash
git clone git@github.com:microg/android_packages_apps_GmsCore.git
git submodule update --recursive --init
```

The cloned repository contains all required build scripts for gradle and the wrapper, which is needed to start the build process. Firstly, create a new `local.properties`, which contains a `sdk.dir=<path to sdk>` directive. After executing `./gradlew` in the repository directory, the debug and release apks can be found in the directory `play-services-core/build/outputs/apk/`.

In case you want to sign the apk, execute the following commands in the `apk` directory with your specific configuration:
```bash
jarsigner -verbose -sigalg SHA1withRSA -digestalg SHA1 -keystore <keystore> play-services-core-release-unsigned.apk <key name>
<sdk directory>/build-tools/22.0.1/zipalign -v 4 play-services-core-release-unsigned.apk play-services-core-release.apk
```

## 3. AOSP
In case, you want to integrate *GmsCore* into an [AOSP-based ROM build](https://source.android.com/source/initializing.html), you can sync the GmsCore project in the subdirectory `/external` of the `repo sync`ed android sources:

```bash
git clone git@github.com:microg/android_packages_apps_GmsCore.git
git submodule update --recursive --init
```

 It is recommended to [patch](https://raw.githubusercontent.com/microg/android_packages_apps_GmsCore/master/android_frameworks_base%2BFAKE_PACKAGE_SIGNATURE.patch) the android distribution to support the "faking" of the original Google Play Services apk signatures. The default android build process will respect *GmsCore* and automatically create an APK on the `/system` partition image.

# Installation

The following steps are only required when building *GmsCore* using gradle. In case you had the Google Play Services previously installed, remove all updates and the packages in `/system/priv-app` of the Google Services `GmsCore`, `GoogleBackupTransport`, `GoogleFeedback`, `GoogleLoginService`, `GoogleOneTimeInitializer`, `GooglePartnerSetup`, `GoogleServicesFramework`, `Phonesky`, `SetupWizard` and `Velvet`. In case you forgot to remove the `GmsCore` updates, you can manually remove these using `adb uninstall com.google.android.gms`. After that, reboot your android device - all privileged GAPPS should be removed. Eventually, you can install the `GmsCore` replacement with `adb install <path to apk>`. In contrast to Google's version, no system privileges are required.



**In case your Android-ROM is rooted, GAPPS-free and you used the script building method, one usually only needs to execute the following commands:**
```shell
#!/bin/bash
adb install com.google.android.gms.apk
```