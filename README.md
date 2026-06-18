# NextDNS Sync Tool

> A self-contained, single-file web app for managing and syncing your NextDNS profiles — no installation, no backend, no dependencies.

![Version](https://img.shields.io/badge/Version-4.0-brightgreen.svg)
![License: GPLv3](https://img.shields.io/badge/License-GPLv3-blue.svg)
![HTML](https://img.shields.io/badge/Built%20with-HTML%2FJS-orange.svg)
![NextDNS](https://img.shields.io/badge/API-NextDNS-blueviolet.svg)

---

## What is this?

If you manage multiple [NextDNS](https://nextdns.io) profiles — for example, one per device, family member, or network — you know the pain of keeping them in sync. Adding a domain to the denylist of one profile means manually repeating that on every other profile.

**NextDNS Sync Tool** solves that. It's a single HTML file you open in your browser that connects directly to the NextDNS API using your API key. No server, no signup, no install. Just open and go.

---

## Features

### 🔄 Profile Sync
Copy settings from a **master profile** to one or more target profiles. Choose exactly what to sync:
- Denylist & Allowlist
- DNS Rewrites
- Security settings (threat intelligence, AI detection, Safe Browsing, etc.)
- TLD Blocklist
- Privacy settings & blocklists
- Parental controls

Before applying anything, you get a full **diff preview** — color-coded per profile, per category — showing exactly what will be added, removed, or left unchanged. Individual entries can be skipped or force-applied.

**Preset selections** let you save your favorite sync configurations (source profile, targets, categories) and reload them with one click — no need to reconfigure every time.

### 🔑 Multi-Account Support
Add multiple NextDNS API keys in a single session. Each key is added on the login screen and shown in a list with a name, profile count, and a 🗑 button to remove it. You can switch between accounts inside the app via the header switcher.

**Cross-account sync** is fully supported: the master profile and target profiles can belong to different accounts. The correct API key is resolved per profile automatically.

Keys can optionally be remembered for the duration of the browser session (sessionStorage — cleared when you close the browser). A name field appears when you choose to remember a key.

### 💻 Devices
View all devices linked to a profile, filterable by name or model, with query counts and a usage bar.

### 📡 Flows (Live DNS Query Log)
Stream live DNS queries per profile in real time using Server-Sent Events. Filter by device, domain, or blocked-only. Useful for diagnosing what's being blocked or allowed as it happens.

### ✏️ Quick Edit
Rapidly add or remove domains from any profile's denylist, allowlist, or rewrites — without going through the full sync flow. Supports bulk input and file upload (`.txt`). **Preset selections** let you save common domain sets and reapply them instantly.

### 💾 Config Management
Back up and export profiles to a portable JSON snapshot and import them back later — or onto a different account. Includes a human-readable preview with all settings, lists, and rules laid out clearly. Create new profiles directly from this tab.

### ⇄ Compare
Place two profiles side by side and see exactly where they differ — per category, per entry — without changing anything. Works across accounts. Filter which components to compare using the sidebar checkboxes.

### 🕘 History
Every sync and duplication is logged automatically: when it ran, which profiles were involved, how many items were added or removed, and which categories were included. Export the full log as a `.txt` file, or clear it from the sidebar.

---

## Getting Started

### 1. Download
Save `nextdns-sync.html` to your computer. That's the whole app.

### 2. Serve it locally (required for API access)
Most browsers block direct API calls from local `file://` pages due to CORS restrictions. Serve the file with a simple local server instead:

```bash
# Python (built-in)
python3 -m http.server 8080

# Node.js (npx)
npx serve .

# PHP
php -S localhost:8080
```

Then open `http://localhost:8080/nextdns-sync.html` in your browser.

### 3. Log in
Enter your NextDNS API key. You can find it at [my.nextdns.io/account](https://my.nextdns.io/account) under **API**.

> **No API key?** Type `demo` to explore the app with sample data. Nothing is sent to NextDNS.

You can add multiple keys on the login screen to manage several accounts simultaneously. Each key appears in a list with a name and profile count; click any to re-add it, or use 🗑 to forget it.

---

## How to Sync Profiles

1. Select a **Master Profile** from the dropdown — this is the source (any account).
2. Check one or more **target profiles** to sync to (any account, grouped by account if you have multiple).
3. Choose which **categories** to sync (denylist, security settings, etc.).
4. Optionally enable **"Remove if not in master"** to clean up entries that no longer exist in the master.
5. Click **Preview Changes** to see a full diff.
6. Review, skip individual items if needed, then click **Apply Changes**.

Save frequently-used configurations as **Preset selections** to skip steps 1–4 next time.

---

## Other Actions

| Action | Where |
|---|---|
| Rename a profile | Profile Sync sidebar → ✎ Rename |
| Duplicate a profile | Profile Sync sidebar → ⧉ Duplicate |
| Compare two profiles | Compare tab |
| Create a new profile | Config Management tab |
| View sync history | History tab |

---

## Privacy & Security

- Your API key is **never stored in `localStorage`** or sent to any third party.
- If you choose "Remember temporarily", the key is stored in `sessionStorage` only — it disappears when you close the browser.
- All API calls go directly from your browser to `api.nextdns.io`. Nothing passes through any intermediate server.
- The app is entirely client-side JavaScript in a single file. You can audit every line.

---

## Interface

- **Dark mode** — toggle in the top-right corner, respects your OS preference on first load.
- **Language** — English and Dutch (NL), defaults to your browser language. Toggle in the top-right corner.
- **Demo mode** — type `demo` as your API key to explore the full interface with realistic sample data.

---

## Browser Compatibility

Works in any modern browser (Chrome, Firefox, Edge, Safari). Requires JavaScript to be enabled.

---

## Contributing

Found a bug or want to add something? Feel free to open an issue or pull request at [github.com/timohissink/nextdns-sync](https://github.com/timohissink/nextdns-sync).

---

## License

GNU General Public License v3.0 — see [LICENSE](LICENSE) for details.

Maintained by [Timo Hissink](https://github.com/timohissink).
