# ShipLean design assets

Reference material for anyone making something that should look like ShipLean: the website, a social post, a slide or a new screen. ShipLean shares its house style with Codex (the same palette, type and density) but has its own mark and brand gradient, so the two never get mixed up.

## What's here

| Path | What it is |
|---|---|
| `brand/shiplean-mark-light.svg` | The mark on light backgrounds: teal-to-blue gradient square with a white boat: three backlog rows stacked as a sail, widening down to the hull. |
| `brand/shiplean-mark-dark.svg` | The mark on dark backgrounds: mint-to-cyan gradient square, navy boat. |
| `brand/shiplean-logo-on-light.svg`, `brand/shiplean-logo-on-dark.svg` | The mark with the **ShipLean** wordmark. The wordmark is live SVG text set in Inter 700, so it needs Inter installed; convert it to outlines before sending it to print. |
| `brand/shiplean-avatar-mark.png` | 512×512 PNG of the light mark, for the GitHub org avatar. |
| `brand/favicon.svg` | One file that switches between the light and dark mark with the visitor's theme. |
| `tokens/tokens.css`, `tokens/tokens.json` | The ShipLean design tokens, the same files as the app's `design/` folder: colour, type, spacing, density, work item types, state categories and charts, light and dark. |
| `screenshots/*.png` | Every reference screen at 2880×1800 (1440×900 at 2x), in light and dark. |
| `social/og-card.html`, `social/og-image.png` | The 1200×630 link-preview card and its source. |

## Palette: Nord Frost, deepened

| Token | Light | Dark | Use |
|---|---|---|---|
| `--color-bg` | `#e8eef7` | `#171e2d` | Page background |
| `--color-surface` | `#f7f9fd` | `#1f2839` | Cards, bars, inputs |
| `--color-surface-2` | `#dfe7f3` | `#29344a` | Table headers, hover, tracks |
| `--color-border` | `#cdd9ea` | `#334058` | Borders and dividers |
| `--color-text` | `#1c2638` | `#eef2f8` | Body text |
| `--color-muted` | `#52627c` | `#a0aec6` | Secondary text and icons |
| `--color-accent` | `#2563c9` | `#5cc8f0` | Primary actions, focus, selection |
| `--color-accent-soft` | `#dae6fb` | `#163a57` | Selected and hover backgrounds |
| `--color-ok` | `#3f8a3a` | `#9fdc8a` | Completed, free capacity |
| `--color-warn` | `#b7701b` | `#f4cf72` | Resolved, warnings |
| `--color-danger` | `#c2353b` | `#f08a8f` | Over capacity, errors |

The landing page adds one brand gradient for the mark and highlighted headline words: `#16a089 → #2563c9` (teal to blue) in light and `#3dd6b5 → #5cc8f0` (mint to cyan) in dark. Codex uses blue to sky blue, so keep ShipLean on the teal end.

## Type

- **Inter** for everything, at weights 400, 500, 600 and 700 (700 for marketing headlines only; the app stays at 600 and below).
- The app is compact, with 13px body text. The landing page uses a larger scale: 16px body, a 40–74px hero headline with -0.035em tracking, and 30–46px section headings.

## Rules of thumb

- **Use both themes.** Every visual needs a light and a dark version. On the website, the matching screenshot is chosen by `prefers-color-scheme` or the theme toggle.
- **Accent means action.** Use the accent for buttons, links, focus and selection, not for decoration. Surfaces stay neutral.
- **Work item type colours are only for type icons**, never for UI state.
- **Show the real product.** Use the screenshots in `screenshots/` rather than mock-ups, so what people see matches what they get.
- **Leave clear space around the mark** of at least half its width. Don't recolour, stretch or rotate it.

## Screenshots

The screenshots come from the reference screens in the app repo (`design/screens/*.html`), captured at 1440×900 at 2x by its `design/screenshots.sh`. Variants such as `backlog-tree`, `features-epics`, `import-key`, `import-run`, `work-item-bug` and the `taskboard-*` files are one screen in another state. The website uses only the ones in `site/shots/`.

The website uses 2000px-wide WebP copies of these in `site/shots/` (quality 82). To make one from a PNG:

```sh
cwebp -q 82 -resize 2000 0 screenshots/planning-dark.png -o ../site/shots/planning-dark.webp
```

To re-render the social card, open `social/og-card.html` in headless Chrome at 1200×630 and save it as `social/og-image.png`, then copy it to `site/og-image.png`.
