Please review the [Prerequisites](https://github.com/microg/android_packages_apps_GmsCore/wiki/Prerequisites) and [Helpful Information](https://github.com/microg/android_packages_apps_GmsCore/wiki/Helpful-Information) before starting installation.

1. **Install apk of microG Services** (see note at the bottom) as provided in the [download section](https://github.com/microg/android_packages_apps_GmsCore/wiki/Downloads) or in the microG F-Droid repository. If you built *GmsCore* using gradle, you can use ```adb install <filename>``` on your computer.
2. **Install apk of microG Services Framework Proxy** as provided in the download section if you want to use Google Cloud Messaging ("Push-Notifications"). The GsfProxy version does not need to match the GmsCore.apk version and is installable without higher privileges.
3. **Install a store apk**
   * If you have BlankStore installed, continue with the next step.
   * If you want to be able to access the Play Store, install BlankStore from the [XDA thread](http://forum.xda-developers.com/showthread.php?t=1715375). It is not a requirement that you set it up correctly and this is not covered by this instructions. If you need help ask in the BlankStore original thread.
   * If you don't care about Play Store access, install the apk of _microG Companion_ as provided in the download section.
4. **Open the microG Settings**, which are available in the launcher now. If you want to use any Google services (Log-In, Cloud Messaging), tick both checkboxes for background services. This is the only supported setup, but you are free to disable them if you like playing with fire. You can also open the UnifiedNlp settings to enable the location backends of your choice. If you don't have any yet, check out F-Droid. For further questions and concerns regarding UnifiedNlp, use its corresponding [GitHub repo](https://github.com/microg/android_packages_apps_UnifiedNlp) or [XDA thread](http://forum.xda-developers.com/android/apps-games/app-g-unifiednlp-floss-wi-fi-cell-tower-t2991544).
5. **Reboot your device**. If you skip this step, everything unwanted is possible.
6. **Disable Battery Optimization**, if you use Android 6 (Marshmallow) or above. Ensure that it is disabled for microG Services Core in System Settings > Battery > Menu > Battery optimization. Note that this is the case for the original Play Services, as it is required to keep a stable background connection.

**Note:** On Android 7 (or later) an [additional patch](https://github.com/microg/android_packages_apps_UnifiedNlp/blob/master/patches/android_frameworks_base-N.patch) is needed to make location work, or alternatively:
*  You can install **GmsCore.apk** in the `/system/priv-app` folder. This can be done by using `adb push`.