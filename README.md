<h1 align="center">🚀 TermuxHunter</h1>
<h4 align="center">💻 Run Kali NetHunter GUI & CLI in Termux — No Root Required!</h4>

<p align="center">
  <img src="images/kalivnc.jpg" width="90%" alt="Kali VNC Screenshot">
</p>

---

## 🧠 About the Project

**TermuxHunter** is a powerful mobile pentesting platform that lets you run **Kali Linux NetHunter** inside **Termux** — fully loaded with CLI tools, GUI via VNC, and shell configurations. It’s designed for Android devices without requiring root access.

Whether you’re a bug bounty hunter, ethical hacker, or CTF enthusiast, TermuxHunter brings Kali to your pocket — complete with **auto-install scripts**, **shell enhancements**, and **phantom process killer fix**.

---

## 📦 Features

- 🔧 Full & Minimal Kali NetHunter install
- 🖥️ VNC GUI support
- ⚙️ Custom bash/zsh configs
- 🧵 Lightweight, rootless setup
- 🔐 Non-root login with `kali`, root with `kali -r`
- 🧬 Phantom process killer patch via ADB

---

## 🛠️ Requirements

- Android (ARM64)
- 15GB free storage
- [Termux App (v0.118.2)](https://github.com/termux/termux-app/releases/download/v0.118.2/termux-app_v0.118.2+github-debug_arm64-v8a.apk)
- [VNC Viewer (Kex)](https://store.nethunter.com/repo/com.offsec.nethunter.kex_11525001.apk)

---

## ⚡ Quick Installation

### 🔹 Full Kali NetHunter + VNC (Recommended)
```bash
pkg update && pkg install wget -y
wget -qO- https://raw.githubusercontent.com/KIRAN-KUMAR-K3/TermuxHunter/refs/heads/main/kali_nethunter/kali-full | bash && kali
````

### 🔹 Minimal Kali NetHunter (CLI Only)

```bash
pkg update && pkg install wget -y
wget -qO- https://raw.githubusercontent.com/xiv3r/Termux-Pentesting-Distro/refs/heads/main/KaliLinux/Chroot/kali-minimal | bash && kali
```

---

## 🖥️ VNC GUI Setup

1. Set VNC password:

```bash
kali vnc passwd
```

2. Start VNC service:

```bash
kali vnc &
```

3. Open VNC Viewer and connect to:

```
127.0.0.1:5901
```

Username: `kali`
Password: *(your VNC password)*

<p align="center">
  <img src="images/vncsetup.png" width="60%" alt="VNC Setup">
</p>

---

## 🔓 Access & Management

| Action         | Command          |
| -------------- | ---------------- |
| Login as User  | `kali`           |
| Login as Root  | `kali -r`        |
| Exit Session   | `exit`           |
| Uninstall Kali | `kali-uninstall` |

---

## 🧬 Phantom Process Killer Fix (Optional)

Fix Android’s aggressive background process killer using **Shizuku + ADB shell**.

### 🔹 Steps

1. Download & install:

   * [Shizuku](https://github.com/RikkaApps/Shizuku/releases)
   * [aShell](https://github.com/DP-Hridayan/aShellYou/releases)

2. Enable **wireless debugging** via Developer Options

3. Pair with Shizuku and grant access to aShell

4. Run the following commands:

```bash
adb shell /system/bin/device_config set_sync_disabled_for_tests persistent
adb shell /system/bin/device_config put activity_manager max_phantom_processes 2147483647
adb shell settings put global settings_enable_monitor_phantom_procs false
```

### 🔎 Verify:

```bash
adb shell /system/bin/device_config get activity_manager max_phantom_processes
adb shell dumpsys activity settings | grep max_phantom_processes
```

---

## 🧰 File Structure

```bash
TermuxHunter/
├── README.md
├── images/
│   ├── kalinh.png
│   ├── kalivnc.jpg
│   └── vncsetup.png
├── kali
├── kali-full
├── neofetch
├── rcfiles/
│   ├── etcbash.bashrc
│   ├── home.bashrc
│   ├── home.zshrc
│   ├── homebash.bashrc
│   ├── root.zshrc
│   └── rootbash.bashrc
└── vnc
```

---

## 👨‍💻 Author

**Kiran Kumar K**
Cybersecurity Enthusiast | VAPT | Bug Bounty Hunter
📧 [18kirankumar.k03@gmail.com](mailto:18kirankumar.k03@gmail.com)
🔗 [GitHub](https://github.com/KIRAN-KUMAR-K3) • [LinkedIn](https://www.linkedin.com/in/kiran-kumar-k3/) • [Blog](https://kirankumark3.blogspot.com/)

---

## 📜 License

This project is open-source and available under the [MIT License](https://choosealicense.com/licenses/mit/).

---

> 🚨 **Disclaimer:** This tool is intended for educational and ethical purposes only. Unauthorized use against systems you don’t own is illegal and strictly prohibited.

