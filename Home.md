<img src="http://i.imgur.com/hXY4lcC.png" height="45px" alt="microg logo"/> GmsCore
===

### Overview
microG GmsCore is a free software reimplementation of Google's Play Services. It allows applications calling proprietary Google APIs to run on AOSP-based ROMs like LineageOS, acting as a free replacement for the non-free, proprietary [Google Play Services](https://en.wikipedia.org/wiki/Google_Play_Services) (sometimes referred to as the more generic term "GApps"). It is a powerful tool to reclaim your privacy and freedom while enjoying Android core features (although apps you use that take advantage of it may still be using proprietary libraries to communicate with microG, just as they do when communicating with the actual Google Play Services).

### Features
- Opt-in to Google Services and extend application support
- On-/Offline location service
- Easy on battery, memory and CPU
- No bloatware
- Works on real devices, test emulators and virtual mobile infrastructure
- Free (open source) (Apache 2.0 licensed)

### System Requirements
Your Android system needs to support [signature spoofing](https://github.com/microg/android_packages_apps_GmsCore/wiki/Signature-Spoofing) so GmsCore can pretend the existence of the official Play Services to applications calling Google APIs. See the linked page to know about ROM providing out-of-the-box support and what you can do about the other ones.

### Modules
GmsCore includes the Unified Network Location Provider module (UnifiedNlp) which handles application calls to Google's network location provider. It relies on location and address lookup backends which must be installed separately. For more information on UnifiedNlp and its backends, please refer to the [module's wiki](https://github.com/microg/android_packages_apps_UnifiedNlp/wiki).

For a full-working microG setup, you may consider to install a PlayStore replacement application as well as the Services Framework Proxy (GsfProxy) module to provide Google's push messaging service. See also [Installation](https://github.com/microg/android_packages_apps_GmsCore/wiki/Installation).

### Project status
The current status of implemented APIs is documented [on this wiki page](https://github.com/microg/android_packages_apps_GmsCore/wiki/Implementation-Status).

### Contributions welcome!
Please report bugs and include logs, screenshots, version numbers and device information depending on what issue you observed. Also, do not bother to contact the author of third-party apps when it might be related to microG services. If you created a logcat, but fear or know it contains sensitive data, you can send a private message. If the problem is related to geolocation, please file an issue in the UnifiedNlp project, even if you're using it through GmsCore.

Thanks for continously supporting this project with feedback, pull requests and donations!
