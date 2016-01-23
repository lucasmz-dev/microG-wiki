In case you had the Google Play Services previously installed, remove all updates and the packages in `/system/priv-app` of the Google Services `GmsCore`, `GoogleBackupTransport`, `GoogleFeedback`, `GoogleLoginService`, `GoogleOneTimeInitializer`, `GooglePartnerSetup`, `GoogleServicesFramework`, `Phonesky`, `SetupWizard` and `Velvet`. In case you forgot to remove the `GmsCore` updates, you can manually remove these using `adb uninstall com.google.android.gms`. After that, reboot your android device - all privileged GAPPS should be removed.

The installation does not require any modification of the /system partition. All installations should be done using the default app installer included with Android or using `adb install`. This means you need to enable third-party sources or developer mode first. In contrast to Google's version, no system privileges are required.

1. **Install GmsCore.apk** as provided in the download section. If you built *GmsCore* using gradle, use ```adb install <filename>``` on your computer.
2. **Install GsfProxy.apk** as provided in the download section if you want to use Google Cloud Messaging ("Push-Notifications"). The GsfProxy version does not need to match the GmsCore.apk version.
3. **Install a PlayStore APK**
   * If you have BlankStore installed, continue with the next step.
   * If you want to be able to access the Play Store, install BlankStore from the [XDA thread](http://forum.xda-developers.com/showthread.php?t=1715375). It is not a requirement that you set it up correctly and this is not covered by this instructions. If you need help ask in the BlankStore original thread.
   * If you don't care about Play Store access, Install FakeStore.apk as provided in the download section.
4. **Open the microG Settings**, which are available in the launcher now. If you want to use any Google services (Log-In, Cloud Messaging), tick both checkboxes for background services. This is the only supported setup, but you are free to disable them if you like playing with fire. You can also open the UnifiedNlp settings to enable the location backends of your choice. If you don't have any yet, check out F-Droid. For further questions and concerns regarding UnifiedNlp, use its corresponding [GitHub repo](https://github.com/microg/android_packages_apps_UnifiedNlp) or [XDA thread](http://forum.xda-developers.com/android/apps-games/app-g-unifiednlp-floss-wi-fi-cell-tower-t2991544).
5. **Reboot your device**. If you skip this step, everything unwanted is possible.