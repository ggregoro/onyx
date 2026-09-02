# Pure Black Color — an Omarchy theme

A stark **pure-black** desktop theme for [Omarchy](https://omarchy.org/):
`#000000` background, white foreground, greyscale UI accents — but the
**8 ANSI terminal colours (+ brights) are real colours**, not shades of
grey, so terminal text (syntax highlighting, `ls`, `git`, TUIs) reads in
full colour on the black.

## Why

Dark terminal themes tend to fail readability in one of two ways, and
both come down to too little hue separation in the output:

- **Monochrome / greyscale** (Omarchy's stock `vantablack`, `ash`, and
  friends): terminal text is rendered in shades of grey, so `ls`, `git`,
  diffs, and syntax highlighting all collapse to near-uniform low
  contrast.
- **Single-accent-hue** (a theme keyed entirely on one neon colour):
  there's colour, but every ANSI slot leans the same direction, so
  tokens still don't pull apart — and at low luminance on near-black it
  reads muddy rather than "neon".

Pure Black Color keeps the stark `#000000` background but gives the 8
ANSI slots genuinely distinct hues (red / green / yellow / blue /
magenta / cyan / orange / brown), each tuned to hold its own luminance
on pure black. Colour is doing structural work — separating meaning —
not just setting a mood.

- `background = #000000`, `foreground = #ffffff`
- ANSI palette: a Tokyo-Night-ish set tuned to read well on pure black
  (`red #f7768e`, `green #9ece6a`, `yellow #e0af68`, `blue #7aa2f7`,
  `magenta #bb9af7`, `cyan #7dcfff`, `orange #ff9e64`, `brown #c0a36e`)
- Folder icons: `Yaru-blue` (standard blue GNOME/Ubuntu-style folders)
- 5 bundled backgrounds in `backgrounds/`

The pure-black background/foreground started from Omarchy's stock
`vantablack` theme; everything else here is its own.

## Install

```bash
omarchy theme install https://github.com/ggregoro/omarchy-pure-black-color
omarchy theme set "Pure Black Color"
```

Or clone it manually:

```bash
git clone https://github.com/ggregoro/omarchy-pure-black-color \
  ~/.config/omarchy/themes/pure-black-color
omarchy theme set pure-black-color
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
`omarchy theme set pure-black-color`. Everything else — Hyprland border
colours, waybar, btop, Neovim, etc. — regenerates from `colors.toml`.
To tint borders/waybar too, change `accent` from grey `#8d8d8d` to one
of the ANSI colours.

## Revert

`omarchy theme set vantablack` returns to Omarchy's stock pure-black theme.

## Backgrounds & licensing

The bundled wallpapers are a personal selection, including a public-domain
Edward Hopper painting (*Nighthawks*, 1942) and stock desktop images.
Swap `backgrounds/` for your own if you prefer. Theme files (`colors.toml`,
`icons.theme`, this README) are MIT-licensed — see `LICENSE`.
