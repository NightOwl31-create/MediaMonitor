# Privacy Policy

_Last updated: 2026-05-22_

MediaMonitor is designed with privacy as a core principle. This document describes exactly what the app does — and what it does **not** do — with your data.

## TL;DR

- **No personal data is collected.**
- **No analytics, no tracking, no advertising.**
- **No data is sent to any third party.**
- The app only communicates with the **Plex and Jellyfin servers you configure yourself**.
- Credentials are stored locally in **Android's encrypted secure storage**.

## What data does the app process?

When you configure a server in MediaMonitor, the app stores the following information **locally on your device only**:

- Server URL (e.g. `http://192.168.1.10:8096`)
- API token / API key required to authenticate against that server

These credentials are stored in Android's secure storage (Android Keystore, via the `flutter_secure_storage` library). They are never transmitted anywhere except to the corresponding server you configured.

While the app is running, it queries your servers' REST APIs to fetch:

- Currently active playback sessions
- Playback history
- Library statistics (movie / series / episode counts)
- Per-item technical metadata (codec, bitrate, audio and subtitle tracks)

This data is displayed in the UI and is never persisted beyond the in-memory session.

## Network access

MediaMonitor requests a single Android permission: `INTERNET`. It uses this permission to:

- Talk to the Plex and/or Jellyfin servers whose URL you provide
- Fetch poster images from your servers via the same connection

The app supports clear-text (`http://`) traffic so that it can reach servers running on your local network without forcing you to set up HTTPS. No traffic is ever sent to MediaMonitor's developers or to any third party.

## No analytics, no crash reporting (beyond Play Console defaults)

MediaMonitor does not embed any third-party analytics SDK (no Firebase Analytics, no Google Analytics, no Crashlytics, no Sentry, etc.).

Google Play automatically collects anonymous crash and ANR data when an app is installed via the Play Store; this is a platform-level behaviour controlled by Google and your device settings, not by MediaMonitor. You can disable this in your device's Google Play settings if you wish.

## No ads

MediaMonitor does not display advertisements of any kind and contains no advertising SDK.

## Children

MediaMonitor is not directed at children and does not knowingly collect any data from any user.

## Changes to this policy

This document may be updated alongside new versions of the app. Significant changes will be reflected in the [CHANGELOG](CHANGELOG.md).

## Contact

For any privacy-related question, please [open an issue](https://github.com/NightOwl31-create/MediaMonitor/issues) on the GitHub repository.
