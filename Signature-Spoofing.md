You need a ROM that supports signature spoofing. Some custom ROMs are patched to support signature spoofing out of the box, however most ROMs will require a patch or a Xposed module. Please ask your ROM developer if unsure.

The following ROMs have out-of-box support for signature spoofing.
* [ArrowOS](https://arrowos.net/) MicroG will ask for Signature Spoofing authorization
* [CalyxOS](https://calyxos.org/) bundled with microG
* [CarbonROM](https://carbonrom.org/) MicroG will ask for Signature Spoofing authorization
* [crDroid](https://crdroid.net/) MicroG will ask for Signature Spoofing authorization
* [/e/](https://e.foundation) bundled with microG
* [OmniROM 5](http://omnirom.org/) (Must be enabled at the bottom of the developer settings first)
* [OmniROM 6/7](http://omnirom.org/) (Must be enabled in Settings>Apps>Advanced(gear icon)>Additional permissions>Spoof signature)
* [MarshRom](http://marshrom.github.io/) (Must be enabled in Settings>Apps>Advanced(gear icon)>Additional permissions>Spoof signature)
* [AospExtended](http://www.aospextended.com/) (Must be enabled in Settings>Apps>Advanced(gear icon)>App Permissions>Spoof package signature)
* [LineageOS bundled with microG](https://lineage.microg.org/)

Also there is another maintained list of [custom ROMs that include the signature spoofing patch](https://forum.xda-developers.com/showpost.php?p=71042083).


If you have the **Xposed Framework** installed, the following module will enable signature spoofing: [FakeGApps by thermatk](http://repo.xposed.info/module/com.thermatk.android.xf.fakegapps)

You can also **patch your already-install ROM** by flashing [NanoDroid-patcher](https://github.com/Nanolx/NanoDroid), without any computer interaction. It will auto-patch every updated ROM.

Finally, if you have **Root**, but are not using Xposed, you can try patching your already-installed ROM using [Needle by moosd](https://github.com/moosd/Needle) (or its fork [Tingle by ale5000](https://github.com/ale5000-git/tingle)) or [Haystack by Lanchon](https://github.com/Lanchon/haystack). Haystack can optionally add a simple UI to control spoofing similar to the one offered by OmniROM 5. Note that all 3 patchers require that the ROM to be patched is **not odexed**.

If you are a **ROM developer** or just do **custom builds** for whatever reason, you can download and include the patch from [here](https://github.com/lineageos4microg/docker-lineage-cicd/tree/master/src/signature_spoofing_patches). Once you've downloaded the correct patch for your build version, change to the `frameworks/base` directory of your build tree and run `patch -p1 -i "path/to/where/you/saved/the/patch"`, changing the path to the appropriate path of where you saved the patch file. If it runs without error, your build will have Signature Spoofing enabled.

microG GmsCore tests and diagnoses signature spoofing, but unfortunately it cannot be installed on devices that have Google services. For testing on such devices you can use [Signature Spoofing Checker](https://github.com/Lanchon/sigspoof-checker) instead.