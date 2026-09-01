# Vantablack Color — an Omarchy theme

A fork of Omarchy's stock **`vantablack`** theme. Same stark pure-black
background and white foreground, greyscale UI accents kept — the one
change is that the **8 ANSI terminal colours (+ brights) are real
colours** instead of shades of grey, so terminal text (syntax
highlighting, `ls`, `git`, TUIs) shows in colour.

- `background = #000000`, `foreground = #ffffff` — unchanged from vantablack
- ANSI palette: a Tokyo-Night-ish set tuned to read well on pure black
  (`red #f7768e`, `green #9ece6a`, `yellow #e0af68`, `blue #7aa2f7`,
  `magenta #bb9af7`, `cyan #7dcfff`, `orange #ff9e64`, `brown #c0a36e`)
- Folder icons: `Yaru-blue` (standard blue GNOME/Ubuntu-style folders)
- 5 backgrounds in `backgrounds/`

## Install

```bash
omarchy theme install https://github.com/ggregoro/omarchy-vantablack-color
omarchy theme set "Vantablack Color"
```

Or clone it manually:

```bash
git clone git@github.com:ggregoro/omarchy-vantablack-color.git \
  ~/.config/omarchy/themes/vantablack-color
omarchy theme set vantablack-color
```

Cycle backgrounds with `Super+Ctrl+Space` or `omarchy theme bg next`.

## One extra step: terminal opacity (optional)

Omarchy strips terminal configs from an installed theme and regenerates
`foot.ini` from a template, so background transparency can't ship inside
the theme. To add it, edit `~/.config/foot/foot.ini` yourself:

```ini
[colors-dark]
alpha = 0.95
```

then `omarchy restart terminal`. Lower `alpha` = more transparent.
(Omarchy has Hyprland blur disabled by default, so this is plain
see-through, not frosted glass.)

## Tweaking

Edit `colors.toml` (or `icons.theme`), then re-run
`omarchy theme set vantablack-color`. Everything else — Hyprland border
colours, waybar, btop, Neovim, etc. — regenerates from `colors.toml`.
To tint borders/waybar too, change `accent` from grey `#8d8d8d` to one
of the ANSI colours.

## Revert

`omarchy theme set vantablack` returns to the stock theme (untouched).

---

Notes: the bundled wallpapers are personal picks (incl. a public-domain
Edward Hopper painting and stock desktop images) — swap
`backgrounds/` for your own if redistributing.
