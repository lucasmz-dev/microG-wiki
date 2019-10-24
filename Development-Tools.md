## Using the emulator
You can't use the default Android SDK emulator because it lacks signature spoofing capability. Therefore, we ship a custom emulator image that can be installed with the Android SDK. The following instructions will guide you through the installation microG emulator image.

1. SDK manager
2. Select tab "SDK Update Sites" 
3. Add the microG SDK add-on site with the URL `https://microg.org/sdk/sys-img.xml`.
4. Apply changes
5. Select tab "SDK Platforms"
6. Make sure "Show Package Details" in bottom right is ticked
7. From "Android 10.0 (Q)" tick "microG Intel x86 Atom_64 System Image"
8. Apply changes
9. Wait for installation to finish.

Now you will be able to create new virtual Android 10.0 devices with microG support.