You need a ROM that supports signature spoofing. Some custom ROMs are patched to support signature spoofing out of the box, however most ROMs will require a patch or a Xposed module. Please ask your ROM developer if unsure.

The following ROMs have out-of-box support for signature spoofing. 
* [OmniROM 5](http://omnirom.org/) (Must be enabled at the bottom of the developer settings first)
* [OmniROM 6](http://omnirom.org/) (Must be enabled in Settings>Apps>Advanced(gear icon)>Additional permissions>Spoof signature)

If you have the **Xposed Framework** installed, the following module will enable signature spoofing: [FakeGApps by thermatk](http://repo.xposed.info/module/com.thermatk.android.xf.fakegapps)

If you have **Root**, but are not using Xposed, you can try patching your already-installed ROM using [Needle by moosd](https://github.com/moosd/Needle)

If you are a **ROM developer** or just do **custom builds** for whatever reason, you can download and include the patch from [here](https://gerrit.omnirom.org/#/c/14898/) and [here](https://gerrit.omnirom.org/#/c/14899).