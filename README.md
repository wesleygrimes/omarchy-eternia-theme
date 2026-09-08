# Eternia for Omarchy

A saturated, retro-futuristic [Omarchy](https://omarchy.org/) theme inspired by
the heroic science fantasy and restored animation-cel color of early-1980s
Eternia.

Deep Grayskull violet forms the working surfaces. Power Sword cyan, royal
violet, hot coral, Battle Cat green, and heroic gold carry focus, syntax,
status, and active-window states. The active border sweeps from cyan through
violet to gold.

![Eternia desktop with Eternos sunset](preview.png)

## Install

In the Omarchy menu (`Super + Space`), choose **Install > Style > Theme** and
paste:

```text
https://github.com/wesleygrimes/omarchy-eternia-theme.git
```

Or from a terminal:

```bash
omarchy theme install https://github.com/wesleygrimes/omarchy-eternia-theme.git
```

Omarchy derives the name `eternia` from the repository and applies the theme
after install.

```bash
omarchy theme set Eternia
omarchy theme bg next
omarchy theme update
```

To remove it, switch away first, then uninstall:

```bash
omarchy theme set tokyo-night
omarchy theme remove eternia
```

Or use **Remove > Theme** in the Omarchy menu.

Theme install does not run extra scripts. The optional Skeletor crash sounds
are a separate step below.

## What's included

- Semantic + ANSI palette in `colors.toml`. Omarchy generates matching configs
  for terminals, Neovim, Chromium, Helix, Obsidian, Hyprland, the Omarchy
  shell, and other apps supported by the installed release
- Cyan → violet → gold active-window border shared by Hyprland and shell
  surfaces
- Handcrafted transparent btop theme and Grayskull lock-screen panel
- Seven widescreen backgrounds and a 16:9 theme-switcher preview
- Yaru Magenta icon preference
- Optional Skeletor crash-sound easter egg

This repository does not ship auto-executed Lua, terminal command
configuration, personal Hyprland settings, or editor-extension installers.

## Background gallery

Click any image to open the full-resolution wallpaper.

| Castle Grayskull | For Eternia | By the Power | Snake Mountain |
|:---:|:---:|:---:|:---:|
| [![Moonlit Castle Grayskull](backgrounds/1-castle-grayskull.png)](backgrounds/1-castle-grayskull.png) | [![He-Man and Battle Cat facing Grayskull](backgrounds/2-for-eternia.png)](backgrounds/2-for-eternia.png) | [![Transformation inside Castle Grayskull](backgrounds/3-by-the-power.png)](backgrounds/3-by-the-power.png) | [![Retro-futuristic Snake Mountain](backgrounds/4-snake-mountain.png)](backgrounds/4-snake-mountain.png) |
| **Eternos & Point Dread** | **Crystal Castle** | **Skeletor's Throne** |  |
| [![Royal Palace of Eternos and Point Dread](backgrounds/5-eternos-point-dread.png)](backgrounds/5-eternos-point-dread.png) | [![She-Ra and Swift Wind at Crystal Castle](backgrounds/6-crystal-castle.png)](backgrounds/6-crystal-castle.png) | [![Skeletor in the Snake Mountain throne room](backgrounds/7-skeletor-throne.png)](backgrounds/7-skeletor-throne.png) |  |

## Optional Skeletor crash sounds

Four short clips play when a native application dumps core. The watcher only
runs while Eternia is active, picks a random clip, rate-limits to once every
15 seconds, and ignores old crashes at login.

Omarchy does not execute code from a Git-installed theme. Enable this
explicitly after installing Eternia:

```bash
~/.config/omarchy/themes/eternia/install-easter-eggs
systemctl --user status eternia-crash-watcher.service
~/.config/omarchy/themes/eternia/bin/eternia-crash-watcher --test
~/.config/omarchy/themes/eternia/uninstall-easter-eggs
```

Needs `systemd`, `journalctl`, `jq`, and `mpv` (standard on Omarchy). The
installer links a user service from the theme directory. It does not use
`sudo`.

## Compatibility

Designed for current Omarchy releases using semantic `colors.toml`. No
absolute paths or machine-specific settings are included. Omarchy's normal
fallbacks apply if Yaru Magenta icons are unavailable.

Window opacity, blur, gaps, and corner radius stay with each user's Hyprland
config.

## Artwork and attribution

The included backgrounds are AI-generated original fan artwork created for
this theme. They contain no copied logos or text.

This is an unofficial, non-commercial fan project. *He-Man and the Masters of
the Universe*, Eternia, Castle Grayskull, Snake Mountain, and related names
and characters are trademarks and intellectual property of their respective
owners. This project is not affiliated with or endorsed by Mattel.

The optional Skeletor audio clips were downloaded from the
[Voicy Skeletor soundboard](https://www.voicy.network/official-soundboards/series/skeletor).
They remain the property of their respective rights holders and are not
covered by the MIT license.

## License

Original theme configuration and artwork are MIT. See [LICENSE](LICENSE).
No license or ownership claim is made over third-party names, characters, or
settings.
