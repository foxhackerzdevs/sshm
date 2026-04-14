# 🚀 SSH Quick Connect (sshm)  
### Fast CLI SSH Alias Manager  

<p align="center">
  <img src="https://img.shields.io/badge/version-1.0-blue.svg">
  <img src="https://img.shields.io/badge/bash-cli-green.svg">
  <img src="https://img.shields.io/badge/license-MIT-yellow.svg">
  <img src="https://img.shields.io/badge/status-active-success.svg">
</p>

<p align="center">
  <b>Fast • Minimal • Zero-friction SSH Workflow</b>
</p>

---

## 📌 Overview

**sshm** is a lightweight CLI tool that lets you quickly connect to SSH hosts defined in your `~/.ssh/config`.

No typing. No remembering aliases. Just select and connect.

---

## ✨ Features

- 🔍 Auto-detects SSH aliases  
- 📋 Interactive numbered menu  
- ⚡ Fast connection with timeout  
- 🧠 Smart parsing (multiple hosts per line)  
- 🧹 Duplicate removal  
- 🎨 Clean terminal UI  
- 🛑 Safe exit  

---

## 📦 Installation

```bash
git clone https://github.com/foxhackerzdevs/sshm.git
cd sshm
chmod +x sshm.sh
````

(Optional)

```bash
mv sshm.sh ~/.local/bin/sshm
```

---

## ⚙️ Usage

```bash
sshm
```

Example:

```
🚀 SSH Quick Connect
─────────────────────────────
 1) server1
 2) production
 3) dev-box
 4) Quit
```

---

## 🧩 Example SSH Config

```ssh
Host server1
    HostName example.com
    User user

Host dev prod
    HostName dev.example.com
    User devuser
```

✔ Detects:

* server1
* dev
* prod

---

## 🛠️ How It Works

* Parses `~/.ssh/config`
* Extracts valid `Host` entries
* Builds interactive menu
* Connects using `ssh <alias>`

---

## 🔒 Notes

* Does not modify SSH config
* Requires system `ssh`
* Wildcard (`*`) hosts are ignored

---

## 🚀 Future Plans

* 🔎 Fuzzy search (`fzf`)
* 📜 Show host details
* 🕘 Recent connections
* ⚡ Direct connect (`sshm <alias>`)

---

## 📜 License

MIT License © 2026 Fox Hackerz

---

## 🦊 About Fox Hackerz

We build tools focused on:

* Cybersecurity
* Automation
* Developer tools

📌 GitHub: [https://github.com/foxhackerzdevs](https://github.com/foxhackerzdevs)

---

<p align="center">
  <b>🦊 Join the pack. Build. Break. Secure.</b>
</p>
