Most apps work nicely with microG. Some candidates are causing some problems. Here we're collecting problems - and hopefully solutions.


| App                        | App Version     | microG Version       | OS             | Phone      | &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Problem&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; | Workaround | Usable | Related issue |
|----------------------------|-----------------|----------------------|----------------|------------|---------|------------|--------|---------------|
| [Couchsurfing][cs]         | `4.21.8`        | `0.2.4-111-gf1cdb48` | LineageOS 14.1 | OnePlus 3T | 'Hangout' feature doesn't work | | :warning: | [349][cs-issue] | |
| [Deutsche Post mobil][dpm] | `4.6.2`         | `0.2.4-108-gf1cdb48` | LineageOS 14.1 | LG G3 D722 | service stations are not displayed around phone location, crashes when a search by post code or street name is carried out | | :warning: | |
| [free2move][free2move]              | `11.3.1` - and all versions before | `0.2.4-108-gf1cdb48` | LineageOS 14.1 | LG G3 D722 |map display gets crazy after some usage|  | :warning: | [406](https://github.com/microg/android_packages_apps_GmsCore/issues/406) |
| [free2move][free2move]              | `11.7.0` | `0.2.4-108-gf1cdb48` | LineageOS 14.1 | LG G3 D722 |app crashes when verhicle on the map is tapped| downgrade to 11.3.1 or below | :warning: | [406 persists](https://github.com/microg/android_packages_apps_GmsCore/issues/406) |
| [hoy milonga Berlin][hoy milonga Berlin] | `1.3` - and all versions before | `0.2.4-108-gf1cdb48` | LineageOS 14.1 | LG G3 D722 |crashes when "show map" icon is tapped|  | minor issue |  |
| [Lyft][lyft]         | `5.18.3.1520427999`        | `0.2.4-108-g464d45d` | DotOS 1.2 | Moto G5 | Display of map has issues, choosing a destination doesn't work at all without a workaround | [workaround](https://github.com/microg/android_packages_apps_GmsCore/issues/207#issuecomment-299622678) | :warning: | [207](https://github.com/microg/android_packages_apps_GmsCore/issues/207) |  
| [Öffi][oeffi]              | `9.07.5-google` | `0.2.4-108-gf1cdb48` | LineageOS 14.1 | LG G3 D722 |     will not install    | flash mapAPI v1 before installing | :heavy_check_mark: | |
| [Threema][Threema] | `3.4.1.413 (webshop version)` | `0.2.4-108-g464d45d` | LineageOS 15.1 | Nexus 5x, OnePlus 3T | does not register with GCM for push notifications; push token cannot be reset either, so push notifications do not work | use polling at the expense of battery consumption | | [509](https://github.com/microg/android_packages_apps_GmsCore/issues/509), [502](https://github.com/microg/android_packages_apps_GmsCore/issues/502), [439](https://github.com/microg/android_packages_apps_GmsCore/issues/439) |
| [Windfinder][Windfinder] | `3.1.2` - and all versions before | `0.2.4-108-gf1cdb48` | LineageOS 14.1 | LG G3 D722 |does not deliver map contents, only background map, but not map overlay, containing the wind force info e.g.  |  | minor issue |  |
| [Strava][Strava] | `3.1.2` - and all versions before | `0.2.4-108-gf1cdb48` | RR-O v6.0.0 | Moto G5 | Refuses to start as Google Maps is not detected, though there is a workaround  | Add a strava widget to your home screen, tapping that allows you into the Strava app | :warning:  | |


[oeffi]: https://play.google.com/store/apps/details?id=de.schildbach.oeffi
[dpm]: https://play.google.com/store/apps/details?id=de.deutschepost.postmobil
[cs]: https://play.google.com/store/apps/details?id=com.couchsurfing.mobile.android
[cs-issue]: https://github.com/microg/android_packages_apps_GmsCore/issues/349
[free2move]: https://play.google.com/store/apps/details?id=com.ghm.carjump
[hoy milonga berlin]: https://play.google.com/store/apps/details?id=com.hoy.berlin&hl=de
[Windfinder]: https://play.google.com/store/apps/details?id=com.studioeleven.windfinder
[Threema]: https://threema.ch/en
[Lyft]: https://play.google.com/store/apps/details?id=me.lyft.android&hl=de
[Strava]: https://play.google.com/store/apps/details?id=com.strava
