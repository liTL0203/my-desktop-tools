# Changelog

> All version release notes. Latest version first.

**[中文版](./CHANGELOG.zh-CN.md)** | **English**

---

# v0.37.0 (2026-08-08)

## New Features

- **Plugin Uninstall**: Added uninstall button to plugin marketplace cards, allowing users to remove installed plugins directly from the marketplace interface
- **Standalone Window Stop-on-Close Option**: Plugins with standalone window mode can now configure `stopOnClose: true` to automatically stop the sidecar process when the window is closed

## Bug Fixes

- **Plugin Frame Loading Mask**: Fixed loading mask not dismissing when plugin iframe content loads via blob URL; added proper blob URL revocation to prevent memory leaks
- **AI Log Detail Expansion**: Fixed AI request log detail expansion not rendering properly when response content contains complex nested JSON
- **Standalone Window Mode Detection**: Fixed mode detection mechanism that incorrectly identified popup vs inapp mode due to WebView runtime differences in blob URL hash handling

---

# v0.36.2 (2026-08-08)

## Bug Fixes

- **Standalone Window Mode Detection**: Fixed plugin detection mechanism for standalone window mode. The iframe window name is now used as the primary mode detection signal (set by core), replacing the unreliable hash-based detection that was affected by WebView runtime differences in blob URL hash handling

---

# v0.36.1 (2026-08-08)

## Bug Fixes

- **Modal/Dialog Background Opacity**: Replaced semi-transparent modal background variables (`--modal-material`, `--popover-bg`) with fully opaque solid color variables (`--modal-solid-bg`, `--popover-solid-bg`) across all 11 popup components, and removed `backdrop-filter: blur()` declarations that caused visual bleed-through in dark themes
- **QuickAction Panel Transparency**: Changed QuickAction window's native `transparent` property from `true` to `false`, preventing desktop content from showing through the semi-transparent panel background
- **Plugin Marketplace Version Field**: Added `version` field to `plugins.json` catalog entries (read from manifest.json), and updated frontend parsing logic to prioritize catalog version with `versions.json` fallback, fixing incorrect version display in the marketplace

## Improvements

- **Plugin Template Default Private**: Plugin scaffolding template (`plugin-dev-kit`) now defaults to `"private": true` in manifest.json, preventing accidental public marketplace exposure of new plugins before they are ready
- **Release Script Private Plugin Prompt**: Release script now detects private plugins and interactively asks developers whether to publish them as public, with `--publish-private` CLI parameter for non-interactive environments
- **Standalone Window Hash Injection**: Added hash marker injection for standalone plugin window mode, improving plugin identification in independent windows

---

# v0.36.0 (2026-08-07)

## New Features

- **AI Service Settings Page Redesign**: Completely refactored the AI service settings page with improved layout, provider management, and API key configuration flow. Added request log detail expansion for inspecting individual AI call payloads and responses
- **AI Usage Tracking Enhancement**: Enhanced usage tracking with per-model statistics and improved charts visualization on the settings page
- **Context Data Passing Optimization**: Optimized context data delivery mechanism for standalone plugin windows, improving plugin-to-core communication reliability

## Improvements

- **AI Settings UI Polish**: Refined AI settings interface styling details for better visual hierarchy and user experience
- **Plugin Frame Communication**: Improved PluginFrame component to better handle AI-related plugin interactions
- **Resource Monitor Tab**: Updated resource monitor tab component for consistency with the new AI settings design

---

# v0.35.0 (2026-08-05)

## New Features

- **AI Service Infrastructure**: Built-in AI service backend with multi-model support (OpenAI-compatible, Ollama, Anthropic Claude). Includes API key management, usage tracking, and a dedicated AI service settings page with usage charts
- **Plugin Custom Icons**: Plugins can now provide custom icons (`icon.png`) in their manifest, displayed in the sidebar navigation, tool cards, and quick action panel
- **Background Task Indicator Optimization**: Refactored the background task progress indicator with improved responsiveness and smoother animation

## Improvements

- **Markdown Rendering**: Implemented lazy-loading for the Markdown renderer component, reducing initial bundle size and improving page load performance
- **Workspace Architecture**: Completed the monorepo split into `mydt-core` + `mydt-plugins` multi-workspace layout, with release scripts fully adapted to the new path configuration
- **Release Attribution Filtering**: Added automated commit attribution filtering to the release pipeline, preventing plugin changes from being incorrectly included in core release notes

---

# v0.34.0 (2026-08-03)

## New Features

- **Afdian Settings Link**: Added external link to the Afdian (爱发电) sponsorship page directly from the Settings page, making it easier for users to support the project

## Improvements

- **Marketplace Data Accuracy**: The `plugins.json` catalog metadata now reads actual download sizes from built ZIP files instead of relying on static manifest values, ensuring accurate size display in the marketplace
- **Dev Server Configuration**: Changed dev server URL from `localhost` to `127.0.0.1` for improved reliability and reduced DNS resolution overhead during development

---

# v0.33.0 (2026-07-29)

## New Features

- **Plugin Marketplace**: Browse, filter, and install plugins directly from the in-app marketplace. Features banner carousel with featured plugins, category single-select and status multi-select cross-filtering, and a refresh button to pull the latest catalog
- **Marketplace Data Source**: Auto-generated `plugins.json` catalog metadata from plugin manifests, served via Gitee raw URL with automatic `updatedAt` timestamps extracted from CHANGELOG entries
- **Markdown Changelog Rendering**: Plugin update logs and release notes are now rendered as properly formatted Markdown with XSS-safe sanitization (via `marked` + `dompurify`). Structured changelog data replaces raw text for consistent display across update dialogs, detail popups, and version history

---

# v0.32.0 (2026-07-28)

## New Features

- **Plugin Smart Unloading**: Intelligent plugin process lifecycle management with KeepAlive cache optimization. Inactive plugin processes are automatically unloaded to reduce memory footprint, while keeping their state cached for instant reactivation
- **Communication Log Toggle**: Per-plugin communication log enable/disable switch with optimized logging performance. Users can now control which plugins' IPC traffic is logged
- **Background Task Progress Indicator**: Status bar component showing real-time progress of background operations (scans, downloads, plugin operations) with animated indicators
- **Main Window Idle Memory Release**: Automatically releases unused WebView2 memory when the main window is idle, keeping baseline memory footprint within 30-80MB target
- **Quick Launcher Configurable Hotkeys**: Users can now customize the global hotkey for Quick Launcher toggle via Settings → Hotkey. Full hotkey recorder UI with visual key capture
- **Quick Launcher Pin Mode**: Pin the Quick Launcher popup to keep it visible while interacting with other windows. Click the pin icon to toggle always-on-top behavior
- **Skeleton Loading Screens**: All major pages (Home, Plugin Manager, Settings) now show skeleton placeholders during initial data loading instead of blank screens
- **Quick Launcher Standalone Window**: Quick Launcher applications can now be opened in independent desktop windows with configurable size and behavior

## Improvements

- **Plugin Management Architecture**: Refactored plugin orchestration and performance monitoring for better modularity and maintainability
- **Modal & Icon Selector UX**: Polished modal dialog styles and expanded icon selector with sticky search and improved scrolling behavior
- **Context Menu Robustness**: Enhanced right-click menu boundary detection, scroll-to-close, and mutual exclusion between multiple menus
- **Quick Launcher Search**: Optimized drag interaction logic and client-side filtering for recent items
- **Log System Tuning**: Adjusted log levels for production and reduced plugin log file size limits
- **Dependency Updates**: Updated Vue, Vite, Naive UI, Tauri CLI, and other dependencies to latest stable versions

## Bug Fixes

- Fixed context menu boundary detection failures and scroll-close behavior
- Fixed Quick Launcher search returning empty results when background scan completes
- Fixed standalone window right-click menu security issue and concurrent creation race condition
- Fixed MSI download checksum and installation file lock contention issues
- Fixed Quick Launcher "Recent" tab showing empty when app cache is incomplete

---

# v0.31.0 (2026-07-26)

## New Features

- **Privacy Controls**: Three-tier data collection controls (Core/Aggregate/Detailed) in Settings → Privacy. All optional analytics are opt-in only and disabled by default
- **Privacy Policy Dialog**: View detailed privacy policy from Settings, including data collection levels, your rights, and data storage practices
- **First-Run Consent**: New consent dialog on first launch to choose your analytics sharing preferences
- **Delete My Data**: Clear all uploaded cloud analytics data with one click from Settings → Privacy
- **Legal Documents**: Privacy Policy and Disclaimer (bilingual) are now bundled with the application installer
- **Smart Unload (M1)**: Plugin windows automatically release WebView memory after idle timeout (Level 1/2 tiered suspension). Configurable in Settings → Performance
- **Main Window Idle Release**: Main window WebView is destroyed after configurable idle timeout when minimized to tray. Tray click dynamically rebuilds the window
- **Background Task Indicator**: Status bar shows running background tasks (plugin startup, update checks, app scanning) with VSCode-style progress display and click-to-expand details
- **Performance Optimization (S1-S5 + L1-L3)**: Resource polling self-adaptation, log batching, Condvar sleep, ArcSwap cache, quick-launcher lazy creation, iframe keep-alive pool (LRU=3), watchdog thread merged into heartbeat

### Improvements

- **Log System Audit**: Sensitive info redaction (paths, device IDs, sponsor IDs downgraded to debug), high-frequency info logs downgraded to debug, plugin log cap reduced from 5MB to 3MB
- **Dependency Upgrades**: lnk 0.5→0.6 (fixes panic bug), png 0.17→0.18, ico 0.4→0.5, pinyin 0.10→0.11, winreg 0.52→0.56, ~80 transitive deps updated
- **i18n Fix**: HotkeyRecorder component localized (Clear/Restore Default), app manager table column overflow fixed for English mode

---

# v0.30.0 (2026-07-18)

## New Features

- **Multi-Remote Architecture**: Refactored release pipeline to support independent publishing to multiple remote repositories, enabling separated core and plugin release workflows
- **Release Automation**: Added standardized release command templates and automated task flow for streamlined version publishing
- **Plugin Settings i18n**: Comprehensive internationalization for all plugin settings operations, including install, uninstall, enable, disable, and configuration actions
- **Multi-Source Download Strategy**: Added ghproxy fallback for GitHub Releases downloads, automatically detecting optimal source for users in different regions

## Bug Fixes

- **GitHub Release Asset Naming**: Fixed MSI download URL mismatch caused by GitHub converting spaces to dots in asset filenames, now correctly tracks actual asset name
- **Window Visibility**: Fixed production build window initialization issue by restoring visible:true in tauri.conf.json

## Improvements

- **Startup Performance**: Optimized application startup sequence for faster launch times and smoother user experience
- **Production Manifest**: Pomodoro plugin build script now strips development configurations to generate clean production manifests
- **MSI Installer**: Added bilingual WiX installer UI with custom banner and dialog images for a polished installation experience

---

# v0.29.0 (2026-07-16)

## New Features

- **Plugin Cache Clearing**: Added plugin cache clearing functionality to resolve issues where stale cached data prevents upgrades from being detected
- **Plugin Force-Fetch Enhancement**: Improved plugin manifest force-fetch mechanism with better cache invalidation for more reliable upgrade detection

## Improvements

- **Documentation**: Updated plugin upgrade module documentation with comprehensive v0.28.0 changelog records

---

# v0.28.0 (2026-07-16)

## New Features

- **Plugin Upgrade Force-Fetch**: Plugins now force-fetch the latest manifest during upgrade checks, ensuring users always get up-to-date version information

## Bug Fixes

- **Version Consistency**: Added build-time validation to detect version mismatches between `package.json` and `manifest.json` before packaging, preventing corrupted plugin upgrades
- **Plugin Upgrade Reliability**: Fixed plugin upgrade logic and enhanced ZIP extraction with better error handling

---

# v0.27.0 (2026-07-15)

## Bug Fixes

- **Plugin Upgrade**: Fixed plugin upgrade logic and enhanced ZIP extraction functionality, improving upgrade reliability and error handling

## Improvements

- **Documentation**: Added quick start guide and API reference documentation for better developer onboarding experience

---

# v0.26.0 (2026-07-15)

## Bug Fixes

- **Version History Language Switching**: Fixed an issue where version history records did not switch language correctly when changing the application language setting

## Improvements

- **Bilingual Release Docs**: Release repository now generates independent English (`README.md`, `CHANGELOG.md`) and Chinese (`README.zh-CN.md`, `CHANGELOG.zh-CN.md`) files, enabling Gitee's automatic language switching
- **Plugin Development Documentation**: Updated plugin development guide with correct repository clone address and template path configuration

---

# v0.25.0 (2026-07-15)

## New Features

- **Plugin Settings Directory**: Quickly open a plugin's local settings directory from the plugin manager, making it easier to access configuration files
- **Plugin Upgrade Dialog**: Improved plugin upgrade dialog with clearer version information display and better user experience

## Improvements

- **Bilingual Validation**: Enhanced release pipeline with early pre-build validation for bilingual release notes format, preventing wasted build time on non-compliant input

---

# v0.24.0 (2026-07-15)

## New Features

- **Resource Table i18n**: Resource table columns and content now support automatic Chinese/English switching, following the core application language setting
- **Bilingual Release Flow**: Release process now fully supports bilingual format, ensuring all downstream artifacts (update notifications, changelogs) are delivered in both languages

---

# v0.23.0 Release Notes (2026-07-15)

## Bug Fixes
- **Update Installation Fix**: Fixed file locking issues during the update installation process, improving auto-update success rate

## New Features
- **Bilingual Release Notes**: Update notification popups now support bilingual (Chinese/English) display, further enhancing the internationalization experience

## Improvements
- **Documentation System**: Improved version history document structure with quick-start guide and API reference documentation

---

# v0.22.0 Release Notes (2026-07-15)

## New Features
- **Markdown Rendering Support**: Release notes in update notification popups now support Markdown format parsing, with a new universal Markdown parsing utility module for improved formatting and readability

---

# v0.21.0 Release Notes (2026-07-14)

## New Features
- **Internationalization (i18n)**: Integrated vue-i18n for full-stack internationalization architecture, supporting Chinese/English language switching across settings page, statistics panel, plugin names, and other core UI
- **Plugin Name Localization**: Plugin display names now automatically switch based on system language, improving the multilingual user experience

## Improvements
- **Plugin Settings Architecture**: Extracted plugin settings update logic into standalone functions, reducing coupling and improving maintainability
- **Documentation Cleanup**: Removed outdated quick-start guide and API reference docs to reduce maintenance burden

---

# v0.20.0 Release Notes (2026-07-14)

## New Features
- **Brand New App Icon**: Adopted Apple HIG design style, combining "paw print + toolbox" concept with Apple system blue (#007aff / #0a84ff) gradient and frosted glass texture. Fully replaced the old icon to enhance brand recognition and visual refinement

---

# v0.19.0 Release Notes (2026-07-14)

## New Features
- **Custom Title Bar**: Implemented a custom window title bar to replace the native Windows window decoration, providing a more refined cross-platform consistent experience
- **Update Detection Source Tracking**: Added update detection source options to distinguish between manual checks and automatic detections, enabling precise tracking of update trigger paths

## Improvements
- **Documentation Cleanup**: Removed outdated quick-start guide and API reference docs to reduce maintenance burden

---

# v0.18.0 Release Notes (2026-07-13)

## New Features
- **Plugin Category System**: Added `category` field; proxy-switch plugin categorized as `network-control`, laying the foundation for future plugin category filtering
- **Plugin Version History Enhancement**: Version history composable now prioritizes reading from standalone CHANGELOG.md files

## Bug Fixes
- **Search Bar Truncation Fix**: Fixed text truncation issue in the search bar across different viewport widths, improving responsive adaptation

## Improvements
- **proxy-switch Plugin Upgraded to v2.5.0**: Added global hotkeys, TCP request logging, dashboard navigation, traffic chain import/export, dynamic network interface listing; improved elevation communication mechanism and startup performance
- **CHANGELOG Generation Fix**: Fixed version sorting and date source logic in release.mjs to ensure correct semantic version ordering and accurate dates
- **Documentation Cleanup**: Removed outdated security authentication docs and search bar validation scripts, streamlining project documentation structure

---

# v0.17.0 Release Notes (2026-07-13)

## New Features
- **Plugin Settings Default Path**: Plugin settings page now auto-fills default paths, improving configuration efficiency
- **Selective Plugin Release**: release.mjs now supports `--plugins` argument to build only specified plugins (e.g., `--plugins=proxy-switch`), skipping unchanged plugins and significantly reducing release time

## Bug Fixes
- **Grid Layout Overflow Fix**: Fixed horizontal overflow issue in homepage category grid layout and responsive breakpoint adaptation

## Improvements
- **Homepage Layout Optimization**: Optimized responsive layout logic for RecentTools and CategoryGrid components
- **Plugin Settings Enhancement**: Plugin settings composable now supports default path generation and auto-fill
- **Release Script Fix**: Fixed duplicate code block causing parse errors in release-with-sign.ps1
- **Release Script Enhancement**: release-with-sign.ps1 now supports -Plugins argument passthrough for end-to-end selective releases

---

# v0.16.0 Release Notes (2026-07-13)

## New Features
- **Selective Plugin Release**: release.mjs now supports `--plugins` argument to build only specified plugins (e.g., `--plugins=proxy-switch`), skipping unchanged plugins and significantly reducing release time

## Improvements
- **Release Script Fix**: Fixed duplicate code block causing parse errors in release-with-sign.ps1
- **Release Script Enhancement**: release-with-sign.ps1 now supports -Plugins argument passthrough for end-to-end selective releases

---

# v0.15.0 Release Notes (2026-06-22)

## Upgrades
- Rust toolchain upgraded to 1.96.0
- sysinfo 0.38 → 0.39 (system information)
- rusqlite 0.39 → 0.40 (SQLite database engine)
- windows crate 0.58 → 0.62 (Windows API bindings)
- Vite 7 → 8 (frontend build tool)
- TypeScript 5.7 → 6.0
- ESLint 9 → 10
- UnoCSS 66 → latest
- vue-tsc 2 → 3
- @types/node 24 → 26

## Plugin Dependency Upgrades
- proxy-switch: axum 0.7 → 0.8, ipstack 0.4 → 1.0

---

# v0.14.0 Release Notes (2026-06-18)

## New Features
- Integrated Afdian payment system for plugin launch paywall and device code verification
- Added encrypted key-value storage (secure_store), replacing plaintext file storage to protect sensitive data
- Enhanced plugin security mechanism with device identification codes for sponsorship verification

## Refactoring
- Refactored plugin communication transport layer, optimized JSON-RPC error handling and timeout mechanisms
- Removed deprecated Tauri commands, streamlining backend API interface structure

## Documentation
- Updated AI development guidelines to v4.0, improving Qoder CN IDE configuration framework
- Added security and authentication mechanism documentation
- Updated project documentation structure and backend architecture docs

## Dependency Upgrades
- Upgraded project dependencies to latest versions, added TypeScript-related dependencies

---

# v0.13.0 Release Notes (2026-06-17)

## New Features
- System tray menu now displays plugin quota indicator, showing current entitlements (unlimited plugins during trial period, max 3 for free tier after expiration)

---

# v0.12.0 Release Notes (2026-06-16)

## New Features
- Added plugin count limit functionality (1 plugin in development environment, 3 in production)
- Added automatic plugin process cleanup on application exit, ensuring no orphan processes remain
- MSI installation now enforces administrator privileges to ensure sidecar plugin processes have sufficient system permissions

## Improvements
- Removed NSIS installer, unified to MSI as the sole installer format
- Simplified frontend update detection logic, unified to MSI update path
- Application exit now uses Windows Job Object as fallback for child process cleanup, preventing process leaks

---

# v0.11.0 Release Notes (2026-06-16)

## New Features
- Added plugin launch paywall mechanism; unpaid users see a payment guidance dialog when launching plugins
- Upgraded device identification code algorithm, generating 32-bit SHA-256 digest from multi-source hardware fingerprints (CPU/motherboard/serial numbers)
- Support for precise navigation from payment gateway to the sponsorship verification section in settings

## Improvements
- Optimized payment dialog UI design following Apple HIG guidelines
- Improved trial period expiration and time rollback detection prompt text for clearer guidance
- Enhanced payment interception response parsing with JSON format support

---

# v0.10.0 Release Notes (2026-06-15)

## New Features
- Added device identification code for sponsorship verification binding
- Added application single-instance lock to prevent duplicate launches
- Added Apple HIG-style header navigation design
- Log viewer now supports keyboard shortcuts (Ctrl+F search, Ctrl+E export, Space pause/resume)

## Improvements
- Redesigned update dialog with expand/collapse, ESC close, and background blur effects
- Optimized plugin version history fetching: prioritizes standalone CHANGELOG.md, falls back to ZIP extraction
- Plugin download repository README now includes version history link column
- Enhanced proxy-switch plugin rule management with rule testing and statistics reset
- Upgraded Vue, ESLint, Prettier and other core dependencies

## Bug Fixes
- Fixed grid layout horizontal overflow issue
- Fixed performance issue from repeated tray menu rebuilding
- Fixed plugin version history dialog not displaying remote new version content
- Fixed plugin upgrade download failure due to CORS restrictions

---

# v0.9.1 Release Notes (2026-06-15)

## Improvements
- Optimized plugin version history fetching: prioritizes standalone CHANGELOG.md file (a few KB), falls back to ZIP extraction
- Enhanced publishing workflow: plugins now automatically generate standalone CHANGELOG.md files during release for in-app version history viewing
- Plugin download repository README now includes a version history link column

## Bug Fixes
- Fixed issue where plugin version history dialog could not display remote new version content
- Fixed plugin upgrade download failure due to CORS restrictions

---

# v0.9.0 Release Notes (2026-06-14)

## New Features
- Added time-of-day distribution chart and usage habit insights
- Plugin upgrade UI now displays download progress and version diff details
- Plugin resource monitor table now features upgrade banner and quick upgrade entry

## Improvements
- Introduced Apple HIG design system, comprehensively redesigned plugin management UI visual style
- Unified theme color system to improve overall visual consistency
- Refactored plugin upgrade workflow with Rust-side ZIP download and progress monitoring
- Optimized table hover effects and card shadow styles

---

# v0.8.0 Release Notes (2026-06-14)

## New Features
- Added system wakeup re-check: automatically checks for pending updates when the page becomes visible again
- Added exponential backoff retry strategy for update detection, up to 4 retries over ~3.5 minutes
- Added HTTP cache control mechanism to prevent CDN from serving stale data
- Added update dialog transition animation for improved user experience

## Bug Fixes
- Fixed missing 30-second retry mechanism after update detection polling failure
- Improved error handling and backoff mechanism in system status component

## Improvements
- Reduced update detection polling interval from 24 hours to 2 hours
- Optimized system status component styles to use theme variables for dark mode adaptation
- Completed update detection mechanism documentation and design specifications

---

# v0.7.0 Release Notes (2026-06-14)

## New Features
- Added local usage statistics, supporting tool usage duration and frequency tracking
- Added dynamic height adaptation for resource monitor table, improving data browsing experience
- Added CHANGELOG.md copy functionality in plugin build scripts, ensuring plugin packages include update logs

## Bug Fixes
- Fixed plugin management page layout and button display issues

## Improvements
- Redesigned settings page to card-based layout with new feature modules, improving visual hierarchy and interaction
- Redesigned plugin settings page UI to card-based layout, unifying design style
- Refactored plugin logs and resource monitor components, optimizing component architecture and performance
- Updated project specification document architecture, improving development standards

---

# v0.6.0 Release Notes (2026-06-13)

## New Features
- Added Afdian payment verification, supporting payment verification through the Afdian platform
- Added global payment verification intercept dialog; unverified users are automatically prompted
- Added Afdian configuration module in settings page for configuring verification parameters
- Refactored bottom status bar component architecture, splitting into independent status components
- Added SystemStatusWidget for displaying system information independently
- Added VersionHistoryPopover component for viewing version update records

## Bug Fixes
- Fixed payment verification dialog logic for correct handling of various expiration scenarios
- Fixed edge cases in plugin lifecycle management
- Fixed style and functional compatibility issues after settings page component splitting

## Improvements
- Refactored bottom status bar component architecture, improving code maintainability
- Refactored plugin management commands, optimizing plugin install and update workflows
- Updated project configuration and development tool definitions
- Updated dependency versions for improved overall stability

---

# v0.5.0 Release Notes (2026-06-10)

## New Features
- Proxy-switch plugin TUN 2.0 full rewrite, supporting IPv6, DNS forwarding, and automatic adapter management
- Added traffic chain management: create, edit, import/export traffic chains
- Added rule tags and filtering for quick proxy rule location and management
- Added node connection testing for visual connectivity status
- Added global hotkey configuration for quick proxy switching
- Added TCP request logging with pagination and auto-refresh
- Added plugin administrator elevation mechanism for plugins requiring admin privileges
- Added plugin version history for viewing and rolling back plugin versions
- Added WinTun driver management with automatic detection and installation

## Bug Fixes
- Fixed TUN adapter lifecycle management issues, improving connection stability
- Fixed DNS forwarding bypassing local DNS
- Fixed edge cases in TCP stream processing and DNS queries
- Fixed configuration file write safety with atomic writes to prevent corruption

## Improvements
- Optimized logging system performance, reducing resource usage
- Enhanced plugin communication pipeline security
- Improved form control styles in dark mode
- Updated dashboard UI with rule navigation and quick jump support
- Updated dependency versions for improved overall stability

---

# v0.4.0 Release Notes (2026-05-01)

## New Features
- Homepage tool cards now support multiple display modes with switchable views and active mode highlighting
- Notification sound feature with multiple sound styles and volume control; different events play different sound effects
- Performance settings now include system status refresh interval configuration (1-30 seconds adjustable)

---

# v0.3.7 Release Notes (2026-04-30)

## New Features
- Health monitoring now uses consecutive heartbeat stability threshold; auto-resets restart count after sustained stability
- Resource polling adds independent health status polling, updating plugin health every 3 seconds
- Production environment now captures frontend logs, improving troubleshooting efficiency

## Bug Fixes
- Fixed issue where plugins disabled by users were still auto-restarted by health monitoring
- Fixed toggle state desync when plugins were disabled due to excessive restarts
- Fixed network detection error on systems without WiFi modules
- Fixed iframe resource path resolution in PluginFrame component production mode

## Improvements
- Rust sidecar plugins now uniformly enable static-linked MSVC runtime, no longer requiring VC++ Redistributable
- Hidden sidecar console windows on Windows to prevent CMD window popups
- Plugin management page tabs redesigned as custom pill-style for more compact layout
- Watchdog now logs enhanced crash information with exit code descriptions
- Pomodoro plugin release build enables LTO and extreme size optimization

---

# v0.3.6 Release Notes (2026-04-29)

## New Features
- Improved production logging system with frontend log capture for easier troubleshooting

---

# v0.3.5 Release Notes (2026-04-29)

## New Features
- Bottom version number popup now includes version history viewing for quick access to past update content

---

# v0.3.2 Release Notes (2026-04-28)

## New Features
- Added proxy-switch plugin for system-level proxy management with multi-profile switching
- Pomodoro plugin upgraded to v2.0, supporting light/dark themes and hotkeys
- Implemented plugin auto-start mechanism for boot-time automatic plugin execution
- Added global hotkey settings with capture, display, and save support
- Added network environment detection with WiFi SSID identification
- System tray now includes "Check for Updates" menu item with version update status
- Update detection system supports automatic MSI/NSIS installer type matching
- Bottom version number shows pulse indicator when update is available
- Auto-push system notifications for plugin crash/restart/install/uninstall events
- Homepage cards support drag-and-drop reordering within categories

## Bug Fixes
- Fixed auto-check-update setting not persisting
- Fixed desync between notification popup and tray status
- Fixed rule editing and log table rendering anomalies

## Improvements
- Refactored proxy-switch main UI to thin-shell layout with clearer component structure
- Optimized sidebar toggle with manual hide and state persistence
- Removed unused @tauri-apps/plugin-sql dependency to reduce bundle size
- Extracted timeout execution logic, optimizing plugin management command implementation
- Multiple code standard and UI detail improvements
