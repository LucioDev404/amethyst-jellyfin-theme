# Amethyst — a purple & violet theme for Jellyfin

An **Apple TV / Netflix inspired** purple-violet skin for Jellyfin.

**Self-contained**: the design base is
**[ElegantFin](https://github.com/lscambo13/ElegantFin)** (© lscambo13,
GPL-2.0), **embedded** into `theme.css` — the only external stylesheet
loaded is the **[Intro-Skipper button CSS](https://github.com/intro-skipper/intro-skipper-css)**.

Amethyst re-maps every color variable of the base to a **purple / violet
palette** and curates all the small details: card progress bars, mini play
buttons, watched flags, OSD icons and more.

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

## What Amethyst changes on top of the base

1. **Purple/violet palette** — all ElegantFin variables plus Jellyfin 12's
   `--jf-palette-*` variables (MUI navbar, dialogs, dashboard)
2. **Curated details, all in theme color:**
   - card **progress bars** (watch progress + player seek bar)
   - **play buttons** on cards (hover FAB, mobile overlay button, list items)
   - **watched flag** (green ✔ → violet), unseen-episode counts,
     sync/media-source badges, "video version" flag
   - **player OSD icons** (violet, white on hover), recording indicator
   - the **Skip Intro** button adapts automatically (violet progress bar)
3. **Centered navbar (desktop)** — on Jellyfin 12's modern MUI layout the
   server name stays on the left and the nav options are horizontally centered
   as pills; the active view gets a violet pill
4. **Library tiles without labels** — "My Media" tiles show artwork only
5. **Detail-page buttons** — extra spacing; on phones they spread across the
   full width, on tablets they stack vertically; never overflow the screen

> Note: the **Inter webfont** import that ships with ElegantFin was removed
> (single-import policy) — text uses the system sans-serif instead.

## Publishing your repo

```bash
cd amethyst-jellyfin-theme
git remote add origin git@github.com:<YOUR-USER>/amethyst-jellyfin-theme.git
git push -u origin main
```

## Customization

All colors live in the single `:root[data-theme]:root, html:root` block in the
**AMETHYST OVERRIDES** section at the bottom of [`theme.css`](theme.css) —
edit the hex values there and reload. Do not edit the embedded base theme
section.

## Credits & License

- Base theme: [ElegantFin](https://github.com/lscambo13/ElegantFin) — © lscambo13, **GPL-2.0** (embedded)
- Skip button: [intro-skipper-css](https://github.com/intro-skipper/intro-skipper-css) (loaded via CDN)
- Amethyst overrides: **GPL-2.0** — see [LICENSE](LICENSE)
