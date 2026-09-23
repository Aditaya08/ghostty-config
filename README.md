# Ghostty Config

Personal [Ghostty](https://ghostty.org/) terminal configuration for Linux (GTK).

## Files

| File | Purpose |
|------|---------|
| `config` | Main configuration: fonts, sizing, opacity, keybindings, tabs/splits, shell integration |
| `theme.conf` | Theme declaration (`theme = "Argonaut"`), overridable by wallust |
| `wallust.conf` | Wallust-generated color template that overrides theme colors to match the active wallpaper |
| `.gitignore` | Reserved for future ignores (Ghostty keeps no cache/key files in this dir) |

## Highlights

- **Font**: `FantasqueSansM Nerd Font Mono` at 20pt (requires the [Nerd Font](https://www.nerdfonts.com/) installed)
- **Appearance**: 90% background opacity, 60px blur radius, dark window theme, bar cursor
- **Terminal**: `xterm-256color`, shell integration enabled (`cursor`, `sudo`), mouse auto-hides while typing
- **Layout**: 110x32 window, saved window state, single-instance GTK
- **Keybindings**:
  - `Ctrl+Shift+T` — new tab
  - `Ctrl+Shift+W` — close tab
  - `Ctrl+Shift+H` — new split (down)
  - `Ctrl+Shift+R` — reload config

## Theme management

The config supports changing themes without editing the main file:

- `theme.conf` holds the active theme (`Argonaut`).
- `wallust.conf` is written by [wallust](https://github.com/JaKooLit/Wallust) and derives the full 16-color palette plus UI colors (`foreground`, `background`, `cursor-color`, `selection-*`) from the current wallpaper. When present it overrides the theme colors.
- To re-enable either override, uncomment the matching `config-file` line in `config` (currently both are commented out; the `theme` line in `config` is authoritative today).

## Usage on a new machine

```sh
mkdir -p ~/.config
git clone git@github.com:Aditaya08/ghostty-config.git ~/.config/ghostty
```

Ensure the Nerd Font is installed and pick your theme/wallust entry in `config`.

## Maintenance

```sh
cd ~/.config/ghostty
git add -A && git commit -m "update config" && git push
```

Because this repo lives directly at `~/.config/ghostty`, edits apply immediately (Ghostty hot-reloads config), and the same directory versions itself.