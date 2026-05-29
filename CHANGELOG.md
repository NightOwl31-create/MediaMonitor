# Changelog

User-facing release notes for MediaMonitor. Format follows [Keep a Changelog](https://keepachangelog.com/), versioning is [SemVer](https://semver.org/).

## [2.0.0] — 2026-05-29

### Added
- **Multi-account** — Connect any number of Jellyfin and/or Plex servers, side by side. Per-server filters across Sessions, History and Recently Added.
- **Background notifications** *(opt-in)* — Three event types (new playback, transcoding kicked in, playback finished) with WorkManager polling (15-minute base, accelerated to 5 minutes when playback is active). Per-server filters and "remote viewers only" toggle.
- **Recently added** — Movies, episodes and shows recently added across all connected servers.
- **Global search** across all servers.
- **Token expired banner** with tap-to-reconnect when the background poll detects a 401.
- **Configure notifications guide** with one-tap deep-links to MIUI/HyperOS settings (autostart, per-app battery saver, notification settings).
- **Offline IP geolocation** — Country flag next to remote viewer IPs, computed entirely on-device.
- A small surprise hidden somewhere in the About screen.

### Changed
- **Unified filter sheet** — A single tune icon now opens a multi-group bottom sheet (Type / State / Server) with multi-select and "all checked" as default.
- **Cleaner Sessions/History UI**, faster scroll, sharper posters.
- Notifications channels rebuilt for proper sound and vibration on MIUI/HyperOS.

### Removed
- The user/title search bar in History (replaced by the unified filter sheet).
- The server URL display in Settings (no longer useful).
- The "Reconnect" button in Settings (the new banner does it automatically).

### Fixed
- Notifications icon disappearing on MIUI/HyperOS (vector silently rejected, now PNG).
- Plex "Recently Added" missing episodes and shows on some servers.
- Per-server filter being silently re-checked at every refresh.
- Various performance issues (smoother scroll, lower data usage, lower RAM pressure).

### Security
- Privacy policy fully updated to list every Android permission requested and document the on-device IP geolocation.

---

## [1.2.3] — 2026-05-25

### Added
- **Instant error feedback on Jellyfin sign-in** — credentials and network errors now appear in an inline banner instead of a delayed snackbar hidden behind the keyboard.
- **Redesigned Plex server picker** — the recommended connection (accessible everywhere, both Wi-Fi and cellular) is starred and sorted first. Servers shared by friends are hidden (admin access is required).
- **Brand icons on active sessions** — each playback now displays the actual brand logo of the device playing the media (Android, Apple, Chrome, Firefox, Safari, Windows, Xbox, PlayStation, Linux).
- **Live language picker on first launch** — both the title and the Continue button update in the language being selected, before confirmation.

---

## [1.2.2] — 2026-05-25

### Added
- **Hindi** added as the 24th supported language.
- Tooltips on icon-only buttons (password visibility, close, search) for screen reader / Talkback accessibility.

### Changed
- Touch target of the sessions filter button enlarged to Material 3 spec.
- Settings → Language picker now shows the full list of 24 languages in a scrollable bottom sheet (was hardcoded to FR/EN).

### Security
- `android:allowBackup="false"` set to prevent Android Auto Backup from copying encrypted credentials whose Keystore keys are not backed up.

---

## [1.2.1] — 2026-05-24

### Added
- Tap a live session to open the detailed media sheet (same view as History).
- Result count displayed above search results.
- Per-server error banner in Recently Added and Search (results from working servers are still shown when one fails).

### Changed
- Connect Jellyfin / Connect Plex bottom sheets now fully translated (some labels were hardcoded in French).

---

## [1.2.0] — 2026-05-23

### Added
- **20 new languages**: German, Spanish, Italian, Portuguese, Dutch, Swedish, Norwegian, Danish, Finnish, Polish, Czech, Hungarian, Russian, Ukrainian, Greek, Japanese, Korean, Chinese, Turkish, Arabic, Hebrew (23 total, plus Hindi added in 1.2.2).
- **Language picker on first launch** (scrollable list, English pre-selected).
- **Recently Added tab** showing the latest items added to your Plex and Jellyfin servers (with filters by server and type).
- **Global search** across all your libraries (magnifier icon in the AppBar).
- **Sticky date headers** in the playback history.

### Changed
- Playback modes (Direct Play / Direct Stream) translated through i18n.
- Singular / plural fixed for French.
- Plex subtitle metadata now as rich as Jellyfin (codec, language, default/forced, sample rate).
- Playback completion badge differentiated per server: "Completed" on Plex, "Stopped" on Jellyfin (raw event).

---

## [1.1.1] — 2026-05-22

### Added
- Full language names on the detail sheet instead of opaque ISO codes (covers ~60 languages).
- Readable subtitle codec names (`SRT`, `PGS`, `ASS`, `WebVTT`…) instead of raw API values.
- Automatic detection of audio/subtitle track variants: VFF, VFQ, VFI, VOST, VOSTFR, VO, SDH, Commentary, Director, Audio description.

### Security
- R8 code shrinking and obfuscation enabled on release builds.

---

## [1.1.0] — 2026-05-21

### Added
- **Tautulli-style detail sheet** opened on tap from History or Sessions.
- All audio and subtitle tracks listed in the detail sheet (not just the first one).
- **Library statistics per server**: movie / series / episode counts.
- **Live server connectivity indicator** with ping check.
- Season/episode numbers (`S03E12`) displayed in Jellyfin history.
- Jellyfin username resolution in history rows.
- Relative dates ("5 min ago", "yesterday") in history.

### Changed
- Long-press from history no longer redirects to the server's web login.

---

## [1.0.3] — 2026-05-21

### Added
- Persistent tab selection across app restarts.
- Haptic feedback on key interactions.
- Long-press on a session to copy details to clipboard.

### Changed
- Test connection results now displayed inline instead of stacked snackbars.
- Snackbars switched to floating style for better visibility on dark theme.

### Fixed
- Duplicate "About" entry between the menu and the settings page.

---

## [1.0.2] — 2026-05-20

### Added
- "Test connection" button on the sign-in form.

### Changed
- Network errors are now displayed less intrusively (subtle banner instead of full red overlay).
- App version is now read dynamically from the manifest.

---

## [1.0.1] — 2026-05-18

### Added
- Jellyfin password is now optional (for accounts that don't require one).
- Admin-only warning when the History endpoint requires elevated rights on Jellyfin.

---

## [1.0.0] — 2026-05-17

First public release. Jellyfin + Plex support, Plex OAuth, light/dark theme, French/English i18n, configurable refresh interval.
