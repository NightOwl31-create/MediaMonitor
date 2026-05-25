# Changelog

All notable changes to MediaMonitor are documented here.
The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and the project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.2.2] — 2026-05-25

### Added
- **Hindi (HI)** added as the 24th supported language
- Tooltips on icon-only buttons (password visibility, close, search) for screen reader / Talkback accessibility

### Changed
- Touch target of the sessions filter button enlarged from 28×28 to 40×40 (Material 3 spec compliance)
- `LanguageSelectionScreen` refactored to use `RadioGroup` (Flutter 3.32+ recommended API)
- Settings → Language picker now shows the full list of 24 languages in a scrollable bottom sheet

### Security
- `android:allowBackup="false"` set in the manifest — prevents Android Auto Backup from copying encrypted credentials whose Keystore keys aren't backed up (would have caused silent credential loss on device-to-device restore)
- `flutter_secure_storage` configured with `migrateWithBackup: true` to protect against credential loss on future cipher migrations

### Fixed
- Settings → Language was showing only French/English — now shows the full list of 24 supported languages

## [1.2.1] — 2026-05-24

### Added
- Tap a live session to open the detailed media sheet (same view as history)
- Result count displayed above search results
- Per-server error banner in "What's new" and Search (you keep results from the other server when one fails)

### Changed
- Bottom sheets for "Connect Jellyfin" / "Connect Plex" now fully translated (were partially hardcoded in French)

## [1.2.0] — 2026-05-23

### Added
- **20 new languages**: German, Spanish, Italian, Portuguese, Dutch, Swedish, Norwegian, Danish, Finnish, Polish, Czech, Hungarian, Russian, Ukrainian, Greek, Japanese, Korean, Chinese, Turkish, Arabic, Hebrew (22 total with French and English)
- **Language picker on first launch** (scrollable list of 22 languages, English pre-selected)
- **New "What's new" tab** showing the latest items added to your Plex and Jellyfin servers (with filters by server and type)
- **Global search** across all your libraries (magnifier icon in the AppBar)
- **Sticky date headers** in the playback history (stays anchored as you scroll)

### Changed
- Playback modes `Direct Play` and `Direct Stream` now translated through i18n
- Singular/plural fixed for French ("0 session active" instead of "0 sessions actives")
- Plex subtitle metadata now as rich as Jellyfin (codec, language, default/forced flags, sample rate)
- Playback completion badge differentiated per server: "Completed" on Plex (server already filters by watch threshold), "Stopped" on Jellyfin (raw event, no completion filter)

### Fixed
- Trailing 's' bug on French session counter

## [1.1.1] — 2026-05-22

### Added
- Full language names on the detail sheet (e.g. `English`, `French`) instead of opaque ISO codes (`ENG`, `FRA`) — covers ~60 languages
- Readable subtitle codec names (`SRT`, `PGS`, `ASS`, `WebVTT`…) instead of raw API values (`subrip`, `hdmv_pgs_subtitle`…)
- Automatic detection of audio/subtitle track variants: **VFF**, **VFQ**, **VFI**, **VOST**, **VOSTFR**, **VO**, **SDH**, **Commentary**, **Director**, **Audio description**

### Changed
- All dependencies upgraded to their latest stable versions
- Flutter SDK upgraded from 3.41.9 to 3.44.0
- `flutter_secure_storage` upgraded from v9 to v10 (new custom cipher implementation, deprecated `encryptedSharedPreferences` removed)
- `package_info_plus` upgraded from v8 to v10
- `flutter_lints` upgraded from v4 to v6

### Security
- R8 code shrinking and obfuscation enabled on release builds (reduces APK size by ~1.9 MB and makes reverse-engineering harder)
- ProGuard rules added for all reflection-based plugins (Tink, ICU, Play Core, etc.)

## [1.1.0] — 2026-05-21

### Added
- **Tautulli-style detail sheet** opened on tap from history or sessions, with poster, summary, technical metadata, and a close button
- **All audio and subtitle tracks** listed in the detail sheet (not just the first one), each on its own row with badges
- **Library statistics per server**: movie counts, series counts, episode counts — separated by type
- **Live server connectivity indicator** with ping check on the configuration screen
- Season/episode numbers (e.g. `S03E12`) displayed in Jellyfin history
- Jellyfin username resolution in history rows
- Relative dates ("5 min ago", "yesterday") in history
- French → English translation parity for all new strings

### Changed
- History no longer shows a useless scrollbar (history can contain thousands of items)
- Long-press from history no longer redirects to the server's web login page — a local detail sheet is shown instead

## [1.0.3] — 2026-05-21

### Added
- Persistent tab selection across app restarts
- Haptic feedback on key interactions
- Long-press on a session to copy details to clipboard

### Changed
- "Test connection" snackbar redesigned (was unreadable on dark theme)
- Inline server-test results instead of overlapping snackbars
- Snackbars switched to floating style for better visibility
- Improved empty-state messaging in history

### Fixed
- Duplicate "About" entry between the menu and the settings page

## [1.0.2] — 2026-05-20

### Added
- Dynamic version display in the About section
- "Test connection" button in server configuration

### Changed
- Network errors made less intrusive (no more shouting red banners for transient failures)

## [1.0.0] — 2026-05-17

### Added
- Initial public release on the Google Play Store
- Plex Media Server support
- Jellyfin support
- Live playback sessions view (both servers simultaneously)
- Playback history (unified across servers)
- Material 3 UI with light and dark themes
- French and English localisation
- Encrypted local storage of server credentials (Android Keystore)
