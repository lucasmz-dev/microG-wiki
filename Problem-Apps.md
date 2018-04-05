Most apps work nicely with microG. Some candidates are causing some problems. Here we're collecting problems - and hopefully solutions.


| App                        | App Version     | microG Version       | OS             | Phone      | Problem | Workaround | Usable | Related issue |
|----------------------------|-----------------|----------------------|----------------|------------|---------|------------|--------|---------------|
| [Öffi][oeffi]              | `9.07.5-google` | `0.2.4-108-gf1cdb48` | LineageOS 14.1 | LG G3 D722 |         | flash mapAPI v1 before installing | :heavy_check_mark: | |
| [Deutsche Post mobil][dpm] | `4.6.2`         | `0.2.4-108-gf1cdb48` | LineageOS 14.1 | LG G3 D722 | service stations are not displayed around phone location, crashes when a search by post code or street name is carried out | | :warning: | |
| [Couchsurfing][cs]         | `4.21.8`        | `0.2.4-111-gf1cdb48` | LineageOS 14.1 | OnePlus 3T | 'Hangout' feature doesn't work | | :warning: | [349][cs-issue] |


[oeffi]: https://play.google.com/store/apps/details?id=de.schildbach.oeffi
[dpm]: https://play.google.com/store/apps/details?id=de.deutschepost.postmobil
[cs]: https://play.google.com/store/apps/details?id=com.couchsurfing.mobile.android
[cs-issue]: https://github.com/microg/android_packages_apps_GmsCore/issues/349
