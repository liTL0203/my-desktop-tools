---
title: Third-Party SDK Notices
version: 1.0.0
updated: 2026-08-15
language: en
---

# Third-Party SDK Notices

This document lists the third-party SDKs redistributed with **My Desktop Tools**, together with their license terms.

## Everything SDK (Everything64.dll)

- **Vendor**: voidtools (<https://www.voidtools.com/>)
- **SDK page**: <https://www.voidtools.com/support/everything/sdk/>
- **Component**: `Everything64.dll` (IPC client library, redistributed unmodified)
- **License**: voidtools License (<https://www.voidtools.com/License.txt>) — an MIT-style
  license that permits commercial use and redistribution (including binary redistribution),
  provided that the copyright notice below is preserved.

### Copyright Notice

```text
Everything software license agreement

voidtools (C) 2026

This software and associated documentation files (the "Software") may only be used in
original unaltered form.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED,
INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A
PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT
HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION
OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE
SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
```

> The authoritative license text is the one published at
> <https://www.voidtools.com/License.txt>. If this copy differs from the online version,
> the online version prevails.

### Notes

- The Everything **application itself is NOT redistributed** with this product. Users may
  download and install Everything from the official website if they wish to enable the
  "Everything full-disk search" integration.
- This product uses the SDK only to send search queries to a locally running Everything
  process via its IPC interface. No user data is sent to voidtools or any third party.
