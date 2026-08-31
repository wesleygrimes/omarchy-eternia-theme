# Eternia for Omarchy

A saturated, retro-futuristic Omarchy theme inspired by the heroic science
fantasy and restored animation-cel color of early-1980s Eternia.

Deep Grayskull violet forms the working surfaces. Power Sword cyan, royal
violet, hot coral, Battle Cat green, and heroic gold carry focus, syntax,
status, and active-window states. The active border sweeps from cyan through
violet to gold.

## What Eternia brings

| Feature | Experience | Source |
|---|---|---|
| Semantic + ANSI palette | Grayskull violet surfaces with Power Sword cyan, royal violet, heroic gold, hot coral, and Battle Cat green | `colors.toml` |
| Active-window energy border | Cyan → violet → gold gradient shared by Hyprland and Omarchy shell surfaces | `colors.toml` |
| Eternian Command Center | Handcrafted transparent btop instrumentation with distinct Power, Life, Threat, and Operations colors | `btop.theme` |
| Grayskull lock screen | Translucent dark panel, quiet violet idle state, energized typing border, gold selection, and Horde-red failure state | `shell.lock.toml` |
| Seven illustrated worlds | Castle Grayskull, Eternos, Point Dread, Snake Mountain, Crystal Castle, and Skeletor's throne room | `backgrounds/` |
| Desktop integration | Yaru Magenta icon preference and an Eternos theme-switcher preview | `icons.theme`, `preview.png` |
| Optional villain commentary | Four rate-limited Skeletor clips when a native application dumps core | `install-easter-eggs`, `sounds/` |

From the core palette, Omarchy safely generates matching configurations for
Alacritty, Foot, Ghostty, Kitty, Hyprland, the Omarchy shell, Chromium, Neovim,
Helix, Obsidian, Claude, Pi, and other applications supported by the installed
Omarchy release. Eternia's handcrafted btop and lock-screen files override only
those two generated targets.

## Preview

![Eternia desktop with Eternos sunset](screenshots/desktop-eternos.png)

![Eternia desktop with Skeletor's throne room](screenshots/desktop-skeletor.png)

## Background gallery

Click any image to open the full-resolution wallpaper.

| Castle Grayskull | For Eternia | By the Power | Snake Mountain |
|:---:|:---:|:---:|:---:|
| [![Moonlit Castle Grayskull](backgrounds/1-castle-grayskull.png)](backgrounds/1-castle-grayskull.png) | [![He-Man and Battle Cat facing Grayskull](backgrounds/2-for-eternia.png)](backgrounds/2-for-eternia.png) | [![Transformation inside Castle Grayskull](backgrounds/3-by-the-power.png)](backgrounds/3-by-the-power.png) | [![Retro-futuristic Snake Mountain](backgrounds/4-snake-mountain.png)](backgrounds/4-snake-mountain.png) |
| **Eternos & Point Dread** | **Crystal Castle** | **Skeletor's Throne** |  |
| [![Royal Palace of Eternos and Point Dread](backgrounds/5-eternos-point-dread.png)](backgrounds/5-eternos-point-dread.png) | [![She-Ra and Swift Wind at Crystal Castle](backgrounds/6-crystal-castle.png)](backgrounds/6-crystal-castle.png) | [![Skeletor in the Snake Mountain throne room](backgrounds/7-skeletor-throne.png)](backgrounds/7-skeletor-throne.png) |  |

## Install

```bash
omarchy theme install https://github.com/wesleygrimes/omarchy-eternia-theme.git
```

Omarchy derives the theme name `eternia` from the repository name and applies
it after installation.

### Optional Skeletor crash sounds

Eternia includes an optional easter egg that plays one of four short Skeletor
clips when a native application dumps core. The watcher:

- runs as a lightweight systemd user service
- only plays sounds while Eternia is the active theme
- chooses a random clip for each crash
- limits playback to once every 15 seconds to tame crash loops
- starts at the end of the journal, so old crashes do not trigger at login

Omarchy intentionally does not execute code supplied by a Git-installed theme.
Enable the easter egg explicitly after installing Eternia:

```bash
~/.config/omarchy/themes/eternia/install-easter-eggs
```

The optional watcher requires `systemd`, `journalctl`, `jq`, and `mpv`. These
are present on a standard Omarchy installation. The installer links a user
service from the installed theme directory; it does not use `sudo` or modify
system-wide services.

Confirm that the watcher is running:

```bash
systemctl --user status eternia-crash-watcher.service
```

Preview a random clip safely without crashing an application:

```bash
~/.config/omarchy/themes/eternia/bin/eternia-crash-watcher --test
```

Remove the service without deleting the theme or its clips:

```bash
~/.config/omarchy/themes/eternia/uninstall-easter-eggs
```

## Use

Apply the theme again at any time:

```bash
omarchy theme set Eternia
```

Cycle through the seven included backgrounds:

```bash
omarchy theme bg next
```

## Included

- A complete semantic and ANSI palette in `colors.toml`
- A cyan-violet-gold Hyprland and Omarchy shell border gradient
- A handcrafted, wallpaper-transparent Eternian Command Center btop theme
- A custom Grayskull lock-screen panel with energized and error states
- Seven widescreen backgrounds spanning Castle Grayskull, Eternos, Point Dread,
  Snake Mountain, She-Ra's Crystal Castle on Etheria, and Skeletor's throne room
- A theme-switcher preview
- A widely available Yaru Magenta icon-theme preference
- An optional, rate-limited Skeletor crash-sound easter egg

Omarchy generates safe, version-compatible configurations for terminals,
Neovim, Chromium, Helix, Obsidian, the Omarchy shell, Hyprland, and other
supported applications from `colors.toml`. This repository intentionally does
not ship auto-executed Lua, terminal command configuration, personal Hyprland
settings, or editor-extension installers. The optional shell scripts remain
inert until the user explicitly runs `install-easter-eggs`.

## Compatibility

Designed for current Omarchy releases using the semantic `colors.toml` theme
format. No absolute paths or machine-specific settings are included. Omarchy's
normal fallbacks apply if Yaru Magenta icons are unavailable.

Window opacity, blur, gaps, and corner radius are deliberately left to each
user's existing Hyprland configuration.

## Artwork and attribution

The included backgrounds are AI-generated original fan artwork created for
this theme. They contain no copied logos or text.

This is an unofficial, non-commercial fan project. *He-Man and the Masters of
the Universe*, Eternia, Castle Grayskull, Snake Mountain, and related names and
characters are trademarks and intellectual property of their respective
owners. This project is not affiliated with or endorsed by Mattel.

The optional Skeletor audio clips were downloaded from the
[Voicy Skeletor soundboard](https://www.voicy.network/official-soundboards/series/skeletor).
They remain the property of their respective rights holders and are not covered
by the theme configuration reuse permission below.

The theme configuration may be reused and adapted with attribution. No license
or ownership claim is made over third-party names, characters, or settings.
