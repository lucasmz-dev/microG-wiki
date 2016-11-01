You need a ROM that supports signature spoofing. Some custom ROMs are patched to support signature spoofing out of the box, however most ROMs will require a patch or a Xposed module. Please ask your ROM developer if unsure.

The following ROMs have out-of-box support for signature spoofing. 
* [OmniROM 5](http://omnirom.org/) (Must be enabled at the bottom of the developer settings first)
* [OmniROM 6/7](http://omnirom.org/) (Must be enabled in Settings>Apps>Advanced(gear icon)>Additional permissions>Spoof signature)
* [MarshRom](http://marshrom.github.io/) (Must be enabled in Settings>Apps>Advanced(gear icon)>Additional permissions>Spoof signature)

If you have the **Xposed Framework** installed, the following module will enable signature spoofing: [FakeGApps by thermatk](http://repo.xposed.info/module/com.thermatk.android.xf.fakegapps)

If you have **Root**, but are not using Xposed, you can try patching your already-installed ROM using [Needle by moosd](https://github.com/moosd/Needle) (or its fork [Tingle by ale5000](https://github.com/ale5000-git/tingle)) or [Haystack by Lanchon](https://github.com/Lanchon/haystack). Haystack can optionally add a simple UI to control spoofing similar to the one offered by OmniROM 5. Note that all 3 patchers require that the ROM to be patched is **not odexed**.

If you are a **ROM developer** or just do **custom builds** for whatever reason, you can download and include the patch from [here](https://github.com/microg/android_packages_apps_GmsCore/tree/master/patches).