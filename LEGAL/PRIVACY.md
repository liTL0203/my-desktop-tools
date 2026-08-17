---
title: Privacy Policy
version: 1.7.0
updated: 2026-08-16
language: en
---

# Privacy Policy

**Last Updated:** 2026-08-16  
**Effective Date:** 2026-08-16

> **v1.7.0 changelog:** Further narrowed the collection surface and simplified to a **single switch** — screen resolution and CPU architecture are no longer collected; the fixed `referrer` field (formerly the project repository link) is removed from every request; the former L0 (Core) and L1 (Aggregate) switches are merged into a single "anonymous usage statistics" switch.
>
> **v1.6.0 changelog:** Narrowed the collection surface — removed the Level 2 detailed-behavior tier (tab switches, page dwell time, sidebar toggles, and theme changes are no longer collected); removed update-check events; plugin start/stop no longer reports plugin names (plugin ID only); quick launcher clicks report item IDs for plugin/app types only (file/URL types do not report item IDs, preventing file-path leakage).
>
> **v1.5.0 changelog:** Enriched data fields across all levels — L0 adds CPU architecture and session duration; L1 adds plugin names, item IDs, and update check events; L2 adds sidebar toggle and theme change events.
>
> **v1.4.0 changelog:** All data collection levels (including L0 Core) are now fully opt-in. Removed forced/mandatory language for L0. No data is collected until the user explicitly enables cloud analytics in Settings.
>
> **v1.3.0 changelog:** Documented pageview session initialization and fixed-value metadata fields (url/title/referrer/hostname) transmitted with every analytics request.
>
> **v1.2.0 changelog:** Added screen resolution to L0 data collection (device analytics).

This Privacy Policy describes how My Desktop Tools ("the Application", "we") collects, uses, and protects your data.

## Data Collection

Cloud analytics is a **single, fully optional switch (opt-in, disabled by default)**: until you explicitly enable it in "Settings → Privacy", the Application sends no analytics data to any server.

When enabled, the following **anonymous usage statistics** are collected:

- Application start / exit events (the exit event includes session duration in seconds)
- **Session initialization event** (a "pageview" sent once on startup to establish a visitor session in the analytics dashboard; enables aggregate visitor counts)
- Application version number
- Operating system type (Windows / macOS / Linux)
- Interface language (zh-CN / en-US)
- Plugin start / stop events (plugin ID only; the stop event includes duration in seconds, **no plugin names**)
- Quick launcher click events (item type only; plugin/app types include the item ID, **file/URL types do not report item IDs and no file paths are collected**)
- Anonymous device identifier (randomly generated UUID, not derived from hardware fingerprints)

In addition, every analytics request carries the following **fixed metadata** (constant values shared by all users, containing no personal or device-specific information):

- `url`: A virtual route identifier (e.g., `app://main`)
- `title`: The constant application name "My Desktop Tools"
- `hostname`: The constant pseudo-hostname `app.my-desktop-tools.local`

**Legal Basis:** Consent — opt-in only, disabled by default.

> **Anonymous device ID note:** Generated once at random (not derived from hardware fingerprints) and stored locally only; used solely for session grouping in the analytics dashboard. It cannot be reversed to identify your hardware or identity.

> **Historical tiers note:** Versions up to v1.6.0 used an L0 / L1 / L2 tiered model. The L2 detailed-behavior tier (tab switches, page dwell, sidebar, theme) was removed in v1.6.0; as of v1.7.0, L0 and L1 are merged into the single list above, and screen resolution, CPU architecture, and the referrer field are no longer collected. The corresponding tier switches in older configuration files are deprecated and have no effect.

## What We Do NOT Collect

We explicitly do **not** collect:

- Your name, email, phone number, or any personally identifiable information (PII)
- File contents or file paths from your system
- Clipboard contents
- Browser history or credentials
- Hardware serial numbers
- Hardware specs such as screen resolution or CPU model/architecture

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

- **Access:** You can view what data types are collected (see Data Collection Levels above; the Settings → Privacy page provides a transparency card covering "what is collected / where it is sent / how to manage it")
- **Deletion (local):** You can clear the local pending upload queue and turn off reporting at any time via Settings → Privacy → "Delete My Data". Note that this does **not** delete data already uploaded to the cloud (the analytics service has no per-record deletion API); uploaded data is automatically purged after the 90-day retention period
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
