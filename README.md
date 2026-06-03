# Trufflepig — Archived Flash Website

Static site that plays the original Trufflepig Flash website using the
[Ruffle](https://ruffle.rs) emulator.

## Quick start

```bash
npm install
npm start
```

Open **http://localhost:3000** in your browser.

## Adding the SWF

Drop your `.swf` file into the project root (next to `index.html`) and name it
**`trufflepig.swf`**. If your file has a different name, either rename it or
update the `src` attribute on the `<ruffle-embed>` tag in `index.html`.

## Project structure

```
.
├── index.html          # The page — embeds the SWF via Ruffle
├── ruffle/             # Self-hosted Ruffle player files (from npm)
├── trufflepig.swf      # ← your Flash file goes here
├── package.json
└── README.md
```

## Adjusting the player size

The player defaults to 800 × 600. If your SWF has a different stage size, edit
the `width` / `height` on the `<ruffle-embed>` tag and the matching CSS in
`#player-container`.

## Deploying to a static host

Upload the following files/folders — nothing else is needed:

- `index.html`
- `ruffle/` (entire directory)
- `trufflepig.swf`

### GitHub Pages

Push those files to a repo, go to **Settings → Pages**, and set the source to
the branch/folder containing them.

### Netlify / Cloudflare Pages

Point the site at the repo (or drag-and-drop the files above). No build command
is needed — it's all static.

### MIME type note

Most static hosts serve `.swf` as `application/x-shockwave-flash` by default.
If your host doesn't, add a `_headers` file (Netlify/Cloudflare) or equivalent:

```
/*.swf
  Content-Type: application/x-shockwave-flash
```
