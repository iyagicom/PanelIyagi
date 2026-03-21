# PanelIyagi

A **custom Qt6 panel / taskbar** for Ubuntu GNOME.

Integrates with the GNOME Shell Extension via D-Bus to provide window tracking, app launching, and quick settings — all in one panel.

> **Ubuntu only** — Built on X11 (XCB) protocols. Runs in XCB mode even on Wayland sessions.

---

## ✨ Features

### App Launcher
* **Category view** — freedesktop categories (Internet · Media · Development · Games, etc.)
* **Favorites** — top 20 apps ranked by click count, shown automatically
* **Real-time search** — searches app name and generic name simultaneously
* **Register app** — right-click a category → create a .desktop entry directly
* **Icon auto-discovery** — Yaru theme → GNOME fallback chain → /usr/share/pixmaps → direct scan

### Taskbar
* **Open window list** — synced in real-time with GNOME Shell Extension via D-Bus
* **Pin apps** — pin frequently used apps to the left area (right-click → pin/unpin)
* **Active window highlight** — visual indicator on the currently focused window
* **Minimize / focus toggle** — click to toggle between minimize and focus

### Calculator
* **Panel popup** — click 🧮 to open an inline calculator popup instantly
* **Standalone window** — open a separate calculator window from the popup
* **History** — result list with automatic thousands-separator formatting
* **Always on top** — right-click the standalone window to pin it on top

### System Tray
* **XEMBED standard** — shows tray icons from Telegram, Discord, ClipIyagi, etc.

### Clock + Calendar / Notes
* **Clock** — two-line display (hh:mm + date), click to open popup
* **Calendar** — per-date notes, highlights dates that have notes
* **Notes** — category + page hierarchy, stored in SQLite
* **Full search** — unified search across calendar notes and memos
* **Sticky notes** — desktop-pinned note windows, restored after restart

### Quick Settings
* **Volume** — slider, mute toggle, mouse wheel adjustment
* **Wi-Fi** — on/off toggle, network list, password prompt for secured networks
* **Bluetooth** — on/off toggle, paired device list, connect/disconnect
* **Battery** — percentage + status (Charging / Discharging / Full), shown only when present

### IME Input Mode Indicator
* **Korean / English live display** — shows IBus input mode directly on the panel (Korean in orange · English in grey)

### Power Menu
* Log out · Restart · Shut down

### Right-click Menu
* Icon size (24 / 32 / 40 / 48 px) · Icon alignment (left / center)
* Panel position (top / bottom) · Panel preferences dialog
* System settings shortcuts (Wi-Fi · Bluetooth · Display · Sound · Power · Mouse · Printers)
* System Monitor

### Extension Indicators
* Real-time display of GNOME screen recording / screen sharing indicators
* Notification buttons from Desktop Icons and other extensions

### Multilingual UI
* Automatically uses Korean when the system language is Korean, English otherwise

---

## 🎮 Controls

| Action | How |
|---|---|
| Open app launcher | Click or hover the ⊞ button |
| Open quick settings | Click the 🔊 button |
| Open calendar / notes | Click the clock |
| Open calculator | Click the 🧮 button |
| Panel settings | Right-click panel → 🔧 Panel Settings |
| Pin an app | Right-click taskbar button → Pin |
| Adjust volume | Mouse wheel in quick settings |

---

## 🚀 Installation

### 1. Download the latest binary

Download the latest release from [GitHub Releases](https://github.com/iyagicom/PanelIyagi/releases) and extract.

```
PanelIyagi/
├── PanelIyagi                          ← executable
└── extension/paneliyagi@iyagi.com/     ← GNOME Shell extension
```

### 2. Install the GNOME Shell Extension

```bash
bash extension/install.sh

gnome-extensions enable paneliyagi@iyagi.com
```

Log out and back in if GNOME Shell needs to restart.

### 3. Run PanelIyagi

```bash
chmod +x PanelIyagi
./PanelIyagi &
```

### 4. Register for autostart (recommended)

Right-click the panel → **⚙ Settings** → check **Launch at startup**.

Or manually:

```bash
mkdir -p ~/.config/autostart
cat > ~/.config/autostart/paneliyagi.desktop << 'EOF'
[Desktop Entry]
Type=Application
Name=PanelIyagi
Exec=/path/to/PanelIyagi
Hidden=false
X-GNOME-Autostart-enabled=true
EOF
```

---

## ⚙ Configuration file locations

| Content | Path |
|---|---|
| Panel settings (position, size, pinned apps) | `~/.config/PanelIyagi/PanelIyagi.conf` |
| Calendar / notes SQLite DB | `~/.local/share/PanelIyagi/paneliyagi.db` |
| Sticky note positions / sizes | `~/.config/PanelIyagi/stickynotes.ini` |
| App click counts (favorites) | `~/.config/PanelIyagi/app_clicks.ini` |

---

## 🏗 Architecture

```
PanelIyagi (Qt6 + XCB)
│
├── Engine         — D-Bus service (org.iyagi.Engine)
│     └── EngineAdaptor — D-Bus XML interface
│
├── Panel          — Main panel window (_NET_WM_WINDOW_TYPE_DOCK)
│     ├── AppLauncherPopup — App launcher popup
│     ├── TaskButton       — Open window button
│     ├── PinnedButton     — Pinned app button
│     ├── TrayManager      — XEMBED system tray
│     ├── IME Label        — Korean / English input mode indicator
│     ├── ClockWidget      — Clickable clock
│     ├── CalcPopup        — Calculator popup
│     ├── CalcWindow       — Calculator standalone window
│     ├── ClockPopup       — Clock popup → NoteWindow
│     ├── QuickPanel       — Quick settings popup
│     └── SettingsDialog   — Panel preferences
│
├── NoteWindow     — Calendar / notes / search window
│     ├── MemoDB   — SQLite storage
│     └── StickyNote — Desktop sticky note
│
└── GNOME Shell Extension (paneliyagi@iyagi.com)
      └── D-Bus → Engine — Bridges window events and app launches
```

---

## 🖥 Supported Platforms

* Ubuntu 22.04 / 24.04 (GNOME 46, X11 or Wayland+XCB)
* Qt 6.2+

---

## 👤 Author

IYAGI INC
Email: [iyagicom@gmail.com](mailto:iyagicom@gmail.com)
GitHub: https://github.com/iyagicom

---

## 📜 License

Copyright (c) 2026 IYAGI INC. All rights reserved.

This software is provided as **executable files only**. Source code is not publicly available.

You may use this software for personal and non-commercial purposes.
Redistribution, modification, or reverse engineering is prohibited without explicit written permission from the author.
