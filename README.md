# NextDNS Profile Sync

> A self-contained, single-file web app for managing and syncing your NextDNS profiles — no installation, no backend, no dependencies.

![License: GPLv3](https://img.shields.io/badge/License-GPLv3-blue.svg)
![HTML](https://img.shields.io/badge/Built%20with-HTML%2FJS-orange.svg)
![NextDNS](https://img.shields.io/badge/API-NextDNS-blueviolet.svg)

---

## What is this?

If you manage multiple [NextDNS](https://nextdns.io) profiles — for example, one per device, family member, or network — you know the pain of keeping them in sync. Adding a domain to the denylist of one profile means manually repeating that on every other profile.

**NextDNS Profile Sync** solves that. It's a single HTML file you open in your browser that connects directly to the NextDNS API using your API key. No server, no signup, no install. Just open and go.

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

### 💻 Devices
View all devices linked to a profile, filterable by name or model.

### 📡 Flows (DNS Query Log)
Inspect recent DNS query logs per profile. Filter by device to see per-device traffic. Useful for spotting what's being blocked or allowed in real time.

### ✏️ Quick Edit
Make rapid changes to any profile's denylist or allowlist without going through the full sync flow.

### 💾 Config Management
Back-up and export your profiles to a portable JSON snapshot and import them back later — or onto a different account. Includes a human-readable preview with all settings, lists, and rules laid out clearly.

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

---

## How to Sync Profiles

1. Select a **Master Profile** from the dropdown — this is the source.
2. Check one or more **target profiles** to sync to.
3. Choose which **categories** to sync (denylist, security settings, etc.).
4. Optionally enable **"Remove if not in master"** to clean up entries that no longer exist in the master.
5. Click **Preview Changes** to see a full diff.
6. Review, skip individual items if needed, then click **Apply Changes**.

---

## Privacy & Security

- Your API key is stored in `sessionStorage` only — it disappears when you close the tab.
- All API calls go directly from your browser to `api.nextdns.io`. Nothing passes through any third-party server.
- The app is entirely client-side JavaScript. You can audit every line.

---

## Browser Compatibility

Works in any modern browser (Chrome, Firefox, Edge, Safari). Requires JavaScript to be enabled.

---

## Demo Mode

Type `demo` as your API key to explore the full interface with realistic sample data. Useful for getting familiar with the tool before connecting your real account.

---

## Contributing

Found a bug or want to add something? Feel free to open an issue or pull request.

---

## License

GNU General Public License v3.0 — see [LICENSE](LICENSE) for details.
