# 🚀 SSH Quick Connect (sshm)

A fast, interactive CLI tool to manage and connect to SSH hosts defined in your `~/.ssh/config`.

> Built for developers who prefer speed, clarity, and zero friction in terminal workflows.

---

## ✨ Features

- 🔍 Auto-detects all SSH aliases from config
- 📋 Interactive menu with numeric selection
- 🎨 Clean terminal UI with colors
- ⚡ Fast connection with timeout handling
- 🧠 Smart parsing (handles multiple hosts per line)
- 🧹 Duplicate removal
- 🛑 Safe exit option

---

## 📦 Installation

```bash
git clone https://github.com/Abhrankan-Chakrabarti/sshm.git
cd sshm
chmod +x sshm.sh
````

(Optional) Move to global path:

```bash
mv sshm.sh ~/.local/bin/sshm
```

Now you can run:

```bash
sshm
```

---

## ⚙️ Usage

Simply run:

```bash
sshm
```

You’ll see a menu like:

```
🚀 SSH Quick Connect
─────────────────────────────
 1) server1
 2) production
 3) dev-box
 4) Quit
```

Select a number to connect instantly.

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

✔ Automatically detects:

* `server1`
* `dev`
* `prod`

---

## 🛠️ How It Works

* Parses `~/.ssh/config`
* Extracts all valid `Host` entries (excluding wildcards)
* Builds a dynamic menu
* Connects using `ssh <alias>`

---

## 🔒 Safety & Limitations

* No root access required
* Does not modify SSH config
* Depends on system `ssh` client
* Wildcard (`*`) hosts are ignored

---

## 🚀 Future Improvements

* [ ] 🔎 Fuzzy search with `fzf`
* [ ] 📜 Show HostName/User preview
* [ ] 🕘 Recent connections history
* [ ] ⚡ Direct connect: `sshm <alias>`
* [ ] 🌐 Remote config support

---

## 📁 Project Structure

```
sshm/
├── sshm.sh
└── README.md
```

---

## 👨‍💻 Author

**Abhrankan Chakrabarti**
📧 [abhrankan@gmail.com](mailto:abhrankan@gmail.com)
🔗 [https://github.com/Abhrankan-Chakrabarti](https://github.com/Abhrankan-Chakrabarti)

---

## 📜 License

MIT License
