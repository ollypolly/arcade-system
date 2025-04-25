# 🎮 Arcade System (Linux-Based, Dockerized)

This project sets up a minimal Linux-based arcade system using Pegasus Frontend inside a Docker container. It is fully codified, requires no manual installation, and is designed to boot directly into kiosk mode.

---

## 🧱 Structure

```

arcade-system/
├── docker-compose.yml # Orchestrates the system
├── Dockerfile # Builds the frontend container
├── install.sh # Installs dependencies & Pegasus
├── run.sh # Launches Pegasus in kiosk mode
│
├── frontend/pegasus/ # Pegasus theme, metadata, config
├── emulators/pcsx2/ # PS2 emulator container setup
└── roms/ps2/ # Test ROMs (e.g. Street Fighter EX3)

```

---

## 🚀 Quick Start

1. Clone this repo:
   ```bash
   git clone <repo-url>
   cd arcade-system
   ```

````

2. Build and run the system:

   ```bash
   docker compose up --build
   ```

3. Pegasus will launch in fullscreen kiosk mode.

---

## 💾 ROM & Emulator Setup

- Drop ROMs into `roms/ps2/`
- Emulators go in their own containers under `emulators/`
- Pegasus metadata links games to emulator launch commands

---

## 🛠️ TODO (for future versions)

- Add more emulator containers (e.g. MAME, SNES, etc.)
- Add analytics logging & dashboard
- Create companion Windows containers for Xenia, RPCS3, etc.
- Remote update system via Git

---

## 🧠 Philosophy

> "No manual installs. No mystery setup. Just games."

```

Let me know if you want me to tailor it further!
```
````
