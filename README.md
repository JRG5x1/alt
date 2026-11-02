# apps.5x1.com

5x1's app downloads, served by GitHub Pages: BEep for iPhone (AltStore/SideStore source) and for Android (APK).

- iPhone: add `https://apps.5x1.com/source.json` in AltStore or SideStore.
- Android: download the APK from [apps.5x1.com](https://apps.5x1.com).

`source.json` is the AltStore source and `android.json` lists the Android downloads (the page's buttons read it). Publish BEep and BEep BETA builds with BEep's `ci/publish.py`, which reads everything from the build itself; BETA builds are downloads on this repo's releases.

If an iPhone app's Info.plist gains or loses a `...UsageDescription`, `publish.py` updates `appPermissions.privacy` to match, because AltStore refuses to install an app whose listed permissions differ.

`fdroid/repo` is the 5x1 F-Droid repository (BEep and BEep BETA, the same signed APKs). It's generated and signed by `fdroid update` in a private workspace (`/root/jibo-stuff/BEep-signing/fdroid`, which holds the index signing key) and synced here by `publish.py`; never edit it by hand. Repo fingerprint: `6972056445AEC814CFBD42234FB369106DBEBEC161E8C55358D1089AFAD6D099`.

The old address, alt.5x1.com, is the small `JRG5x1/alt-redirect` site: it sends browsers here and keeps a copy of `source.json` for phones that added the old source.
