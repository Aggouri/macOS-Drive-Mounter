# 💾 macOS Drive Mounter

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

---

**Differences with upstream**:
- pick a custom drive configuration file, so that it is stored separately from the script location
- the scripts are already executable

---

A simple, robust, and persistent tool to automatically mount your network drives on macOS and keep them connected.

This script solves the common frustration of macOS dropping connections to network shares after waking from sleep or changing networks. It uses the same reliable mounting engine as Finder's "Go > Connect to Server" feature, ensuring the highest level of compatibility.

**Visit the project's homepage:** [pangeranwiguan.com/macos-drive-mounter](https://pangeranwiguan.com/macos-drive-mounter)

---

## ✨ Features

- ⚙️ **Reliable Mounting Engine:** Uses AppleScript to communicate directly with the Finder, bypassing the inconsistencies of lower-level mount commands.
- 🚀 **Runs Automatically:** A persistent agent runs at login and every 30 seconds to ensure your drives are always available.
- 📝 **Simple Configuration:** A clean, 4-column text file makes adding or changing drives incredibly easy. No more confusing URL encoding!
- 📦 **Portable & Self-Contained:** Everything you need is in one folder. Place it anywhere on your Mac and run the installer.
- 🛡️ **macOS Security Compliant:** Works with modern macOS security features by guiding you through a one-time permission process.

---

## 🚀 Setup Guide

Follow these five steps to get your drives mounting automatically.

### Step 1: Get the Files

Clone or download this repository to a permanent location on your Mac (e.g., in your `~/Documents` or `~/Scripts` folder).

```bash
# Clone the repository using Git
git clone https://github.com/Aggouri/macOS-Drive-Mounter.git
```

_Or, download the ZIP and extract it._

### Step 2: Configure Your Drives

Before activating the script, tell it which drives to mount.
By default, the script uses the `drives.txt` file that is collocated with the script, but you can choose to use any other file.

To use the existing `drives.txt` file:
1.  Open the `drives.txt` file in a text editor.
2.  Replace the generic examples with your own server details using the 4-column format.

To use another file:
1. Copy the existing `drives.txt` file to your desired location, using any filename you want.
2. Replace the generic examples with your own server details using the 4-column format.

```
# --- FORMAT ---
# server_address    "Share Name"    username    "Password"

# --- EXAMPLES (replace these with your actual drives) ---
MyNAS.local             Public          guest       ""
192.168.1.50            "My Documents"  myuser      "SimplePass123"
fileserver.local        "Scans@HP"      scanner     "Scan-Pass!"
10.0.0.10               Backups         admin       "My$uperP@ssw0rd!"
```

**Important:** If your Share Name or Password contains spaces or special characters (like `@`, `!`, `$`, `#`), you **MUST** enclose it in `"double quotes"`.

### Step 3: Open Terminal and Navigate

Open the **Terminal** app and change into the script's directory.

```bash
cd path/to/macOS-Drive-Mounter
```

### Step 4: Make Scripts Executable

Run this command once to give the scripts permission to run.

```bash
chmod +x *.sh
```

### Step 5: Run the Installer

This command will set up the background service and run the script for the first time.

If using the default `drives.txt` file, run:

```bash
./install.sh
```

If using a custom file, run:

```bash
./install.sh path/to/file
```

> `path/to/file` is the path to the custom file

### Step 6: Approve One-Time Security Prompts

The very first time the script runs, macOS will ask for your permission. **This is normal and expected.**

- You may see a prompt asking for permission to control the Finder. **Click Allow.**
- For each new server, you may see a prompt asking, "You are attempting to connect to the server...". **Click Connect.**

Once you have approved these prompts, they will not appear again.

✅ **Setup Complete!** Your drives will now mount automatically at login and reconnect every 30 seconds if they disconnect.

---

## 🗑️ Uninstallation

If you wish to stop the script and remove it:

1.  **Navigate to the Directory** in Terminal.
2.  **Run the Uninstaller:**
    ```bash
    ./uninstall.sh
    ```
3.  You can now safely delete the `macOS-Drive-Mounter` folder.

---

## 📜 License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for the full text.

---

## ✍️ Author

**Pangeran Wiguan**

- **Website:** [pangeranwiguan.com](https://pangeranwiguan.com)
- **Email:** [pangeranwiguan@gmail.com](mailto:pangeranwiguan@gmail.com)
- **Project Page:** [pangeranwiguan.com/macos-drive-mounter](https://pangeranwiguan.com/macos-drive-mounter)
