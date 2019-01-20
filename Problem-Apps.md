Most apps work nicely with microG. Some candidates are causing some problems. Here we're collecting problems - and hopefully solutions.


| App                        | App Version     | microG Version       | OS             | Phone      | &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Problem&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; | Workaround | Usable | Related issue |
|----------------------------|-----------------|----------------------|----------------|------------|---------|------------|--------|---------------|
| [Cabify][cabify]         | `7.1.10`        | `0.2.4-111-gf1cdb48` | OmniROM  8.1.0-20180422 | Xiaomi Redmi Note 4 | crashes with NullPointerException (right after selecting a pickup address) | | :warning: | [525][cabify-issue] | |
| [car2go][car2go]         | `3.23.4`        | `0.2.4-111-gf1cdb48` | LineageOS 15.1 (15.1-20180731-microG-oneplus3) | OnePlus 3T | Requires update of Google Play Services | :heavy_check_mark: fixed with v0.2.6.13280 | :warning: | [590][car2go-issue] | |
| [Couchsurfing][cs]         | `4.21.8`        | `0.2.4-111-gf1cdb48` | LineageOS 14.1 | OnePlus 3T | 'Hangout' feature doesn't work | | :warning: | [349][cs-issue] | |
| [Deutsche Post mobil][dpm] | `4.6.2`         | `0.2.4-108-gf1cdb48` | LineageOS 14.1 | LG G3 D722 | service stations are not displayed around phone location, crashes when a search by post code or street name is carried out | | :warning: | |
| [Discord][discord] | `6.5.6`         | `0.2.4-111-gf1cdb48` | LineageOS 14.1 | OnePlus 3T | Does not register for push notifications | | :warning: | [540][discord-issue] |
| [eBay Kleinanzeigen][ebaykleinanzeigen] | `8.7.0`         | `0.2.6-13280` | LineageOS 15.1 | Fairphone 2 | Does not register for push notifications | Downgrade to App version 7.3.1 and it will register, but notifications will be unreliable, then re-upgrade to latest and it will work! | :heavy_check_mark: | |
| [free2move][free2move]              | `11.3.1` - and all versions before | `0.2.4-108-gf1cdb48` | LineageOS 14.1 | LG G3 D722 |map display gets crazy after some usage|  | :warning: | [406](https://github.com/microg/android_packages_apps_GmsCore/issues/406) |
| [free2move][free2move]              | `11.7.0` | `0.2.4-108-gf1cdb48` | LineageOS 14.1 | LG G3 D722 |app crashes when verhicle on the map is tapped| downgrade to 11.3.1 or below | :warning: | [406 persists](https://github.com/microg/android_packages_apps_GmsCore/issues/406) |
| [free2move][free2move]              | `11.12.0` | `0.2.5-12879` | LineageOS 14.1 | LG G3 D722 |vehicles on the map are not displayed|  | issue 406 (mentioned above) does no longer exist (: |
| [free2move][free2move]              | `12.3.0` | `0.2.6-14799-dirty-145` | LineageOS 15.1 | Xiaomi Mi6 |Sometimes vehicles on the map are not displayed| Workaround 1: Restart the App sometimes - Workaround 2: Open Google Maps and locate yourself with GPS, then reopen Free2Move | |
| [Hangouts][hangouts] | `23.0.172956998` | `0.2.5-12879` | LineageOS 14.1 | | crashes on startup | [workaround](https://github.com/microg/android_packages_apps_GmsCore/issues/72#issuecomment-303714674) | | [72](https://github.com/microg/android_packages_apps_GmsCore/issues/72) |
| [hoy milonga Berlin][hoy milonga Berlin] | `1.3` - and all versions before | `0.2.4-108-gf1cdb48` | LineageOS 14.1 | LG G3 D722 |crashes when "show map" icon is tapped|  | minor issue |  |
| [Lyft][lyft]         | `5.18.3.1520427999`        | `0.2.4-108-g464d45d` | DotOS 1.2 | Moto G5 | Display of map has issues, choosing a destination doesn't work at all without a workaround | [workaround](https://github.com/microg/android_packages_apps_GmsCore/issues/207#issuecomment-299622678) | :warning: | [207](https://github.com/microg/android_packages_apps_GmsCore/issues/207) |  
| [N26][n26]         | `3.18`        | `0.2.6.13280` | LineageOS 15.1 | Xiaomi Mi 5 gemini | No push notifications, app doesn't even register with GMS, issue 507 author got it fixed randomly but no proper solution was offered | [workaround] | :warning: | [507](https://github.com/microg/android_packages_apps_GmsCore/issues/507) |  
| [NINA][nina] | `2.2.3`         | `0.2.6-13280` | LineageOS 15.1 | Fairphone 2 | Does not register for push notifications | | :warning: | |
| [Öffi][oeffi]              | `9.07.5-google` | `0.2.4-108-gf1cdb48` | LineageOS 14.1 | LG G3 D722 |     will not install    | flash mapAPI v1 before installing | :heavy_check_mark: | |
| [Threema][Threema] | `3.4.1.413 (webshop version)` | `0.2.4-108-g464d45d` | LineageOS 15.1 | Nexus 5x, OnePlus 3T | does not register with GCM for push notifications; push token cannot be reset either, so push notifications do not work | use polling at the expense of battery consumption | :heavy_check_mark: fixed with microG v0.2.613280 | [509](https://github.com/microg/android_packages_apps_GmsCore/issues/509), [502](https://github.com/microg/android_packages_apps_GmsCore/issues/502), [439](https://github.com/microg/android_packages_apps_GmsCore/issues/439) 
| [Tinder](https://play.google.com/store/apps/details?id=com.tinder) | `10.5.0` | `0.2.6.14847-dirty-155` | LineageOS 16.0 | Pocophone F1 | Crashes to home screen upon trying to login via phone number, `android.content.ActivityNotFoundException: No Activity found to handle null` |  | :x: | [693](https://github.com/microg/android_packages_apps_GmsCore/issues/693) |
| [Windfinder][Windfinder] | `3.1.2` - and all versions before | `0.2.4-108-gf1cdb48` | LineageOS 14.1 | LG G3 D722 |does not deliver map contents, only background map, but not map overlay, containing the wind force info e.g.  |  | minor issue  |  | 
| [Strava][Strava] | `3.1.2` - and all versions before | `0.2.4-108-gf1cdb48` | RR-O v6.0.0 | Moto G5 | Refuses to start as Google Maps is not detected, though there is a workaround  | Add a strava widget to your home screen, tapping that allows you into the Strava app | :warning:  | |
| [Blitzortung Lightning Monitor][bo-android]              | `1.6.3_206` | `0.2.4-111-gf1cdb48` | LineageOS 14.1 | Moto G3 |     will not install, not show map    | flash mapAPI v1 before installing |  | |

[cabify]: https://play.google.com/store/apps/details?id=com.cabify.rider
[cabify-issue]: https://github.com/microg/android_packages_apps_GmsCore/issues/525
[car2go]: https://play.google.com/store/apps/details?id=com.car2go
[car2go-issue]: https://github.com/microg/android_packages_apps_GmsCore/issues/590
[oeffi]: https://play.google.com/store/apps/details?id=de.schildbach.oeffi
[dpm]: https://play.google.com/store/apps/details?id=de.deutschepost.postmobil
[discord]: https://play.google.com/store/apps/details?id=com.discord
[discord-issue]: https://github.com/microg/android_packages_apps_GmsCore/issues/540
[cs]: https://play.google.com/store/apps/details?id=com.couchsurfing.mobile.android
[cs-issue]: https://github.com/microg/android_packages_apps_GmsCore/issues/349
[free2move]: https://play.google.com/store/apps/details?id=com.ghm.carjump
[hangouts]: https://play.google.com/store/apps/details?id=com.google.android.talk
[hoy milonga berlin]: https://play.google.com/store/apps/details?id=com.hoy.berlin&hl=de
[Windfinder]: https://play.google.com/store/apps/details?id=com.studioeleven.windfinder
[Threema]: https://threema.ch/en
[Lyft]: https://play.google.com/store/apps/details?id=me.lyft.android&hl=de
[Strava]: https://play.google.com/store/apps/details?id=com.strava
[N26]: https://play.google.com/store/apps/details?id=de.number26.android
[bo-android]: https://play.google.com/store/apps/details?id=org.blitzortung.android.app
[ebaykleinanzeigen]: https://play.google.com/store/apps/details?id=com.ebay.kleinanzeigen
[nina]: https://play.google.com/store/apps/details?id=de.materna.bbk.mobile.app