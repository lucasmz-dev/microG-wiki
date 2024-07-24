* You can test Firebase Cloud Messaging using [this test application](https://play.google.com/store/apps/details?id=com.firstrowria.pushnotificationtester)*. Push notifications do not require account registration.
* You can add an account through the system settings. Some applications might ask you to do so, if you don't.
* Apps that use Firebase Cloud Messaging must be installed/started after GmsCore, or else they will not work.
* If you are using AdAway, make sure to put mtalk.google.com on your whitelist, or else problems are likely to occur when using Firebase Cloud Messaging. Thanks [@benstyle1 on XDA](http://forum.xda-developers.com/member.php?u=5459278) for the hint.
* If your device is having trouble registering with Firebase Cloud Messaging, you may need to open the system phone app and dial `*#*#2432546#*#*` (or `*#*#CHECKIN#*#*`) to manually register the device as described [here](https://github.com/microg/android_packages_apps_GmsCore/issues/439#issuecomment-433018720). if typing via the keypad does not work, [check this out](https://github.com/microg/android_packages_apps_GmsCore/issues/660):
(execute as root) `adb shell am broadcast -a android.provider.Telephony.SECRET_CODE -d android_secret_code://2432546 --receiver-include-background`
* If you tried everything above and Cloud Messaging shows to be registered in microG, but no apps show up and the Push Notification Tester fails to register, try the following steps from [this Reddit thread](https://www.reddit.com/r/MicroG/comments/kuhgse/device_registration_and_push_notifications/girx53t/?context=3):
  1. disable both cloud messaging and Google device registration and reboot
  2. enable only Google device registration and reboot
  3. enable Cloud messaging and reboot  

  Many thanks to [orestarod on reddit](https://www.reddit.com/user/orestarod/) for posting this unintuitive solution.


*[possibly inaccurate](https://github.com/bbindreiter/PushNotificationTester_App/issues/3) if not up-to-date; if you're having issues considering testing with a more up-to-date application