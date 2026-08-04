# pour DevTools

Packaged builds of **pour DevTools**, the accessibility testing,
documentation and vision simulation extension from
[pour.dev](https://pour.dev).

Every release here is the exact build submitted to the browser stores, so
you can install it by hand, pin a version, or check what shipped.

## Install

- **Chrome and Edge**: [Chrome Web
  Store](https://chromewebstore.google.com/detail/cmebappepecpgihmahkfmaahmajglgch)
- **Firefox**: listing is in review, coming soon

## Downloads

Each [release](../../releases) attaches two zips:

| File | For |
| --- | --- |
| `pour-devtools-chromium-<version>.zip` | Chrome and Edge, Manifest V3 |
| `pour-devtools-firefox-<version>.zip` | Firefox 140 and later, Manifest V3 |

The store version is the one to use. Install a zip by hand only if you need
a specific version or your organisation sideloads extensions.

### Loading a zip by hand

**Chrome or Edge**: unzip it, open `chrome://extensions`, turn on Developer
mode, then "Load unpacked" and pick the unzipped folder.

**Firefox**: open `about:debugging#/runtime/this-firefox`, then "Load
Temporary Add-on" and pick the zip. Temporary add-ons are removed when
Firefox restarts.

## What it does

Runs a WCAG 2.2 audit of the current page from the toolbar popup or a
DevTools panel, showing every failing element with its WCAG criterion, a CSS
path, and the evidence behind the verdict. Criteria automation cannot judge
are listed for manual review instead of being silently skipped. It also
simulates vision and sensory conditions so you can experience a page the way
others do.

Audits run entirely in your browser. The extension makes no network requests
of its own: nothing is uploaded, and there is no analytics or tracking.
Preferences live in browser storage, and per-tab results are cleared when the
tab or the browser session ends.

## Something not working?

If an audit cannot reach a page, the panel explains why and offers a
"Report a bug" button that assembles a diagnostic report. Copy it and email
it to <info@pour.dev>, or open an issue here and paste it in.

The commonest cause is a tab that was already open when the extension was
installed or updated. Reload the page and run the audit again.

## Source

The audit engine is open source and MIT licensed:
[pourdev/pour-engine](https://github.com/pourdev/pour-engine), published to
npm as [`pour-engine`](https://www.npmjs.com/package/pour-engine). The
extension around it is not open source; these builds are published so you
can install and inspect exactly what the stores ship.

Copyright © 2026 David Yarham. All rights reserved.
