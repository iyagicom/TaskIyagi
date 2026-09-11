# TaskIyagi

A **Qt6 panel and taskbar** for the Linux desktop.

App launcher, taskbar, system tray, calendar · notes · sticky notes, calculator and quick settings in one panel.
It runs **not only on GNOME but also on KDE Plasma, wlroots-based compositors such as labwc and sway,
and XFCE · MATE · Cinnamon · LXQt**.

> TaskIyagi contains every feature of PanelIyagi, with the window-handling part adapted to each desktop.
> See [Differences from PanelIyagi](#-differences-from-paneliyagi).

[한국어](README.md)

---

## ✨ Features

### App Launcher
* **Apps by category** — Internet · Multimedia · Development · Games, etc.
* **Favorites** — apps you open often move to the top
* **Live search** — by name and description
* **Add programs** — right-click a category to create a launcher entry

### Taskbar
* **Open windows** — received live in the way that fits your desktop ([supported desktops](#-supported-desktops))
* **Active window marker** — the focused window is underlined
* **One click to minimize ↔ raise** — clicking the front window minimizes it, otherwise it comes forward
* **Pin apps** — right-click a window button → Pin to taskbar
* **Pinned app click = new window** — with several windows, hover to pick one from a list
* **Group windows** — windows of the same program under one button
* **Kill process** — end an unresponsive program from the right-click menu
* **Long titles** — trimmed to the button width, including wide CJK text

### System Tray
* **StatusNotifierItem tray** — KDE apps · Electron apps (Discord, Slack …) · app indicators · Qt apps,
  including their menus (submenus, check items)
* **XEMBED tray** — Telegram · Wine programs · ClipIyagi, etc.

### Clock + Calendar / Notes
* **Calendar** — notes per date, days with notes are marked
* **Notes** — categories + pages, full-text search
* **Sticky notes** — note windows on the desktop, restored where you left them
* **Reminders** — a popup at a given time on a given day
* **Monthly tasks** — recurring monthly items, unchecked on the 1st, groupable into categories
* **Quick tasks** — jot down requests from mail or chat; removed automatically after their due date

### Calculator
* Inline popup, separate window, history, always on top

### Quick Settings
* Volume · Wi-Fi · Bluetooth · Battery · Night light (GNOME · KDE)
* CPU · memory usage, system monitor, network watch

### Multi-Monitor
* Choose the monitor for the panel (right-click the panel → Settings)
* Follows monitors being plugged and unplugged, layout and scale changes
* Fullscreen detection uses the panel's own monitor

### Also
* **Korean / English input mode indicator** — HangulIyagi · IBus
* **Power menu** — Suspend · Log out · Restart · Power off (using your desktop's own confirmation dialog)
* **Settings shortcuts** — Wi-Fi · Bluetooth · Display · Sound · Power · Mouse · Printers (opens your desktop's settings)
* **Global shortcuts** — Shift+Esc system monitor, Shift+F1–F5 your assigned programs
* **Skins · colors · icon size · top/bottom position · auto-hide**
* **Korean / English UI** — follows the system language

---

## 🖥 Supported Desktops

TaskIyagi detects the desktop on start and picks the matching method. Nothing to configure.

| Desktop | Window list | StatusNotifierItem tray | Global shortcuts | Setup |
|---|---|---|---|---|
| **GNOME** (Ubuntu · Fedora default) | ✅ | ✅ | ✅ | **Log in again once** (see below) |
| **KDE Plasma** | ✅ | ✅ | ✅ changeable in System Settings > Shortcuts | none |
| **labwc · Wayfire · niri · Hyprland** | ✅ | ✅ | set in the compositor's config | none |
| **sway** (tiling) | ✅ sway does not accept minimize/maximize | ✅ | set in the compositor's config | none |
| **XFCE · MATE · Cinnamon · LXQt** (X11) | ✅ | ✅ | ✅ | none |

### First run on GNOME

For security, GNOME on Wayland does not show other programs' windows to ordinary apps. On first run
TaskIyagi therefore installs a small GNOME extension (**WindowIyagi**) that passes the window list along.
GNOME loads new extensions only at login, so **log out and back in once**.

* The extension only relays the window list and window control. It draws nothing on screen
* Turning off the **"User Extensions" main switch** in the Extensions app also turns off the WindowIyagi
  extension, and the window buttons disappear. The panel then shows ⚠ — click it to see why. To turn off
  another extension, switch off just that one

---

## 🔀 Differences from PanelIyagi

TaskIyagi has every PanelIyagi feature. Both can be **installed and running at the same time** without
getting in each other's way (separate settings, data and shortcuts).

| | PanelIyagi | TaskIyagi |
|---|---|---|
| **Desktops** | GNOME only | GNOME · KDE Plasma · wlroots-based · XFCE/MATE/Cinnamon/LXQt |
| **GNOME extension** | install and enable the PanelIyagi extension yourself | installs the WindowIyagi extension itself on first run (log in again once). No extension outside GNOME |
| **When the extension stops or is turned off** | window buttons vanish without any sign | ⚠ on the panel — click for the reason (disabled · error · user-extensions switch) |
| **Extension updates** | an update landing at the moment of login could leave the extension in an error state | files are swapped in atomically, so this cannot happen |
| **System tray** | XEMBED only | XEMBED + **StatusNotifierItem** — KDE, Electron and app-indicator icons too |
| **Long CJK window titles** | cut by character count, overflowing the button | cut by pixel width, ending in "…" |
| **Power · settings menus** | GNOME commands only | each desktop's own dialog and settings app |
| **Global shortcuts** | GNOME custom shortcuts | GNOME custom shortcuts · KDE global shortcuts · X11 key grabs |
| **Maximized windows vs. the panel** | space reserved on GNOME | also reserved on wlroots-based compositors, so maximized windows don't cover the panel |
| **Data (notes · calendar · sticky notes · reminders)** | PanelIyagi's own | TaskIyagi's own — copy it over once with **"Import from PanelIyagi"** |

### Moving from PanelIyagi

1. Install and start TaskIyagi
2. Right-click an empty spot on the panel → **Import from PanelIyagi…**
3. Confirm — notes · calendar · sticky notes · monthly/quick tasks · reminders · pinned apps · panel settings
   are copied and TaskIyagi restarts

* PanelIyagi's own data is not touched. PanelIyagi may keep running while you import
* Whatever TaskIyagi had is not deleted but moved to `~/.config/IYAGI-INC/TaskIyagi-backup-<date-time>/`
* The monitor you picked for TaskIyagi stays as it is
* With both panels running, Shift+F1–F5 stay with PanelIyagi, which registered them first. After PanelIyagi
  is removed, TaskIyagi takes them on its next start

---

## 🎮 Controls

| Action | How |
|---|---|
| Open the app launcher | App grid button on the left |
| Raise / minimize a window | Click its button |
| Pin · group · assign a shortcut | Right-click a window button |
| Open a new window | Click a pinned app |
| Tray icon menu | Right-click the tray icon (left click does what the app defines) |
| Calendar / notes | Click the clock |
| Calculator | Calculator button |
| Quick settings | Rightmost button |
| Panel settings · import · quit | Right-click an empty spot on the panel |
| System monitor | Shift+Esc |
| Run an assigned program | Shift+F1 – Shift+F5 |
| Window list missing | Click ⚠ on the panel for the reason |

---

## 🚀 Installation

### Ubuntu (deb)

```bash
sudo apt install ./taskiyagi_X.X.X~ubuntuXX.XX_amd64.deb
```

* Starts automatically when you log in
* Qt and the other libraries it needs are bundled — nothing else to install
* On **GNOME**, log in again once after the first run ([why](#first-run-on-gnome))

To stop the automatic start, turn TaskIyagi off in your desktop's "Startup applications" settings.

### Removal

```bash
sudo apt remove taskiyagi
```

Notes and calendar data are kept in the locations below.

---

## ⚙ Data Locations

| Contents | Path |
|---|---|
| Panel settings (position · size · pinned apps · shortcut slots) | `~/.config/IYAGI-INC/TaskIyagi.conf` |
| Notes · calendar · sticky notes · tasks | `~/.local/share/TaskIyagi/taskiyagi.db` |
| Reminders | `~/.config/IYAGI-INC/TaskIyagi-Alarms.conf` |
| Sticky note positions | `~/.config/IYAGI-INC/stickynotes-taskiyagi.ini` |
| Backup made before an import | `~/.config/IYAGI-INC/TaskIyagi-backup-<date-time>/` |

---

## 👤 Developer

IYAGI INC
Email: [iyagicom@gmail.com](mailto:iyagicom@gmail.com)
GitHub: https://github.com/iyagicom

---

## 📜 License

Copyright (c) 2026 IYAGI INC. All rights reserved.

This software is provided in executable form only; the source code is not published.

You may freely use, install, package and redistribute it for any purpose — personal, commercial,
educational, governmental or organizational.

License notices for the bundled open-source components (Qt, etc.) are in `/usr/share/doc/taskiyagi/licenses/`.
