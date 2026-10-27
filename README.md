# TaskIyagi

**One taskbar for every Linux desktop — GNOME, KDE Plasma, XFCE, Cinnamon, MATE, LXQt, sway, Hyprland. Start menu, tray, calendar and sticky notes in one panel.**

[English](README.md) · [한국어](README_ko.md)

## Why TaskIyagi?

- **Same panel, whatever desktop you use.** Switch from GNOME to KDE or try Hyprland — your taskbar, pinned apps and notes stay the same. TaskIyagi detects the desktop and adapts; nothing to configure.
- **A familiar start menu and taskbar.** Apps by category with live search, every open window on the bar, one click to minimize or raise.
- **Your day in the clock.** Calendar with notes and reminders, sticky notes, monthly and quick to-dos.
- **Quick settings built in.** Volume, Wi-Fi, Bluetooth, battery, night light, CPU and memory — without opening Settings.
- **Multi-monitor done right.** Pick the monitor for the panel; it follows screens being plugged in, rearranged or rescaled.
- **Make it yours.** Skins, colors, icon size, top or bottom, auto-hide.

## Features

### Launcher and taskbar
- Apps by category, favorites, live search, add your own programs
- Open windows with active-window marker, grouping, pinned apps, kill process

### System tray
- StatusNotifierItem and XEMBED trays — modern and older apps both show up

### Clock, calendar, notes
- Calendar, notes, sticky notes, reminders, monthly tasks, quick tasks

### Quick settings
- Volume · Wi-Fi · Bluetooth · battery · night light
- CPU and memory usage, system monitor, network watch

### Also
- Calculator (inline popup or window)
- Korean/English input indicator, power menu, settings shortcuts
- Global shortcuts (`Shift+Esc` system monitor, `Shift+F1`–`F5` your programs)

## Supported desktops

| Desktop | Window list | Tray | Setup |
|---|---|---|---|
| GNOME (Ubuntu · Fedora default) | ✅ | ✅ | Log out and back in once |
| KDE Plasma | ✅ | ✅ | none |
| labwc · Wayfire · niri · Hyprland | ✅ | ✅ | none |
| sway | ✅ | ✅ | none |
| XFCE · MATE · Cinnamon · LXQt | ✅ | ✅ | none |

On GNOME Wayland, TaskIyagi installs a small helper extension on first run so it can see the window list — that's why one re-login is needed.

## Download

Get the latest version from the **[Releases](https://github.com/iyagicom/TaskIyagi/releases/latest)** page. Qt is bundled — nothing else to install.

| Your system | File to download |
|---|---|
| Ubuntu 24.04 | `taskiyagi_X.Y.Z.ubuntu24.04_amd64.deb` |
| Ubuntu 26.04 / Debian | `taskiyagi_X.Y.Z.ubuntu26.04_amd64.deb` |
| Fedora | `taskiyagi-X.Y.Z-1.x86_64.rpm` |
| Arch Linux | `taskiyagi-X.Y.Z-1-x86_64.pkg.tar.zst` |
| Other distributions | `taskiyagi-vX.Y.Z-x86_64.AppImage` or `taskiyagi-vX.Y.Z-linux-x64.zip` |

Using GNOME only? **[PanelIyagi](https://github.com/iyagicom/PanelIyagi)** is available now.
