# Fluid Size

A single-purpose tool that generates fluid CSS `clamp()` values — for typography or spacing that scales smoothly between two viewports, instead of jumping at breakpoints.

Live at [fluid.hey5.studio](https://fluid.hey5.studio).

## What it does

You give it a size at a small viewport and a size at a large viewport (plus the two breakpoints), and it outputs a single `clamp(min, preferred, max)` value that interpolates between them — the standard fluid-typography technique, without doing the slope/intersect math by hand.

- **Live preview** — drag the viewport slider (or type an exact width) to see the result rendered at any size, as text or as a boxed element
- **Arithmetic in every field** — type `18*1.5` or `1440-80` directly instead of pre-computing it
- **`rem` or `px` output**
- **Shareable state** — every setting is written to the URL, so a configured link reproduces the exact same clamp
- **Accessibility check** — flags it when max < 2× min for text, since that can prevent 200% browser zoom (WCAG 1.4.4)

### Shortcuts

| Key | Action |
|---|---|
| `Cmd/Ctrl` + `C` | Copy the clamp() value |
| `Esc` | Reset |

## How it's built

Vanilla HTML/CSS/JS, no framework or build step — same setup as [Name a Color](https://colors.hey5.studio) and [Font Convert](https://fonts.hey5.studio). `base.css` is the shared design-token stylesheet reused across those tools; `style.css` holds this app's own layout. All state and clamp math live in `script.js`.

```
site/        the deployed app — index.html, 404.html, script.js, style.css,
             base.css, icons, manifest, and Cloudflare's _headers
standalone/  fluid-size-preview.html — a separate, fully self-contained copy
             of the whole app (CSS and icons inlined), not part of the
             deployed site, kept for sharing/embedding as a single file
```

`wrangler.jsonc` points Cloudflare's asset root at `site/`.

## Credits

Made with ♥ by Alex Ghit — alex@hey5.studio
