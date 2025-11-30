# Piwigo-Export-Tool
A robust c# GUI tool to export Piwigo albums and images via SSH. Reconstructs the original directory structure from the MySQL database, fixes encoding errors, and supports incremental backups.

# 📸 Piwigo SSH Export Tool

**The ultimate tool to save all albums and images from your Piwigo server.**

![Platform](https://img.shields.io/badge/Platform-Windows-blue)
![Language](https://img.shields.io/badge/Language-C%23-239120)
![License](https://img.shields.io/badge/License-MIT-green)

## 📖 About
This PowerShell tool provides a modern, dark-themed GUI to export your entire Piwigo gallery directly from your server. Unlike simple FTP downloads, this tool connects to your Piwigo MySQL database to understand the logical album structure and reconstructs it locally on your PC.

It solves common issues like "flat" file structures in the `upload` folder and broken character encodings (e.g., German umlauts).

## ✨ Features

* **🖥️ Modern GUI:** A clean, resizeable WPF interface with a dark theme and neon accents.
* **🔐 Secure Connection:** Full SSH and SCP integration. Supports `id_rsa` keys and password authentication.
* **📂 Structure Reconstruction:** Reads the MySQL/MariaDB database to recreate your exact album hierarchy locally.
* **🛠️ Smart Encoding Fix:** Automatically repairs broken filenames and album names (e.g., fixes `Ã¤` to `ä`, `Zõhler` to `Zähler`).
* **⚡ Incremental Backup:** Checks for existing files to skip duplicates (configurable).
* **📦 ZIP Archiving:** Optional feature to zip every exported album automatically.
* **📜 Integrated Logging:** Built-in SQLite log viewer to track every transfer.
* **📜 Integrated Logging:** Databases (logs and credentials) are encrypted for your security
* **🌍 Multi-Language:** Live switching between English 🇺🇸 and German 🇩🇪.

## 🚀 Prerequisites

* **OS:** Windows 10 or Windows 11 | 64BIT only
* **DISC:** ~ 160MB Space
* **SSH:** OpenSSH Client (enabled by default on Windows).
* **Admin:** Administrator / Root access is needed
* **.NET 8.0 Runtime**

## ⚙️ Usage

1.  Download the `PiwigoExportGUI.exe` file.
2.  Right-click the file and select **"Run Administrator"**.
3.  **Configuration:**
    * **SSH:** Enter your server IP, SSH user, and select your Private Key (OpenSSH format recommended).
    * **Paths:** Select where to save files locally and where Piwigo is located on the server (e.g., `/var/www/html/piwigo`).
    * **Database:** Enter your DB credentials (found in your server's `local/config/database.inc.php`).
4.  Click **🚀 START EXPORT**.

## 📝 Configuration Details

| Setting | Description |
| :--- | :--- |
| **Host / IP** | Your server's IP address or domain. |
| **SSH User** | Your Linux system user (e.g., `root` or `pi`). **Not** the Piwigo web user! |
| **Private Key** | Path to your `id_rsa` file. (Putty `.ppk` files must be converted to OpenSSH format). |
| **Remote Path** | The absolute path to your Piwigo installation on the server. |
| **Conflict Strategy** | Choose between *Overwrite*, *Ignore*, or *Log & Skip* (recommended for backups). |

## ⚖️ License

This project is free to use.
Copyright © 2025 by Malte Speck.
