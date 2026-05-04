# Changelog

This file mirrors selected private pull requests as public release summaries. It is safe to share because it contains no source code or patch diffs.

## 2026-05-04

### PR #52 - Deploy events RSS feed

- Summary: Updated the deployment path so the generated RSS feed is included in the public static artifact set and checked during deploy smoke tests.
- Public production links:
  - https://clawexplorer.ai/feed.xml
  - https://clawexplorer.ai/
- Test results:
  - `npm run check`: passed before merge.
  - Deploy smoke test includes `/feed.xml`: passed.
- Deploy result:
  - Main deploy run ID: `25303942144`
  - Status: `success`
  - Completed: 2026-05-04
- Screenshot:
  - [RSS feed response](assets/screenshots/rss-feed.png)

### PR #51 - Add events RSS feed

- Summary: Added a public RSS 2.0 feed for upcoming events, exposed feed discovery in the homepage head, and added a visible homepage footer link to the feed.
- Public production links:
  - https://clawexplorer.ai/feed.xml
  - https://clawexplorer.ai/
- Test results:
  - `npm run check`: passed before merge.
  - RSS generator smoke test: passed.
  - Local artifact check confirmed 46 RSS items, Atom self link, homepage discovery link, and footer link.
- Deploy result:
  - Main deploy run ID: `25303859529`
  - Status: `success`
  - Note: PR #52 completed the deployment allowlist change required for `/feed.xml` to be publicly reachable.
- Screenshot:
  - [RSS feed response](assets/screenshots/rss-feed.png)

### PR #50 - Bust app cache for ZIP nearest default

- Summary: Updated the homepage JavaScript cache key so production browsers load the ZIP search behavior shipped in PR #49.
- Public production link:
  - https://clawexplorer.ai/
- Test results:
  - `npm run check`: passed before merge.
  - Live HTML verification confirmed the updated script cache key.
- Deploy result:
  - Main deploy run ID: `25303113011`
  - Status: `success`

### PR #49 - Default ZIP searches to nearest sort

- Summary: Improved default ZIP-code searches so a 5-digit ZIP entered from the default sort switches to nearest-event behavior instead of showing zero results when no same-city records exist.
- Public production link:
  - https://clawexplorer.ai/
- Test results:
  - `npm run check`: passed before merge.
  - Browser verification confirmed ZIP `45219` returns mapped nearby events from the default search state.
- Deploy result:
  - Main deploy run ID: `25303056653`
  - Status: `success`
- Screenshot:
  - [Homepage events directory](assets/screenshots/homepage.png)

### PR #48 - Add nearest ZIP sort

- Summary: Added a "Nearest first" sort mode for ZIP searches and sorted mapped events by distance from the resolved ZIP location.
- Public production link:
  - https://clawexplorer.ai/
- Test results:
  - `npm run check`: passed before merge.
  - Browser verification covered ZIP queries `10001` and `94086`, exact ZIP prioritization, and normal text search behavior.
- Deploy result:
  - Main deploy run ID: `25302720438`
  - Status: `success`

### PR #47 - Allow ZIP lookup in CSP

- Summary: Updated the production Content Security Policy so the ZIP lookup endpoint can be called by the browser.
- Public production link:
  - https://clawexplorer.ai/
- Test results:
  - `npm run check`: passed before merge.
  - Production CSP behavior was verified before and after the change.
- Deploy result:
  - Main deploy run ID: `25302487730`
  - Status: `success`

### PR #46 - Add ZIP-aware event search

- Summary: Added ZIP-aware search to the homepage search box. Exact ZIP/address matches rank first, with city/state fallback for records that only have city-level location data.
- Public production link:
  - https://clawexplorer.ai/
- Test results:
  - `npm run check`: passed before merge.
  - Browser verification covered exact ZIP, city/state fallback, normal text search, unknown ZIP, and non-US 5-digit postal behavior.
- Deploy result:
  - Main deploy run ID: `25302412682`
  - Status: `success`
