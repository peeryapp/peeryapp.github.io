# Peery website

Source for [peeryapp.com](https://peeryapp.com), the homepage for Peery: private, peer-to-peer communication, file sharing and backup. No accounts, no cloud, no middleman.

A static site with no build step and no dependencies.

## Structure

```
index.html   Single page: markup, CSS and JS in one file
fonts/       Self-hosted woff2 files (DM Serif Display, Inter)
```

## Run locally

Serve the folder with any static server:

```sh
python3 -m http.server 8000
```

Then open <http://localhost:8000>.

## Deploy

Upload the folder to any static host. Serve `/fonts/` with long-lived caching:

```
Cache-Control: public, max-age=31536000, immutable
```

## Notes

- **No trackers.** The page sets no cookies and makes no third-party requests, and the footer says so. Keep it that way: self-host fonts and avoid analytics or embed scripts.
- **Logo.** The animated mark is rendered in JS by `twinE()` and `renderLogo()` in `index.html`, ported from the app's `TwinEMark.tsx` and `Logo.tsx`. Update both when the logo changes.
- **Motion.** Animations are paused off-screen and respect `prefers-reduced-motion`.
- **Social links** live in the footer. Remove the `hidden` attribute on a link to show it.

## Fonts

DM Serif Display and Inter are licensed under the SIL Open Font License 1.1 and come from [Fontsource](https://fontsource.org).
