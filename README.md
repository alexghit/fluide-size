# Fluid Size

A single-purpose tool that generates fluid CSS `clamp()` values — for typography or spacing that scales smoothly between two viewports.

Vanilla HTML/CSS/JS. No framework, no build step. Fonts (Geist + Geist Mono) are self-hosted in `/fonts`.

## Features

- Live preview (text or element) that scales between your min/max sizes
- Arithmetic in every field (e.g. `18*1.5`, `1440-80`)
- `rem` or `px` output
- Shareable URL state — settings are saved to the address bar
- Keyboard: `⌘/Ctrl + C` to copy, `Esc` to reset
- Accessibility hint when max < 2× min (WCAG 1.4.4)

## Run locally

Open `index.html` in a browser, or serve the folder:

```
python3 -m http.server
```

## Deploy to Cloudflare Pages (via GitHub)

1. Push this folder to a GitHub repo (files at the repo root).
2. Cloudflare dashboard -> Workers & Pages -> Create -> Pages -> Connect to Git.
3. Select the repo. Leave Build command empty and set Build output directory to `/`.
4. Deploy, then add a custom domain under the project's Custom domains tab.

No build step — Cloudflare serves the static files as-is. `_headers` sets caching, `404.html` is the fallback page.

## Files

- `index.html`, `style.css`, `script.js` — the app
- `fonts/` — self-hosted Geist woff2
- `icons/` + `site.webmanifest` — favicon, Apple touch icon, PWA icons
- `_headers` — Cloudflare cache rules
- `404.html` — fallback (copy of index)
