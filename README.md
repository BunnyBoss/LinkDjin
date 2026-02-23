# LinkedIn Company Post Automation (Ubuntu)

## Overview

This tool automates publishing posts to a LinkedIn Company Page using keyboard-based browser interaction.

It is designed specifically for **Ubuntu (X11 session)** and uses Google Chrome in Incognito mode to perform automated posting from a text file.

---

## Problem Statement

Publishing LinkedIn company posts programmatically presents challenges:

### 1. Selenium-Based Automation
- LinkedIn may detect automated browser drivers.
- Browser driver setup and maintenance can be complex.
- UI structure changes may require frequent selector updates.

### 2. LinkedIn API Limitations
- Company posting requires access to the Community Management API.
- API approval requires business verification and compliance review.
- Approval timelines can be long and restrictive.

---

## Approach

This tool simulates real keyboard input directly on the browser.

Instead of interacting with LinkedIn’s DOM structure, it:

- Opens Chrome in Incognito mode  
- Types credentials manually  
- Navigates via keyboard (Tab)  
- Pastes content from a text file  
- Publishes the post  

This keeps the automation lightweight and simple.

---

## Features

- Automated LinkedIn login
- Company page post publishing
- Post content loaded from text file (`--text-post`)
- Post in the compay provided as url (`--company-url`)
- Simple CLI interface
- Minimal dependencies

---

## System Requirements

- Ubuntu (X11 session — Wayland is not supported)
- Python 3.12+
- Google Chrome browser
- Conda or virtualenv (recommended)

### Python Dependencies

- None

---

## ⚠️ Important: Wayland vs X11

This tool does **not** work reliably under Wayland.

To check your session type:

```bash
echo $XDG_SESSION_TYPE
```

If it returns `wayland`, log out and select:

```
Ubuntu on Xorg
```

from the login screen before signing in.

---

## Installation

### 1. Clone Repository

```bash
git clone https://github.com/BunnyBoss/LinkDjin
cd LinkDjin
```

### 2. Create Conda Environment (Recommended)

```bash
conda create -n linkdjin python=3.10
conda activate linkdjin
pip install -r requirements.txt
```

### 3. Configure Credentials

Create a `.env` file in the root directory:

```env
LINKEDIN_USERNAME=your_email
LINKEDIN_PASSWORD=your_password
```

---

## Usage

1. Create a text file containing your post content.
2. Run the script:

```bash
python linkdjin.py --text-post path/to/post.txt --company-id 111838940
```


The script will:

1. Copy content from the text file  
2. Open Chrome in Incognito mode  
3. Log into LinkedIn  
4. Navigate to company post section  
5. Publish the content  

---

## Safety Notes

- Do not move your mouse or type while the script is running.
- LinkedIn UI changes may require adjusting tab counts in the script.

---

## Project Structure

```
linkdjin.py
requirements.txt
.env
README.md
ROADMAP.md
```

---

## License

This project is licensed under the MIT License.

---

## Disclaimer

This project is provided for educational and personal productivity purposes.

Users are responsible for ensuring compliance with LinkedIn’s Terms of Service and applicable regulations.

---

## Contact

Poornachandra G  
📧 poornachandra.gedi@gmail.com  

---

## Roadmap

See `ROADMAP.md` for upcoming improvements.
