# alt.5x1.com

The 5x1 AltStore/SideStore source, served by GitHub Pages. Add `https://alt.5x1.com/source.json` in AltStore or SideStore.

To publish an app update:

1. Add the new IPA to `apps/` (e.g. `apps/BEep-1.1.ipa`).
2. In `source.json`, add a new entry at the top of the app's `versions` (version, buildVersion, date, notes, downloadURL, size in bytes, minOSVersion). Then update the app's `version`, `versionDate`, `versionDescription`, `downloadURL` and `size` to match; older SideStore versions read those fields.
3. If the app's Info.plist gained or lost a `...UsageDescription`, update `appPermissions.privacy` to match exactly, or AltStore refuses to install it.
