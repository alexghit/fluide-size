# Fluid Size

A single-purpose tool that generates fluid CSS `clamp()` values — for typography or spacing that scales smoothly between two viewports, instead of jumping at breakpoints.

Live at [fluid.hey5.studio](https://fluid.hey5.studio).

## What it does

You give it a size at a small viewport and a size at a large viewport (plus the two breakpoints), and it outputs a single `clamp(min, preferred, max)` value that interpolates between them — the standard fluid-typography technique, without doing the slope/intersect math by hand.

- **Live preview** — drag the viewport slider (or type an exact width) to see the result rendered at any size, as text or as a boxed element
- **Arithmetic in every field** — type `18*1.5` or `1440-80` directly instead of pre-computing it
- **`rem` or `px` output**
- **Accessibility check** — flags it when max < 2× min for text, since that can prevent 200% browser zoom (WCAG 1.4.4)

### Shortcuts

| Key | Action |
|---|---|
| `Cmd/Ctrl` + `C` | Copy the clamp() value |
| `Esc` | Reset |

## How it's built

Vanilla HTML/CSS/JS, no framework or build step — the whole app is one self-contained `index.html` with CSS, JS and the favicon inlined.

`wrangler.jsonc` falls back to `index.html` for any unmatched path, since there's nothing else to route to.

## Credits

Made with ♥ by Alex Ghit — <alex@hey5.studio>
