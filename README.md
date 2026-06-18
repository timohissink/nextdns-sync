# NextDNS Sync Tool

> A lightweight, self-contained web application for managing, comparing, backing up, and synchronizing NextDNS profiles — no installation, backend, or external dependencies required.

![Version](https://img.shields.io/badge/Version-4.0-brightgreen.svg)
![License: GPLv3](https://img.shields.io/badge/License-GPLv3-blue.svg)
![HTML](https://img.shields.io/badge/Built%20with-HTML%2FJS-orange.svg)
![NextDNS](https://img.shields.io/badge/API-NextDNS-blueviolet.svg)

---

## Overview

Managing multiple NextDNS profiles can quickly become tedious. Whether you maintain separate profiles for different devices, family members, locations, or customers, keeping settings synchronized often means repeating the same changes multiple times.

The **NextDNS Sync Tool** eliminates that hassle.

Built as a single HTML file, it runs entirely in your browser and connects directly to the NextDNS API using your personal API key. No installation, server, account registration, or third-party services are required.

Simply open the app and start managing your profiles.

---

## Features

### 🔄 Profile Synchronization

Synchronize settings from a designated **master profile** to one or more target profiles.

Choose exactly which components should be included:

- Denylist & Allowlist
- DNS Rewrites
- Security settings (Threat Intelligence, AI Detection, Safe Browsing, etc.)
- TLD Blocklists
- Privacy settings & blocklists
- Parental Controls

Before any changes are applied, the tool generates a detailed **diff preview** showing exactly what will be added, removed, or remain unchanged. Differences are grouped by profile and category with clear color-coded indicators.

Individual entries can be excluded from the sync or force-applied when needed.

#### Preset Configurations

Save commonly used synchronization setups—including source profile, target profiles, and selected categories—and restore them instantly with a single click.

---

### 🔑 Multi-Account Support

Manage multiple NextDNS accounts simultaneously.

Add multiple API keys during login and switch between accounts directly from the application header. Each account displays:

- Custom name
- Number of available profiles
- Quick remove option

The tool fully supports **cross-account synchronization**, allowing a source profile from one account to synchronize with target profiles from another. API credentials are resolved automatically per profile.

Optionally, API keys can be remembered for the current browser session using `sessionStorage`. Stored keys are automatically removed when the browser is closed.

---

### 💻 Device Management

View all devices linked to a profile in a searchable interface.

Features include:

- Device name and model filtering
- Query statistics
- Visual usage indicators
- Quick profile association overview

---

### 📡 Live DNS Query Monitoring (Flows)

Monitor DNS traffic in real time using NextDNS Flow events.

Filter queries by:

- Device
- Domain
- Blocked requests only

Ideal for troubleshooting filtering rules, identifying blocked services, or validating newly created policies.

---

### ✏️ Quick Edit

Make rapid changes without opening the synchronization workflow.

Supported actions:

- Add or remove denylist entries
- Add or remove allowlist entries
- Manage DNS rewrites
- Bulk domain input
- `.txt` file import

Save frequently used domain collections as presets and apply them whenever needed.

---

### 💾 Configuration Management

Create complete backups of your NextDNS profiles and restore them at any time.

Features include:

- Export profiles to portable JSON snapshots
- Import configurations into existing or new accounts
- Human-readable configuration previews
- Profile creation directly from the interface

This makes migration, backup, and disaster recovery straightforward.

---

### ⇄ Profile Comparison

Compare any two profiles side by side without making changes.

The comparison view highlights differences across selected categories and displays individual additions, removals, and modifications.

Supports comparisons across multiple accounts.

---

### 🕘 Activity History

Every synchronization and duplication action is automatically recorded.

History entries include:

- Timestamp
- Source and target profiles
- Categories involved
- Number of additions and removals

Export the entire activity log as a text file or clear it whenever desired.

---

## Getting Started

### 1. Download

Download or clone the repository and save `nextdns-sync.html` to your computer.

### 2. Serve Locally

Most browsers block API requests from `file://` URLs due to CORS restrictions. Serve the file using a simple local web server:

```bash
# Python
python3 -m http.server 8080

# Node.js
npx serve .

# PHP
php -S localhost:8080
```

Then open:

```text
http://localhost:8080/nextdns-sync.html
```

### 3. Log In

Enter your NextDNS API key.

You can find it at:

https://my.nextdns.io/account

under **Account → API Key**.

#### Demo Mode

Enter:

```text
demo
```

as your API key to explore the application using realistic sample data. No requests will be sent to NextDNS.

---

## How to Synchronize Profiles

1. Select a **Master Profile** (source profile).
2. Select one or more **Target Profiles**.
3. Choose the categories to synchronize.
4. Optionally enable **Remove if not in master** to delete entries that no longer exist in the source profile.
5. Click **Preview Changes**.
6. Review the generated diff.
7. Apply the changes.

Frequently used configurations can be saved as **Preset Configurations** for one-click reuse.

---

## Additional Actions

| Action | Location |
|----------|----------|
| Rename a profile | Profile Sync sidebar |
| Duplicate a profile | Profile Sync sidebar |
| Compare profiles | Compare tab |
| Create a profile | Config Management tab |
| View history | History tab |

---

## Privacy & Security

Privacy is a core design principle of this project.

- API keys are **never stored in localStorage**
- No data is sent to third-party services
- All requests go directly to `api.nextdns.io`
- The application runs entirely client-side
- The full source code can be inspected and audited

If enabled, API keys are stored only in `sessionStorage` and are automatically removed when the browser session ends.

---

## Interface

### 🌙 Dark Mode

Supports both light and dark themes.

The application follows your operating system preference on first launch and can be changed at any time.

### 🌍 Localization

Available in:

- English
- Dutch (Nederlands)

The default language is automatically selected based on your browser settings.

### 🧪 Demo Mode

Use `demo` as your API key to explore the full application without requiring a NextDNS account.

---

## Browser Compatibility

Compatible with all modern browsers:

- Google Chrome
- Mozilla Firefox
- Microsoft Edge
- Safari

JavaScript must be enabled.

---

## Contributing

Bug reports, feature requests, and pull requests are welcome.

GitHub repository:

https://github.com/timohissink/nextdns-sync

---

## License

Licensed under the GNU General Public License v3.0 (GPL-3.0).

See the LICENSE file for details.

---

Maintained by Timo Hissink.
