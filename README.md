# Fluid Size

A single-purpose tool that generates fluid CSS `clamp()` values — for typography or spacing that scales smoothly between two viewports.

Live at [fluid.hey5.studio](https://fluid.hey5.studio).

Vanilla HTML/CSS/JS, no framework or build step — same setup as [Name a Color](https://colors.hey5.studio) and [Font Convert](https://fonts.hey5.studio). Fonts (Geist + Geist Mono) are self-hosted in `/fonts`.

## Features

- Live preview (text or element) that scales between your min/max sizes
- Arithmetic in every field (e.g. `18*1.5`, `1440-80`)
- `rem` or `px` output
- Shareable URL state — settings are saved to the address bar
- Accessibility hint when max < 2× min (WCAG 1.4.4)

### Shortcuts

| Key | Action |
|---|---|
| `Cmd/Ctrl` + `C` | Copy the clamp() value |
| `Esc` | Reset |

## Files

| File | Purpose |
|---|---|
| `index.html`, `style.css`, `script.js` | The app |
| `fonts/` | Self-hosted Geist woff2 |
| `icons/` + `site.webmanifest` | Favicon, Apple touch icon, PWA icons |
| `_headers` | Cloudflare cache rules |
| `404.html` | Fallback page (copy of index) |

## Deploy

Static site, no build step. Deployed on Cloudflare Pages.

## Credits

Made with ♥ by Alex Ghit — alex@hey5.studio
