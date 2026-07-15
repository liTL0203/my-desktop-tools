# Changelog

> All version release notes. Latest version first.

**[中文版](./CHANGELOG.zh-CN.md)** | **English**

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
