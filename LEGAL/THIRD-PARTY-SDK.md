---
title: Third-Party SDK Notices
version: 1.1.0
updated: 2026-09-12
language: en
---

# Third-Party SDK Notices

This document lists the third-party SDKs redistributed with **My Desktop Tools**, together with their license terms.

## Everything SDK (Everything64.dll)

- **Vendor**: voidtools (<https://www.voidtools.com/>)
- **SDK page**: <https://www.voidtools.com/support/everything/sdk/>
- **Component**: `Everything64.dll` (IPC client library, redistributed unmodified)
- **License**: voidtools License (<https://www.voidtools.com/License.txt>) — the MIT
  license, which permits commercial use and redistribution (including binary
  redistribution), provided that the copyright and permission notice below is preserved.

### Copyright & License Notice

The text below is the current voidtools License.txt (<https://www.voidtools.com/License.txt>)
as verified in September 2026; the bundled PCRE portion carries a BSD-style license that
likewise permits redistribution:

```text
Everything

Copyright (C) 2018 David Carpenter

Permission is hereby granted, free of charge, to any person obtaining a
copy of this software and associated documentation files (the "Software"),
to deal in the Software without restriction, including without limitation
the rights to use, copy, modify, merge, publish, distribute, sublicense,
and/or sell copies of the Software, and to permit persons to whom the
Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING
FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER
DEALINGS IN THE SOFTWARE.
```

> The authoritative license text is the one published at
> <https://www.voidtools.com/License.txt>. If this copy differs from the online version,
> the online version prevails.

### Notes

- The Everything **application itself is NOT bundled or redistributed** with this
  product. Since v1.6, the settings page offers a guided in-app download: the app
  connects **directly to the official voidtools server** to fetch the installer (the
  version number and official SHA-256 checksum come from the product's version manifest
  via Gitee/GitHub, and the download URL is strictly validated against the official
  domain), then launches the **original official installer** for the user to complete
  the installation. This product does not mirror, modify, or resell the installer.
- This product uses the SDK only to send search queries to a locally running Everything
  process via its IPC interface. No user data is sent to voidtools or any third party;
  both "check for updates" and downloads are user-initiated, with no background polling.
