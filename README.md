# Trufflepig — Archived Flash Website

The original Trufflepig website (circa 2005), preserved as a static site using
the [Ruffle](https://ruffle.rs) Flash emulator.

**Live site:** https://jackdancy.github.io/2005-website/

## About

This is a single self-contained Adobe Flash file (`trufflepig.swf`) — all
assets, photos, text, and navigation are baked into the SWF. The site embeds it
via a self-hosted copy of the Ruffle JavaScript player so it runs in any modern
browser without Flash installed.

- SWF stage size: 1200 x 800 (3:2)
- Flash version: 6
- Player scales to fill the browser viewport

## Running locally

```bash
npm install
npm start
```

Open **http://localhost:3000** in your browser. The SWF must be served over HTTP
(not opened as a `file://` path) for Ruffle to load it.

## Project structure

```
index.html          # Single-page site — loads Ruffle and plays the SWF
ruffle/             # Self-hosted Ruffle player (from @ruffle-rs/ruffle npm package)
trufflepig.swf      # The original Flash file
package.json        # Dev server (serve) and Ruffle dependency
```

## Deployment

The site is deployed to GitHub Pages from the `main` branch. Any push to `main`
triggers a rebuild. No build step is needed — everything is static.
