---
title: Privacy Policy
version: 1.5.0
updated: 2026-07-20
language: en
---

# Privacy Policy

**Last Updated:** 2026-07-20  
**Effective Date:** 2026-07-20

> **v1.5.0 changelog:** Enriched data fields across all levels — L0 adds CPU architecture and session duration; L1 adds plugin names, item IDs, and update check events; L2 adds sidebar toggle and theme change events.
>
> **v1.4.0 changelog:** All data collection levels (including L0 Core) are now fully opt-in. Removed forced/mandatory language for L0. No data is collected until the user explicitly enables cloud analytics in Settings.
>
> **v1.3.0 changelog:** Documented pageview session initialization and fixed-value metadata fields (url/title/referrer/hostname) transmitted with every analytics request.
>
> **v1.2.0 changelog:** Added screen resolution to L0 data collection (device analytics).

This Privacy Policy describes how My Desktop Tools ("the Application", "we") collects, uses, and protects your data.

## Data Collection Levels

We implement a three-tier data collection model:

### Level 0 — Core Runtime Data (Optional, Opt-in)

When enabled, the following data points are collected:

- Application start/exit events (including session duration in seconds)
- **Session initialization event** (a "pageview" sent once on startup to establish a visitor session in the analytics dashboard; enables aggregate visitor counts, country distribution, and referrer statistics)
- Application version number
- Operating system type (Windows/macOS/Linux)
- CPU architecture (e.g., x86_64, aarch64)
- Interface language (e.g., zh-CN, en-US)
- Anonymous device identifier (randomly generated UUID v4, not derived from hardware fingerprints)
- Screen resolution (e.g., 1920x1080, for device analytics only)

In addition, every analytics request carries the following **fixed metadata** (constant values shared by all users, containing no personal or device-specific information):

- `url`: A virtual route identifier (e.g., `app://main`, `app://plugin/pomodoro`)
- `title`: The constant application name "My Desktop Tools"
- `hostname`: The constant pseudo-hostname `app.my-desktop-tools.local`
- `referrer`: The constant project homepage URL (the open-source repository link)

These fixed values are used solely for the analytics dashboard's routing/context display and do not vary per user.

**Legal Basis:** Consent — opt-in only, disabled by default. The user can enable this in Settings → Privacy → Cloud Analytics.

> **Note:** The anonymous device ID is generated once using SHA-256(timestamp + process ID), persisted locally, and used solely for session grouping in the analytics dashboard. It cannot be reversed to identify your hardware or identity.

### Level 1 — Aggregate Statistics (Optional, Opt-in)

When enabled, the following aggregated data is collected:

- Plugin start/stop events (plugin ID, plugin name, duration in seconds)
- Quick launcher click events (item ID, item type)
- Update check events (source: auto, attempt number)

All data is aggregated and contains no personal identifiers.

**Legal Basis:** Consent — opt-in only, disabled by default.

### Level 2 — Detailed Behavior (Optional, Opt-in)

When enabled, the following behavioral data is collected:

- Tab switches (route path transitions)
- Page dwell time (duration per route)
- Sidebar toggle events (visibility state)
- Theme change events (dark/light)

Requires Level 1 to be enabled first.

**Legal Basis:** Consent — opt-in only, disabled by default.

## What We Do NOT Collect

We explicitly do **not** collect:

- Your name, email, phone number, or any personally identifiable information (PII)
- File contents or file paths from your system
- Clipboard contents
- Browser history or credentials
- Hardware serial numbers

## IP Address & Network Data

The Application **does not actively collect, transmit, or store** your IP address in its analytics payload. No IP field is included in any data sent to the analytics server.

However, as inherent to all HTTPS communication, the self-hosted analytics server (Umami) receives your source IP address at the network level. This is standard HTTP behavior and cannot be avoided in any client-server architecture.

**How your IP is used by the server:**

- Aggregate geographic statistics (country/region level only, visible as "Visitors by Country" in the dashboard)
- Bot detection and spam prevention (via the `isbot` library)
- Session deduplication (same IP + same browser = same visitor session)

**How your IP is protected:**

- Raw IP addresses are **not** displayed in the analytics dashboard or stored as a personal identifier
- IP is **not** linked to your anonymous device ID in any queryable form
- IP is **not** shared with any third-party service
- IP is **not** used for individual user tracking, profiling, or cross-site identification
- Server-side access logs (if any) are retained for no more than 7 days for security auditing purposes only

## Data Storage

### Local Storage

Local usage statistics (runtime duration, launch counts) are stored in a local SQLite database at:

- Windows: `%APPDATA%/my-desktop-tools/stats/stats.db`

This data never leaves your device.

### Cloud Storage

When cloud analytics is enabled, data is sent to a developer self-hosted Umami analytics instance via HTTPS. No third-party analytics services (Google Analytics, Mixpanel, etc.) are used.

**Data Retention:** Cloud analytics data is retained for 90 days, then automatically aggregated and purged.

## Your Rights

- **Access:** You can view what data types are collected (see Data Collection Levels above)
- **Deletion:** You can clear all uploaded cloud analytics data at any time via Settings → Privacy → "Delete My Data"
- **Revocation:** You can disable cloud analytics at any time via Settings → Privacy
- **Opt-out:** All optional data collection is opt-in (off by default). No action needed to stay fully offline

## Security

- All network traffic uses HTTPS encryption
- Analytics data contains no personal identifiers that could be traced back to you
- Anonymous device IDs are randomly generated UUIDs, not derived from hardware fingerprints
- The analytics server is self-hosted and managed by the developer

## Responsible Party

**Developer:** li_TL  
**Email:** [3327335699@qq.com](mailto:3327335699@qq.com)

The developer (li_TL) is the sole responsible party for data collection, storage, and processing as described in this Privacy Policy.

## Changes to This Policy

We may update this Privacy Policy from time to time. Changes will be posted in the Application and on the project repository.

## Contact

For privacy-related questions, please contact: [3327335699@qq.com](mailto:3327335699@qq.com)

<!--
  ============================================================
  Legal Reference (Internal Compliance Tracking — Not User-Visible)
  ============================================================
  Privacy Policy References:
    - PIPL: 个人信息保护法 (Personal Information Protection Law of the PRC, 2021)
    - DSL:  数据安全法 (Data Security Law of the PRC, 2021)
    - CSL:  网络安全法 (Cybersecurity Law of the PRC, 2017)
    - Civil Code of the PRC: 民法典 (Privacy & Personal Information chapter, 2021)
    - GDPR: General Data Protection Regulation (EU, for international users)

  Responsible Party: li_TL (3327335699@qq.com)
  ============================================================
-->
