## Using the emulator
You can't use the default Android SDK emulator because it lacks signature spoofing capability. Therefore, we ship a custom emulator image that can be installed with the Android SDK. The following instructions will guide you through the installation microG emulator image.

1. Open the standalone SDK manager
2. From menu, choose "Tools" -> "Manage Add-on sites..." 
3. In the "User Defined Sites" section, add the microG SDK add-on site with the URL 'http://microg.org/sdk/sys-img.xml' (sdk manager seems to not support SNI yet 😞).
4. Close Add-on-site manager.
5. From menu, choose "Packages" -> "Reload"
6. Wait for the reloading process (progress bar at bottom of window) to finish
7. From "Android 6.0 (API 23)" tick "microG Intel x86 Atom System Image"
8. Select "Install 1 package" at the bottom of the window.
9. Wait for installation to finish.

Now you will be able to create new virtual Android 6.0 devices with microG support.