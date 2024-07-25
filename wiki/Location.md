# Remember from GPS
microG can create a local database and remember Wi-Fi and mobile networks from GPS when location is requested, so that location can be acquired more quickly in the future without the same dependence on GPS.

# Request from Hotspot
microG supports a few location services integrated into certain hotspots like the ones in metros, etc. See [this.](https://github.com/microg/GmsCore/blob/991da7bdd172add5eb664a4d713ca53513d5d5f3/play-services-location/core/provider/src/main/kotlin/org/microg/gms/location/network/wifi/MovingWifiHelper.kt#L314C1-L314C70)

# Location Services

microG at the moment by default has Mozilla's Location Services for online location services. Unfortunately, MLS has died and can no longer be used. This should change next release.

At the moment, there are two options for what to use instead, both great!
You need at least microG 0.3.2 to be able to use these.

## [positon.xyz](https://positon.xyz)

The Positon location service provides commercial levels of data quality, as it does come from commercial sources, therefore the need for contribution is not as much as what was the case with MLS where poisoned data was constantly an issue especially after contributions were killed by a third party in a lawsuit.

Positon supports aggressive local caching which means extra data is sent in requests, this helps so that there isn't as much of the need for constantly requesting data from the online service and it is instead stored locally. [microG does not support this yet, but plans to.](https://github.com/microg/GmsCore/issues/2237#issuecomment-2169652426)

You can start using Positon by setting the URL [linked here.](https://github.com/microg/GmsCore/issues/2237#issuecomment-2169193229)

## [beacondb.net](https://beacondb.net)

BeaconDB is a project where people are allowed to contribute data to it just like with MLS, but exports have privacy protections added to them so that it is harder to identify AP owners and locations or contributors.

Currently, it also includes the mobile network export of MLS for better coverage, but not Wi-Fi or Bluetooth as those were not publicized by Mozilla.

Exports are not yet available as there is still work in making these exports more private. You can check a map of contributions in https://beacondb.net/map.
More information on how to contribute and use the service is available [in their website.](https://beacondb.net)

To use it in microG, simply go into Location > Three dots at top right > Configure service URL > replace with https://beacondb.net. API keys are currently not required or used.

> Make sure to have "Request from Mozilla" enabled when using any of these.

# [Nominatim](https://nominatim.org/)

Nominatim is used for address resolving. It means it is used for translating addresses to coordinates, and vice-versa. It is an online service.