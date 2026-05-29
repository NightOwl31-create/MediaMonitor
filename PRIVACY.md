# Privacy Policy — MediaMonitor

_Last updated: 2026-05-29_

**TL;DR**: MediaMonitor does not collect, send, or sell any personal data. Everything stays on your device.

## What data does MediaMonitor handle?

MediaMonitor connects to **your own** Jellyfin and/or Plex media servers to display sessions and playback history. To do so, the app stores **locally on your device**:

- The URL of your Jellyfin server (e.g. `https://jellyfin.example.com`)
- Your Jellyfin authentication token (issued by your server)
- The URL of your Plex server
- Your Plex authentication token (issued by your Plex account)
- Your UI preferences (theme, language)

All of the above is stored:
- **Encrypted** using Android Keystore (via `flutter_secure_storage`) for tokens and server URLs
- Locally in app preferences for theme and language

**This data never leaves your device.** It is sent **only** to the media server(s) you configured, in order to query session data and history.

## What MediaMonitor does NOT do

- ❌ No analytics, no telemetry
- ❌ No advertising, no tracking
- ❌ No data sharing with third parties
- ❌ No account on our side (we don't have a server)
- ❌ No background tracking of your media activity

## Third-party services

MediaMonitor communicates with:

- **The Jellyfin server you configure** — your private/personal server. We follow the [official Jellyfin API](https://jellyfin.org/docs/general/server/api/). MediaMonitor is **not affiliated with the Jellyfin project**.
- **The Plex server you configure** + **plex.tv** (only during the initial OAuth sign-in to obtain a token) — your private/personal server and the official Plex sign-in service. MediaMonitor is **not affiliated with Plex Inc.**

We have no influence over what these services log on their side. Refer to their own privacy policies.

## Required permissions

- **Internet access** (`android.permission.INTERNET`): required to reach your media server.
- **Post notifications** (`android.permission.POST_NOTIFICATIONS`, Android 13+): required only if you enable the optional playback notifications. You can deny it; the app stays usable.
- **Receive boot completed** (`android.permission.RECEIVE_BOOT_COMPLETED`): used by Android WorkManager to reschedule the background polling after a device reboot. No code of ours runs on boot — only the OS scheduler.

## IP geolocation (offline)

When playback notifications are enabled, MediaMonitor displays the country flag of remote viewers (for context only). The IP→country lookup is performed **entirely on-device** against a local snapshot of the [DB-IP IP-to-Country Lite](https://db-ip.com/db/download/ip-to-country-lite) dataset (licensed CC-BY 4.0). **No IP, hostname, or query leaves your device.** The snapshot is refreshed at build time (release builds only) and shipped in the APK.

## Cleartext traffic (HTTP) on LAN

Many self-hosted Jellyfin/Plex setups are reached over plain HTTP on a local network (no TLS). MediaMonitor therefore declares `android:usesCleartextTraffic="true"` in its manifest so users can reach `http://192.168.x.x` servers. Android does **not** support restricting cleartext to RFC1918 ranges only, so this permission is global. In practice MediaMonitor only ever contacts the servers you explicitly configure plus `plex.tv` (HTTPS, OAuth sign-in only) — no other host. If you only use HTTPS servers, the cleartext capability is never exercised.

## Your control

You can:
- Disconnect any server at any time from **Settings → Connections**, which deletes the corresponding stored credentials.
- Uninstall the app, which removes all local data including encrypted credentials.

## Contact

For privacy questions, open an [issue](https://github.com/NightOwl31-create/MediaMonitor/issues) on this repository.
