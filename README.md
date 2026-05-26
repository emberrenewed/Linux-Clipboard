<div align="center">

<img src="assets/hero.svg" alt="Clipd — Native Ubuntu Clipboard Manager" width="100%"/>

# Clipd

### A native, GNOME-quality clipboard manager for Ubuntu.

#### Built with GTK 4 · Libadwaita · Pure native UX. No Electron.

<br/>

[![Download .deb](https://img.shields.io/github/v/release/emberrenewed/Ubuntu-Clipboard?style=for-the-badge&logo=ubuntu&logoColor=white&label=Download%20.deb&color=E95420)](https://github.com/emberrenewed/Ubuntu-Clipboard/releases/latest)
[![Stack](https://img.shields.io/badge/Stack-GTK4%20%2B%20Libadwaita-orange?style=for-the-badge&logo=gtk)](#)
[![Wayland](https://img.shields.io/badge/Wayland-ready-blueviolet?style=for-the-badge&logo=wayland)](#)

[![Built by CodeAhmad](https://img.shields.io/badge/Built%20by-CodeAhmad-ED1B24?style=for-the-badge)](https://github.com/emberrenewed)
[![Kurdish UI](https://img.shields.io/badge/UI-Kurdish%20Sorani-009A44?style=for-the-badge)](#)
[![Shortcut](https://img.shields.io/badge/Shortcut-Super%2BB-FFCC00?style=for-the-badge)](#)

</div>

---

## ⚡ Install on Ubuntu 24.04+

Copy and paste this whole block into your terminal:

```bash
sudo apt update
sudo apt install -y python3-gi gir1.2-gtk-4.0 gir1.2-adw-1 \
  gir1.2-ayatanaappindicator3-0.1 xclip wl-clipboard \
  python3-pil libnotify-bin

cd /tmp
wget https://github.com/emberrenewed/Ubuntu-Clipboard/releases/latest/download/clipd_0.1.0_all.deb
sudo apt install -y ./clipd_0.1.0_all.deb

systemctl --user enable --now clipd.service
```

That's it. The daemon now starts automatically every time you log in.

To open the window press **Super + B**, or type `clipd` in a terminal.

> First time using `Super + B`?
> Open **Settings → Keyboard → View and Customize Shortcuts → Custom Shortcuts**, click **+**, set
> **Name** = `Open Clipd`, **Command** = `clipd`, **Shortcut** = `Super + B`. Save.

---

## ✨ Features

<table>
<tr>
<td width="33%" valign="top">

### 🪟 Native GNOME UI
- AdwApplicationWindow + NavigationSplitView
- Symbolic icons everywhere
- Auto light/dark
- Ubuntu accent matching
- Smooth Adwaita animations

</td>
<td width="33%" valign="top">

### 📋 Captures everything
- Plain & rich text
- Code with language detection
- URLs auto-classified
- Images & screenshots
- Files / file lists
- Live FTS5 search

</td>
<td width="33%" valign="top">

### 🔒 Privacy first
- 100% local SQLite
- No telemetry, ever
- Skips password managers
- Detects keys, OTP, CC#
- Hardened systemd unit
- Open install path

</td>
</tr>
<tr>
<td valign="top">

### ⚡ Performance
- ~30 MB RAM idle
- Near-zero CPU
- WAL-mode SQLite
- FTS5 indexed search
- Async write pipeline
- Lazy thumbnails

</td>
<td valign="top">

### 🌐 Kurdish Sorani UI
- Full Sorani translation
- RTL layout flip
- Curated for native usage
- One-click switch
- KURDISTAN brand footer
- Bundled flag artwork

</td>
<td valign="top">

### 🚀 Set & forget
- Auto-start at login
- Survives reboots (linger)
- Super+B opens instantly
- DBus paste-back
- Wayland & X11 supported

</td>
</tr>
</table>

---

## 🇰🇼 Kurdish Sorani UI

<div align="center">
  <img src="assets/i18n.svg" alt="English ↔ Sorani Kurdish" width="100%"/>
</div>

Switch the entire interface to **کوردی سۆرانی** with one click — every menu, label, and preview message has a hand-curated translation. Layout flips automatically to RTL.

The bundled palette and high-resolution flag background are both opt-in (Preferences → Appearance). You can also drop in any custom image you like — png, jpg, webp — and tune its opacity to your taste.

---

## ⌨️ Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| `Super` + `B` | Open Clipd window |
| `Ctrl` + `Alt` + `V` | Quick-paste popup |
| `Ctrl` + `F` | Focus search |
| `Enter` | Paste selected item |
| `Ctrl` + `P` | Toggle pin |
| `Delete` | Remove item |
| `Ctrl` + `,` | Preferences |

---

## 🔄 Update

Re-run the install block above. `apt` upgrades the package and restarts the daemon.

---

## 🧹 Uninstall

```bash
systemctl --user disable --now clipd.service
sudo apt remove -y clipd
rm -rf ~/.local/share/clipd ~/.cache/clipd ~/.config/clipd ~/.local/state/clipd
```

---

## 🐛 Troubleshooting

<details>
<summary><b>Items don't appear in the list</b></summary>

Check the daemon is running:
```bash
systemctl --user status clipd.service --no-pager | head -10
```
Confirm DBus reachability:
```bash
gdbus call --session --dest io.github.clipd.Daemon \
  --object-path /io/github/clipd/Daemon \
  --method io.github.clipd.Daemon.Stats
```
If `total=0`, copy something fresh and try again — old clipboard contents at startup are deliberately ignored.
</details>

<details>
<summary><b>Super+B does nothing</b></summary>

Open **Settings → Keyboard → Custom Shortcuts**, find or add **Open Clipd** with command `clipd` and binding `Super+B`.
</details>

<details>
<summary><b>Tray icon missing on GNOME</b></summary>

GNOME 42+ doesn't ship a system tray. Install the **AppIndicator and KStatusNotifierItem Support** GNOME Shell extension to get one. Clipd works fine without it.
</details>

<details>
<summary><b>Wrong directory error: <code>Unsupported file ./clipd_0.1.0_all.deb</code></b></summary>

You're running `apt install ./clipd_0.1.0_all.deb` from a folder that doesn't have the .deb file. Either `cd` to the folder where you downloaded it, or use the full path:
```bash
sudo apt install /tmp/clipd_0.1.0_all.deb
```
</details>

---

## 🙏 Credits

Built by **[CodeAhmad](https://github.com/emberrenewed)** with respect for native Linux UX.

---

## 📜 License

Proprietary © 2026 CodeAhmad. Free to install and use; redistribution, modification, and reverse engineering are not permitted.

<div align="center">

<br/>

**KURDISTAN**

#### ⭐ If Clipd makes your day a little smoother, give the repo a star.

[![Star on GitHub](https://img.shields.io/github/stars/emberrenewed/Ubuntu-Clipboard?style=for-the-badge&logo=github&color=FFCC00&labelColor=1B1B1B)](https://github.com/emberrenewed/Ubuntu-Clipboard/stargazers)

</div>
