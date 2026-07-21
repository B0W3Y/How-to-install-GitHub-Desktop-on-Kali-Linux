# 🐧 GitHub Desktop for Kali Linux & Debian-based Systems

[![Linux](https://img.shields.io/badge/OS-Kali_Linux_|_Debian-blue?logo=linux&logoColor=white)](https://www.kali.org/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![GitHub Desktop](https://img.shields.io/badge/App-GitHub_Desktop-purple?logo=github&logoColor=white)](https://github.com/shiftkey/desktop)

A quick, clean, and complete guide to installing **GitHub Desktop** on **Kali Linux** 

---

## 📌 Overview

While GitHub does not officially maintain desktop client for Linux, the open-source community maintains a fully functional build hosted on trusted mirrors. 

This repository provides the exact terminal commands required to add the repository GPG keyring, register the repository source, and install GitHub Desktop natively via `sudo apt`.

---

## 📷 Quick tutorial that guides installation (Click Video Thumbnail)

[![Watch the video](https://img.youtube.com/vi/2qHq1DTjRsw/hqdefault.jpg)](https://www.youtube.com/watch?v=2qHq1DTjRsw)

## ⚡ Quick Installation (3 Steps)

Open your terminal and run these commands in sequence:

### 1️⃣ Add the GPG Security Key
Ensures your system trusts the official package mirror signatures:

---
sudo mkdir -p /etc/apt/keyrings
wget -qO - [https://mirror.mwt.me/shiftkey-desktop/gpgkey](https://mirror.mwt.me/shiftkey-desktop/gpgkey) | gpg --dearmor | sudo tee /etc/apt/keyrings/mwt-desktop.gpg > /dev/null
---

### 2️⃣ Add the Package Repository
Registers the repository source into your APT sources list:

---
sudo sh -c 'echo "deb [arch=amd64 signed-by=/etc/apt/keyrings/mwt-desktop.gpg] [https://mirror.mwt.me/shiftkey-desktop/deb/](https://mirror.mwt.me/shiftkey-desktop/deb/) any main" > /etc/apt/sources.list.d/mwt-desktop.list'
---

### 3️⃣ Update & Install
Refreshes package lists and installs GitHub Desktop cleanly:

---
sudo apt update && sudo apt install github-desktop -y
---
