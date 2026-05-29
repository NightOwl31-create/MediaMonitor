# Security Policy

## Supported versions

| Version | Supported |
| ------- | --------- |
| 2.0.x   | ✅        |
| 1.x     | ❌ (please upgrade) |

## Reporting a vulnerability

If you discover a security issue in MediaMonitor, please **do not** open a public GitHub issue.

Contact the maintainer privately by opening a [**private security advisory**](https://github.com/NightOwl31-create/MediaMonitor/security/advisories/new) on this repository.

Please include:
- A clear description of the issue and its impact
- Steps to reproduce (proof-of-concept welcome)
- The version of MediaMonitor and the Android OS where you observed it

You should receive an acknowledgement within **5 business days**. A fix or mitigation will be planned based on severity.

## Scope

In scope:
- Local credential storage (Android Keystore / `flutter_secure_storage`)
- Network communication with Jellyfin / Plex servers
- Background polling (WorkManager + isolate)
- The Plex OAuth flow

Out of scope (please report to the relevant vendor):
- Vulnerabilities in Jellyfin or Plex Media Server themselves
- Vulnerabilities in upstream Flutter plugins (please open an issue there as well)

## Cryptography

MediaMonitor relies on:
- The Android Keystore for credential storage
- The OS-provided TLS stack for HTTPS connections
- No homemade crypto

Release artifacts are signed and distributed exclusively through the Google Play Store, which guarantees signature integrity end-to-end (Play App Signing).
