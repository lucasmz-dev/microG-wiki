* You can test Google Cloud Messaging using [this test application](https://play.google.com/store/apps/details?id=com.firstrowria.pushnotificationtester). Push notifications do not require account registration.
* You can add an account through the system settings. Some applications might ask you to do so, if you don't.
* Apps that use Cloud Messaging must be installed after GmsCore, or else they will not work. Some applications that can run with microG GmsCore is installed in the correct order: TextSecure/Signal, Play Music, YouTube
* If you are using AdAway, make sure to put mtalk.google.com on your whitelist, or else problems are likely to occur when using Google Cloud Messaging. Thanks [@benstyle1 on XDA](http://forum.xda-developers.com/member.php?u=5459278) for the hint.
