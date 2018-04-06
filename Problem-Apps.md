Most apps work nicely with microG. Some candidates are causing some problems. Here we're collecting problems - and hopefully solutions.


| App                        | App Version     | microG Version       | OS             | Phone      | &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Problem&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; | Workaround | Usable | Related issue |
|----------------------------|-----------------|----------------------|----------------|------------|---------|------------|--------|---------------|
| [Öffi][oeffi]              | `9.07.5-google` | `0.2.4-108-gf1cdb48` | LineageOS 14.1 | LG G3 D722 |     will not install    | flash mapAPI v1 before installing | :heavy_check_mark: | |
| [Deutsche Post mobil][dpm] | `4.6.2`         | `0.2.4-108-gf1cdb48` | LineageOS 14.1 | LG G3 D722 | service stations are not displayed around phone location, crashes when a search by post code or street name is carried out | | :warning: | |
| [Couchsurfing][cs]         | `4.21.8`        | `0.2.4-111-gf1cdb48` | LineageOS 14.1 | OnePlus 3T | 'Hangout' feature doesn't work | | :warning: | [349][cs-issue] | |
| [Lyft][lyft]         | `5.18.3.1520427999`        | `0.2.4-108-g464d45d` | DotOS 1.2 | Moto G5 | Display of map has issues, choosing a destination doesn't work at all without a workaround | [workaround](https://github.com/microg/android_packages_apps_GmsCore/issues/207#issuecomment-299622678) | :warning: | [207] |  
| [free2move][free2move]              | `11.7.0` - and all versions before | `0.2.4-108-gf1cdb48` | LineageOS 14.1 | LG G3 D722 |         | map display gets crazy after some usage | :warning: | [406](https://github.com/microg/android_packages_apps_GmsCore/issues/406) |
| [hoy milonga Berlin][hoy milonga Berlin] | `11.7.0` - and all versions before | `0.2.4-108-gf1cdb48` | LineageOS 14.1 | LG G3 D722 |         | crashes when "show map" icon is tapped | :warning: |  |




[oeffi]: https://play.google.com/store/apps/details?id=de.schildbach.oeffi
[dpm]: https://play.google.com/store/apps/details?id=de.deutschepost.postmobil
[cs]: https://play.google.com/store/apps/details?id=com.couchsurfing.mobile.android
[cs-issue]: https://github.com/microg/android_packages_apps_GmsCore/issues/349
[free2move]: https://app.adjust.com/54svnl_3mlvwg_f3w7b2?adgroup=AppStoreButton&creative=HeroStage&deeplink=carjump%3A%2F%2Fregister
[hoy milonga berlin]: https://play.google.com/store/apps/details?id=com.hoy.berlin&hl=de
