<div align="center">

<img src="https://raw.githubusercontent.com/TaggedHQ/apple/main/Taggd/Assets.xcassets/Taggd-Colored.imageset/Taggd-Colored.svg" width="96" height="96" alt="Tagged logo">

# Tagged

**Own your time. Own your data.**

A fast, privacy‑friendly, self‑hosted time tracker — a single Go server and native
apps for iPhone, iPad, Mac, and Windows. Track your work with flexible tags instead
of rigid projects, and keep every record on your own machine.

`🛠️ vibe coded` &nbsp;·&nbsp; `🔒 self‑hosted` &nbsp;·&nbsp; `🏷️ tag‑based` &nbsp;·&nbsp; `🎨 dark theme` &nbsp;·&nbsp; `🚫 no analytics`

</div>

---

## The repos

| Repo | What it is | Built with |
| --- | --- | --- |
| **[server](https://github.com/TaggedHQ/server)** | Self‑hosted time‑tracker server — one binary, SQLite or Postgres, OAuth · 2FA · passkeys | Go |
| **[apple](https://github.com/TaggedHQ/apple)** | Native iPhone, iPad & Mac apps — widgets, Live Activity, Control Center, Shortcuts | SwiftUI + Sparkle |
| **[windows](https://github.com/TaggedHQ/windows)** | Native Windows system‑tray app | WPF · .NET 8 + Velopack |

## How it fits together

**Tagged Server** is the backend — it stores your entries and tags, exposes an
API, and serves its own web UI. The **apple** and **windows** apps are native
clients that sync to it with a URL and an API token.

The sync protocol is built on, and stays fully interoperable with,
**[TimeTagger](https://github.com/almarklein/timetagger)** — the open‑source
tracker Tagged is based on — so the apps work equally well against a Tagged Server
or an existing TimeTagger install.

```
        ┌──────────────┐        ┌──────────────┐
        │  Apple apps  │        │ Windows app  │
        │ iOS · macOS  │        │    (tray)    │
        └──────┬───────┘        └──────┬───────┘
               │      URL + API token  │
               └───────────┬───────────┘
                           ▼
                  ┌──────────────────┐
                  │  Tagged Server   │  ← your machine, your data
                  │  Go · SQLite/PG  │
                  └──────────────────┘
```

## Why Tagged

- 🔒 **Self‑hosted & private.** No cloud, no analytics, no third‑party services.
  Your data lives on your device and your server.
- 🏷️ **Tags, not projects.** Categorize time with lightweight tags and watch the
  dashboard light up.
- 🖥️ **Native everywhere.** Menu‑bar and tray apps, Home Screen widgets, Live
  Activity, Control Center, and Siri Shortcuts — all sharing one dark theme.
- 🔄 **Interoperable.** Fully compatible with the TimeTagger API.
- ⬆️ **Auto‑updating.** Sparkle on macOS, Velopack on Windows, GHCR images for the
  server.

## Getting started

Spin up the server, then point an app at it:

```bash
# 1. Run the server (Docker)
docker run -d --name tagged -p 8080:8080 -v tagged:/data ghcr.io/taggedhq/server:latest

# 2. Open http://localhost:8080/, create your account, and grab an API token
# 3. In any Tagged app: Settings → Server URL + API token → Test Connection
```

Full instructions live in each repo's README.

---

<div align="center">
<sub>Made with too much coffee and not enough planning. ☕</sub>
</div>
