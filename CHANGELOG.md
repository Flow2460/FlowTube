# Changelog

All notable changes to **FlowTube** are documented in this file.
Official releases and installers are available on [itch.io](https://itch.io).

---

## [1.5] - 2026-11-26
### Added
* Multi-browser support (`chrome`, `brave`, `firefox`, `edge`, `safari`).
* Added `browser` configuration option in `app_config.ini`.

### Changed
* Iterative update.
* Renamed `app_config.ini` parameter `app_chrome_profile_dir` to `app_browser_profile_dirs`.

---

## [1.4] - 2026-09-11
### Changed
* Iterative maintenance update (no feature or functional changes).

---

## [1.3] - 2026-07-08
### Changed
* Iterative maintenance update (no feature or functional changes).

---

## [1.2] - 2026-03-26
### Added
* Replaced the top blue WMP bar with dedicated **CONFIG** (opens `app_config.ini` for quick file format/setting edits) and **REPLAY** (launches Windows Media Player) buttons.

### Changed
* Made **windowed mode** the new UI default.
* Updated `About.txt`.

### Fixed
* Fixed UI resolution scaling issues so the interface renders cleanly across different screen sizes.

---

## [1.1] - 2026-03-15
### Fixed
* Fixed high-resolution monitor UI scaling issues.
* Resolved minor bugs, including a long-load quit issue.

---

## [1.0] - 2025-12-26
### Added
* Initial public release of **FlowTube** for Windows.
* Controlled Chrome browser integration for manual YouTube browsing and automatic video metadata extraction.
* 3-slot queue system with online metadata search, Creative Commons cover art lookup (with local placeholder fallback), millisecond start/end audio trimming, FFmpeg audio conversion, and ID3 tag/artwork embedding.
* Top toolbar button to play download history in Windows Media Player.
