# MediaMonitor

> Monitor your Plex and Jellyfin servers from your Android phone.

[![Latest version](https://img.shields.io/badge/version-1.2.2-blue.svg)](https://github.com/NightOwl31-create/MediaMonitor/releases)
[![Platform](https://img.shields.io/badge/platform-Android%207.0%2B-brightgreen.svg)]()
[![Languages](https://img.shields.io/badge/languages-24-success.svg)]()
[![License](https://img.shields.io/badge/license-proprietary-lightgrey.svg)](#license)

MediaMonitor is a lightweight Android app that lets you keep an eye on what's playing on your home media servers (Plex and Jellyfin), browse playback history, and check library statistics — all from a clean Material 3 interface.

---

## Download

**[Get it on Google Play](https://play.google.com/store/apps/details?id=com.mediamonitor.media_monitor)**

*Published by NightOwl31 on the Play Store.*

---

## Features

- **Live sessions** — see who's watching what, in real time, on both Plex and Jellyfin servers simultaneously
- **Playback history** — unified across servers, with usernames, posters, S/E episode numbers, sticky date headers
- **What's new tab** — latest items added to your Plex and Jellyfin servers, with per-server and per-type filters
- **Global search** — find movies and shows across all your libraries (Plex + Jellyfin merged)
- **Library statistics** — counts of movies and series per server, separated by type
- **Detailed media sheet** — Tautulli-style technical info on tap: video codec, bitrate, all audio tracks, all subtitle tracks
- **Smart language & codec display** — full language names (`English`, `French`…) instead of opaque codes (`ENG`, `FRA`), readable codec names (`SRT`, `PGS`, `AAC`…) instead of raw values
- **Track variant detection** — automatically identifies SDH, VFF, VFQ, VOST, VOSTFR, Commentary, Director's cut, Audio description
- **Server connectivity check** — live ping indicator for each configured server
- **24 languages** — language picker on first launch; supports English, French, German, Spanish, Italian, Portuguese, Dutch, Swedish, Norwegian, Danish, Finnish, Polish, Czech, Hungarian, Russian, Ukrainian, Greek, Hindi, Japanese, Korean, Chinese, Turkish, Arabic, and Hebrew
- **Offline-friendly** — no account, no cloud, no telemetry. The app talks only to the servers you configure

## Supported servers

| Server   | Status         |
|----------|----------------|
| Plex     | ✅ Full support |
| Jellyfin | ✅ Full support |

## Privacy & security

MediaMonitor is built to be transparent and respectful of your data:

- **No tracking, no analytics, no ads.**
- **No data is sent to third parties.** The app communicates only with the Plex and Jellyfin servers you explicitly configure.
- **Credentials are stored locally** in Android's encrypted secure storage (Android Keystore via `flutter_secure_storage`).
- **Only required Android permission**: `INTERNET` (to reach your servers).
- **R8 code shrinking and obfuscation** is enabled on release builds.

Read the full [Privacy Policy](PRIVACY.md).

## Tech stack

- [Flutter](https://flutter.dev/) (Dart) with Material 3
- Android 7.0+ (API 24), targeting Android 15 (API 35)
- Plex Media Server REST API and Jellyfin REST API
- Encrypted local storage via [flutter_secure_storage](https://pub.dev/packages/flutter_secure_storage)

## FAQ

**Is MediaMonitor open source?**
No. The source code is proprietary. See [PRIVACY.md](PRIVACY.md) for confidentiality guarantees.

**Will an iOS version be released?**
No plans at the moment. The app is Android-only.

**Why not publish on F-Droid?**
F-Droid requires fully open-source code. Since MediaMonitor is not open source, it cannot be hosted there.

**I found a bug or want to suggest a feature.**
Please [open an issue](https://github.com/NightOwl31-create/MediaMonitor/issues).

## Changelog

See [CHANGELOG.md](CHANGELOG.md) for the full version history.

## Security

If you discover a security issue, please refer to [SECURITY.md](SECURITY.md) for responsible disclosure instructions.

## License

The source code is proprietary and not publicly available.
The contents of this repository (README, documentation, screenshots) are © NightOwl31 — All rights reserved.
