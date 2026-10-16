# Amethyst — a purple & violet theme for Jellyfin

An **Apple TV / Netflix inspired** purple-violet skin for Jellyfin, built as a
lightweight overlay on top of two excellent base stylesheets:

- **[ElegantFin](https://github.com/lscambo13/ElegantFin)** by lscambo13 — glass surfaces, cards, OSD, animations
- **[Intro-Skipper button CSS](https://github.com/intro-skipper/intro-skipper-css)** — styled Skip Intro button

Amethyst re-maps every color variable of both to a **purple / violet palette**
and adds a few structural fixes (centered navbar on Jellyfin 12+, label-less
library tiles, compact responsive detail-page buttons).

## Palette

| Role | Color |
|---|---|
| Background (deepest) | `#0b0714` |
| Surface | `#191026` |
| Accent (violet) | `#8b5cf6` |
| Accent hover | `#a78bfa` |
| Text | `#e9e4ff` |
| Dim text | `#a99cc9` |

## Requirements

- Jellyfin **10.11+** (tested on 12.x) — web client + mobile apps
- Client theme set to **Dark**

## Installation

### Option A — via CDN (recommended, auto-updates)

1. Push this repo to GitHub (see below)
2. Dashboard → **Branding** → **Custom CSS** → paste this single line:

```css
@import url("https://cdn.jsdelivr.net/gh/<YOUR-USER>/amethyst-jellyfin-theme@main/theme.css");
```

(replace `<YOUR-USER>` with your GitHub username — jsDelivr serves any public
repo automatically, no configuration needed)

3. Save, then hard-refresh the client (`Ctrl+Shift+R`)

### Option B — paste everything

Copy the whole content of [`theme.css`](theme.css) into
Dashboard → **Branding** → **Custom CSS** and save.

## What Amethyst changes on top of ElegantFin

1. **Purple/violet palette** — all ElegantFin variables plus Jellyfin 12's
   `--jf-palette-*` variables (MUI navbar, dialogs, dashboard)
2. **Centered navbar (desktop)** — on Jellyfin 12's modern MUI layout the
   server name stays on the left and the nav options are horizontally centered
   as pills; the active view gets a violet pill
3. **Library tiles without labels** — "My Media" tiles show artwork only
4. **Detail-page buttons** — extra spacing; on phones they spread across the
   full width, on tablets they stack vertically; never overflow the screen
5. The **Skip Intro button** adapts automatically (violet progress bar)

## Publishing your repo

```bash
cd amethyst-jellyfin-theme
git remote add origin git@github.com:<YOUR-USER>/amethyst-jellyfin-theme.git
git push -u origin main
```

## Customization

All colors live in the single `:root[data-theme]:root, html:root` block at the
top of [`theme.css`](theme.css) — edit the hex values there and reload.

## Credits & License

- Base theme: [ElegantFin](https://github.com/lscambo13/ElegantFin) — © lscambo13, **GPL-2.0**
- Skip button: [intro-skipper-css](https://github.com/intro-skipper/intro-skipper-css)
- Amethyst overrides: **GPL-2.0** — see [LICENSE](LICENSE)
