# Remember from GPS
microG can create a local database and remember Wi-Fi and mobile networks from GPS when location is requested, so that location can be acquired more quickly in the future without the same dependence on GPS.

# Request from Hotspot
microG supports a few location services integrated into certain hotspots like the ones in metros, etc. See [this.](https://github.com/microg/GmsCore/blob/991da7bdd172add5eb664a4d713ca53513d5d5f3/play-services-location/core/provider/src/main/kotlin/org/microg/gms/location/network/wifi/MovingWifiHelper.kt#L314C1-L314C70)

# Online Location Services

Online location services are great for their availability, however they are less private as your location is extracted by a third party on basis of known networks around you, that you send over. Be aware of this in case you have a higher threat model.

They might also be used indirectly by things such as weather apps to get an approximate location. 

microG 0.3.3 and above will give options to you when enabling the online location service toggle.

## [positon.xyz](https://positon.xyz)

The Positon location service provides commercial levels of data quality, as it does come from commercial sources, therefore the need for contribution is not as much as what was the case with MLS where poisoned data was constantly an issue especially after contributions were killed by a third party in a lawsuit.

## [beacondb.net](https://beacondb.net)

beaconDB is a project where people are allowed to contribute data to it just like with MLS, but exports have privacy protections added to them so that it is harder to identify AP owners and locations or contributors, and also to prevent future issues.

Currently, it also includes the mobile network export of MLS for better coverage, but not Wi-Fi or Bluetooth as those were not publicized by Mozilla.

Exports are not yet available as there is still work in making these exports more private. You can check a map of contributions in https://beacondb.net/map.
More information on how to contribute and use the service is available [in their website.](https://beacondb.net)

> [!TIP]
> With the open nature of beaconDB, and with its plan to make its data open, it would be possible in the future to have a downloadable database where you do not rely on it to calculate your position, therefore allowing private use of a location service, and for it to be used offline. If this is something you value, consider contributing to it.


# [Nominatim](https://nominatim.org/)

Nominatim is used for address resolving. It means it is used for translating addresses to coordinates, and vice-versa. It is an online service.
