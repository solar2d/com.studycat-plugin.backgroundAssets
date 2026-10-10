# plugin.backgroundAssets (publisherId `com.studycat`)

Apple's Background Assets for Solar2D. It downloads, checks and removes asset packs through the managed Background
Assets API (`BAAssetPackManager`), with Apple-hosted or self-hosted packs. Current version: 1.0.1.

Platforms: iOS, macOS Simulator, Windows Simulator. It needs Solar2D 2026.3731 or newer.

- On iOS 26 and later the calls reach Background Assets. Below iOS 26 the plugin loads and every call reports that it is
  unsupported, so an app can keep another download path there.
- In the macOS and Windows Simulators it runs over an emulator of Background Assets, with settings for offline, free
  disk space and download speed.

## build.settings

```lua
settings =
{
    plugins =
    {
        ["plugin.backgroundAssets"] =
        {
            publisherId = "com.studycat",
        },
    },
}
```

```lua
local backgroundAssets = require("plugin.backgroundAssets")
```

A device build also needs the app setup: a few Info.plist keys, two entitlements and a downloader extension in the
project's `Extensions/` folder. The setup page covers each one. An app built with Xcode 27 (Solar2D 3733) must target
iOS 15.0 or later.

To stay on one release, add `version = "vN"` to the entry, with a tag from this repository's Releases page: `v1` is
1.0.1.

## Links

- Documentation: https://backgroundassets-solar2d.readthedocs.io
- App setup (keys, entitlements, downloader extension): https://backgroundassets-solar2d.readthedocs.io/en/latest/setup.html
- Testing in the Simulator: https://backgroundassets-solar2d.readthedocs.io/en/latest/simulator.html
- Source, changelog and issues: https://github.com/depilz/solar2d-plugin-background-assets

## License

MIT, Copyright (c) 2026 Studycat Limited. See the source repository's LICENSE.
