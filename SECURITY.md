# Security Policy

## Supported versions

Only the latest version published on the Google Play Store is actively supported with security updates.

| Version | Supported          |
|---------|--------------------|
| 1.1.x   | :white_check_mark: |
| 1.0.x   | :x:                |

## Reporting a vulnerability

If you discover a security vulnerability in MediaMonitor, please **do not open a public GitHub issue**.

Instead, use GitHub's **private vulnerability reporting** feature:

1. Go to the [Security tab](https://github.com/NightOwl31-create/MediaMonitor/security) of this repository
2. Click **"Report a vulnerability"**
3. Fill in the form — your report stays confidential between you and the maintainer

Please include:

- A description of the vulnerability
- Steps to reproduce
- The version of the app affected
- Any potential impact you have identified

You can expect:

- An acknowledgement within **7 days**
- A fix or a clear status update within **30 days**, depending on severity

There is no monetary bug bounty programme at this time, but credible reports will be credited in the [CHANGELOG](CHANGELOG.md) (unless you prefer to remain anonymous).

## Scope

In scope:

- The MediaMonitor Android app published on the Google Play Store
- The way the app handles credentials, network traffic, and local storage

Out of scope:

- Vulnerabilities in third-party libraries used by the app (please report those upstream)
- Vulnerabilities in Plex or Jellyfin servers themselves (report to their respective security teams)
- Social engineering or physical attacks
