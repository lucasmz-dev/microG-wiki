## Prerequisites

Due to the use of symlinks, a unix-based operating system is required. Make sure you configured a full-working build setup and have Android SDK and Java installed properly. 

Please note that building with other operating systems is not officially supported.

## Build stand-alone App with Gradle

Get the source code and clone it into your directory of choice:

```bash
git clone https://github.com/microg/android_packages_apps_GmsCore.git
cd android_packages_apps_GmsCore/
git submodule update --recursive --init
```

The cloned repository contains all required build scripts for gradle and the wrapper, which is needed to start the build process. Make sure you have your `ANDROID_SDK_HOME` and `JAVA_HOME` properly defined in your `~/.profile` or `~/.bashrc`.

To build _GmsCore_, execute in your cloned directory
```bash
./gradlew build
```
The generated apks can be found in the subdirectory `play-services-core/build/outputs/apk/`.

You may want to sign your apk using the following commands in the `apk` directory with your specific configuration:
```bash
jarsigner -verbose -sigalg SHA1withRSA -digestalg SHA1 -keystore ~/path_to_your/keystore.jks play-services-core-release-unsigned.apk your_keystore_username --signedjar play-services-core-release-signed.apk
$ANDROID_SDK_HOME/build-tools/23.0.2/zipalign -v 4 play-services-core-release-signed.apk com.google.android.gms.apk
```
Alternatively, you can use this small bash script, which automates all required steps from above:

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

Congratulations, you got your `com.google.android.gms.apk`! Now head over to [Installation](https://github.com/microg/android_packages_apps_GmsCore/wiki/Installation).

### Gradle integrated signing
You can also sign and zipalign directly as part of the `./gradlew build` call. To do so, create a file `play-services-core/user.gradle` with the following content:
```groovy
android {
    signingConfigs {
        release {
            storeFile file('~/path_to_your/keystore.jks')
            storePassword 'keystore password'
            keyAlias 'key alias'
            keyPassword 'key password'
        }
    }

    buildTypes {
        /* Optional: sign debug builds with release key
        debug {
            signingConfig signingConfigs.release
        }
        //*/
        release {
            signingConfig signingConfigs.release
        }
    }
}
```
When doing so, `./gradlew build` will produce the final file at `play-services-core/build/outputs/apk/play-services-core-release.apk`

## Integrate GmsCore in AOSP-based ROM

In case you want to integrate _GmsCore_ into an [AOSP-based ROM build](https://source.android.com/source/initializing.html), you can add its repository to your `local_manifests.xml` to keep it updated by `repo`:

```xml
<remote  name="github"
             fetch="https://github.com/" />

<project path="packages/apps/GmsCore" name="microg/android_packages_apps_GmsCore" remote="github" revision="master" />
```
You may want to add `<project ... />` lines for _GsfProxy_ and _FakeStore/BlankStore_, too.

Now edit your `device.mk` in `~/path_to_aosp/device/your_manufacturer/your_model`
and add the package names you want to include in your build:

```Makefile
# OTHER PACKAGES
PRODUCT_PACKAGES += \
   GmsCore \
   GsfProxy \
   FakeStore
```
The default android build process will respect *GmsCore* and automatically create an APK on the `/system` partition image.

Please note, that to make _GmsCore_ work, your ROM has to support [Signature Spoofing](https://github.com/microg/android_packages_apps_GmsCore/wiki/Signature-Spoofing).