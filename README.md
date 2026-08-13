# ShanuFit

Companion app for the DoctorBilalFit coaching program - meal tracking, food substitution calculator, the Level 1.0 workout program with per-set logging, and daily and weekly WhatsApp check-in reports.

All logged data stays on the device (localStorage). Nothing is uploaded anywhere, and the repository being public does not expose any of it.

## Hosting it on GitHub Pages

The app is plain static files, so Pages serves it as-is. One-time setup:

1. Merge your working branch into `main` - Pages will serve whatever is on `main`.
2. In the repository, go to **Settings** -> **Pages**.
3. Under **Build and deployment**, set **Source** to `Deploy from a branch`.
4. Choose branch `main` and folder `/ (root)`, then **Save**.
5. Wait about a minute for the first build. The site appears at:

   `https://shanuvertv.github.io/bilal-fit/`

To publish changes later, push to `main`. The site rebuilds automatically, and the app picks up the new version the next time it is opened with a connection.

## Installing it on a phone

- **iPhone/iPad** - open the Pages URL in **Safari**, tap Share, then **Add to Home Screen**.
- **Android** - open the URL in Chrome, then **Install app** from the menu.

It launches full screen with its own icon, no browser chrome.

## Offline

`sw.js` caches the app so it opens without a connection - useful mid-workout. The strategy is network-first: online, you always get the latest version; offline, the last good copy runs. Logged data lives in localStorage and is never touched by an update.

If you change the app and want to be sure phones pick it up, bump the `CACHE` name in `sw.js`.

## Files

| File | Purpose |
| --- | --- |
| `index.html` | The whole app - markup, styles, plan data and logic |
| `manifest.webmanifest` | Name, colours and icons for installing to a home screen |
| `sw.js` | Service worker for offline use |
| `icon-*.png` | Home screen and launcher icons |

## Backups

Data lives only on the device. Use **Progress -> Export data** now and then, and **Import data** to restore onto a new phone.
