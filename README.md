# The Me App — public release channel

Public APK distribution for [The Me App](https://github.com/johnkitch/the-me-app) (private source).

## Install on Android

Download the latest signed APK and sideload it:

**[Download the-me-app.apk](https://github.com/johnkitch/the-me-app-releases/releases/latest/download/the-me-app.apk)**

After the first install, the app auto-checks this channel on launch and prompts to install any newer version (sideloaded APKs always prompt — silent updates require Google Play).

## How updates work

The app fetches [`latest.json`](./latest.json) at startup. If its `versionCode` is higher than the installed app's, an update dialog appears. On confirm, the app downloads the APK and hands it to the system installer. The first time, Android will prompt to allow "Install unknown apps" for this app — that's the OS, not the app.

## Channel format (`latest.json`)

```json
{
  "versionCode": <int>,
  "versionName": "<x.y.z>",
  "apkUrl": "<https URL>",
  "notes": "<release notes>"
}
```

`apkUrl` uses the GitHub stable "latest release" redirect, so it doesn't have to be updated per release.
