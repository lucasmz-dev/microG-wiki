| API | Functionality | Crashing | Issues |
|-----|---------------|----------|--------|
| Account Authentication | :warning: Partial | :warning: Maybe | Major regressions in 0.2.7.17455, fixed in [4713797edc](https://github.com/microg/android_packages_apps_GmsCore/commit/4713797edc21e3f3b2a26194056f63b307e67ef6) (0.2.8.17785) |
| Analytics | :white_check_mark:  Not intended | :heavy_check_mark: No | | 
| Auto | :x: None | :x: Yes | |
| Cast | :warning: Partial | :warning: Maybe | Minor issues |
| Drive | ✔️ : Full | :warning: Maybe | |
| Exposure Notifications | ✔️ : Full | :heavy_check_mark:  No | [🦠 Exposure Notifications](https://github.com/microg/android_packages_apps_GmsCore/labels/%F0%9F%A6%A0%20Exposure%20Notifications) |
| FIDO2/U2F | :x: None | :warning: Maybe | [#849](https://github.com/microg/GmsCore/issues/849), Not implemented |
| Firebase Analytics | :white_check_mark: Not intended | :warning: Maybe | |
| Firebase Cloud Messaging | :heavy_check_mark: Full | :heavy_check_mark: No | |
| Firebase Auth | :warning: Partial | :warning: Maybe | [#1198](https://github.com/microg/GmsCore/issues/1198),[#1281](https://github.com/microg/GmsCore/issues/1281) **Supported methods**: Anonymous login, Email/Password login, Phone login, Custom-Token login **Not supported methods**: GoogleSignIn, FirebaseUI |
| Fitness | :x: None | :warning: Maybe | |
| [Fonts](https://developer.android.com/guide/topics/ui/look-and-feel/downloadable-fonts#via-android-studio) | :x: None | :heavy_check_mark: No | [#797](https://github.com/microg/android_packages_apps_GmsCore/issues/797), Not implemented |
| Fused Locations | :heavy_check_mark: Full | :heavy_check_mark: No | Does not honor AppOps! |
| Games | :x: None | :warning: Maybe | [#163](https://github.com/microg/android_packages_apps_GmsCore/issues/163) |
| Geofencing | :x: None | :warning: Maybe | |
| Maps API version 1| :heavy_check_mark:  Full | :heavy_check_mark:  No | |
| Maps API version 2| :warning:  Partially | :warning: Probably | Many unimplemented APIs. **Use Mapbox build**! |
| Maps API version 2 (Mapbox)| :white_check_mark:  Mostly | :warning: Maybe | Minor glitches |
| Mobile Ads | :white_check_mark: Not intended | :heavy_check_mark: No | | 
| Nearby | :x: None | :warning: Maybe | |
| Plus | :x: None | :warning: Maybe | Google discontinued Google Plus, making µG's implementation useless |
| SafetyNet | :warning: Partial | :heavy_check_mark: No | [#526](https://github.com/microg/android_packages_apps_GmsCore/issues/526), [#24](https://github.com/microg/android_packages_apps_RemoteDroidGuard/issues/24) |
| Vision | :warning: Partial | :warning: Maybe | Only Barcode scanning. [#395](https://github.com/microg/android_packages_apps_GmsCore/issues/395), [#670](https://github.com/microg/android_packages_apps_GmsCore/issues/670) |
| Wearable | :x: None | :warning: Maybe | [#4](https://github.com/microg/android_packages_apps_GmsCore/issues/4), Missing most APIs |