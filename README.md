# fika-spt-server-docker (CyberByteCraft Fork)

🐳 SPT + Fika Server in Docker with **Pterodactyl/Pelican Panel Support** 🐳

**🌐 Language / Sprache:** [English](#english) | [Deutsch](#deutsch)

---

<a name="english"></a>
# 🇬🇧 English

> [!NOTE]
> **This is a fork of [zhliau/fika-spt-server-docker](https://github.com/zhliau/fika-spt-server-docker)**
> 
> This project is based on the excellent work of **[@zhliau](https://github.com/zhliau)** and extends it with native Pterodactyl/Pelican Panel support.

---

## 🆕 What's New in This Fork?

| Feature | Original | This Fork |
|---------|----------|-----------|
| Pterodactyl/Pelican Support | ❌ | ✅ |
| Importable Egg File | ❌ | ✅ |
| `/home/container` Support | ❌ | ✅ |
| GitHub Actions for Panel Images | ❌ | ✅ |

---

## 🎮 Pterodactyl / Pelican Panel

### Quick Start

1. **Import Egg**
   - Download [`egg-eft-spt-server.json`](./egg-eft-spt-server.json)
   - Open Panel → **Admin** → **Nests** → **Import Egg**
   - Upload file and select nest

2. **Create Server**
   - **Servers** → **Create New**
   - Select "EFT SPT Server (Fika)" egg
   - Assign port **6969**
   - Start server

> [!TIP]
> First boot takes a few minutes as SPT files are downloaded.

### Docker Images

| Tag | Description |
|-----|-------------|
| `ghcr.io/cyberbytecraft/fika-spt-server-docker:pterodactyl` | **Recommended** for Panel |
| `ghcr.io/cyberbytecraft/fika-spt-server-docker:latest` | Standard Docker-Compose |

---

## 🐳 Standard Docker (without Panel)

For classic Docker/Docker-Compose usage, see the original documentation:
**[zhliau/fika-spt-server-docker](https://github.com/zhliau/fika-spt-server-docker)**

### Quick Start with Docker-Compose

```yaml
services:
  fika-server:
    image: ghcr.io/cyberbytecraft/fika-spt-server-docker:latest
    ports:
      - 6969:6969
    environment:
      - INSTALL_FIKA=true
      - LISTEN_ALL_NETWORKS=true
    volumes:
      - ./server:/opt/server
```

---

## 🌐 Environment Variables

| Variable | Default | Description |
|----------|---------|-------------|
| `INSTALL_FIKA` | `true` | Install Fika Multiplayer Mod |
| `AUTO_UPDATE_SPT` | `true` | Auto-update SPT |
| `AUTO_UPDATE_FIKA` | `true` | Auto-update Fika |
| `LISTEN_ALL_NETWORKS` | `true` | Listen on all networks (important for Docker) |
| `ENABLE_PROFILE_BACKUP` | `true` | Enable profile backups |
| `TZ` | UTC | Timezone (e.g. `Europe/Berlin`) |
| `FORCE_SPT_VERSION` | - | Force SPT version (e.g. `4.0.1-40087-1eacf0f`) |
| `FIKA_VERSION` | - | Override Fika version |
| `NUM_HEADLESS_PROFILES` | - | Number of headless profiles |
| `INSTALL_OTHER_MODS` | `false` | Auto-install additional mods |
| `MOD_URLS_TO_DOWNLOAD` | - | URLs for additional mods |

---

## 🙏 Credits

**This project would not be possible without:**

| Project | Author | Description |
|---------|--------|-------------|
| [fika-spt-server-docker](https://github.com/zhliau/fika-spt-server-docker) | **[@zhliau](https://github.com/zhliau)** | Original Docker Image & Entrypoint Logic |
| [SPT (Single Player Tarkov)](https://www.sp-tarkov.com/) | SPT Team | SPT Server & Mods |
| [Fika](https://github.com/project-fika) | Project Fika Team | Multiplayer Mod for SPT |

> Special thanks to **[@zhliau](https://github.com/zhliau)** for the excellent foundation of this project!

---

## ⚠️ Notes

> [!WARNING]
> With SPT 4.0.0 and the switch to C#, older versions are no longer supported.
> For SPT 3.11.4 (LTS), use the original image: `zhliau/fika-spt-server-docker:3.11.4`

> [!WARNING]
> ARM64 (Raspberry Pi) is currently not supported.
> See [Issue #33](https://github.com/zhliau/fika-spt-server-docker/issues/33)

---
---

<a name="deutsch"></a>
# 🇩🇪 Deutsch

> [!NOTE]
> **Dies ist ein Fork von [zhliau/fika-spt-server-docker](https://github.com/zhliau/fika-spt-server-docker)**
> 
> Dieses Projekt basiert auf der exzellenten Arbeit von **[@zhliau](https://github.com/zhliau)** und erweitert es um native Unterstützung für Pterodactyl/Pelican Panel.

---

## 🆕 Was ist neu in diesem Fork?

| Feature | Original | Dieser Fork |
|---------|----------|-------------|
| Pterodactyl/Pelican Support | ❌ | ✅ |
| Importierbare Egg-Datei | ❌ | ✅ |
| `/home/container` Support | ❌ | ✅ |
| GitHub Actions für Panel-Images | ❌ | ✅ |

---

## 🎮 Pterodactyl / Pelican Panel

### Schnellstart

1. **Egg importieren**
   - Lade [`egg-eft-spt-server.json`](./egg-eft-spt-server.json) herunter
   - Panel öffnen → **Admin** → **Nests** → **Import Egg**
   - Datei hochladen und Nest auswählen

2. **Server erstellen**
   - **Servers** → **Create New**
   - Egg "EFT SPT Server (Fika)" auswählen
   - Port **6969** zuweisen
   - Server starten

> [!TIP]
> Der erste Start dauert einige Minuten, da SPT-Dateien heruntergeladen werden.

### Docker Images

| Tag | Beschreibung |
|-----|--------------|
| `ghcr.io/cyberbytecraft/fika-spt-server-docker:pterodactyl` | **Empfohlen** für Panel |
| `ghcr.io/cyberbytecraft/fika-spt-server-docker:latest` | Standard Docker-Compose |

---

## 🐳 Standard Docker (ohne Panel)

Für die klassische Docker/Docker-Compose Nutzung, siehe die originale Dokumentation:
**[zhliau/fika-spt-server-docker](https://github.com/zhliau/fika-spt-server-docker)**

### Schnellstart mit Docker-Compose

```yaml
services:
  fika-server:
    image: ghcr.io/cyberbytecraft/fika-spt-server-docker:latest
    ports:
      - 6969:6969
    environment:
      - INSTALL_FIKA=true
      - LISTEN_ALL_NETWORKS=true
    volumes:
      - ./server:/opt/server
```

---

## 🌐 Umgebungsvariablen

| Variable | Standard | Beschreibung |
|----------|----------|--------------|
| `INSTALL_FIKA` | `true` | Fika Multiplayer Mod installieren |
| `AUTO_UPDATE_SPT` | `true` | SPT automatisch aktualisieren |
| `AUTO_UPDATE_FIKA` | `true` | Fika automatisch aktualisieren |
| `LISTEN_ALL_NETWORKS` | `true` | Auf allen Netzwerken lauschen (wichtig für Docker) |
| `ENABLE_PROFILE_BACKUP` | `true` | Profil-Backups aktivieren |
| `TZ` | UTC | Zeitzone (z.B. `Europe/Berlin`) |
| `FORCE_SPT_VERSION` | - | SPT Version erzwingen (z.B. `4.0.1-40087-1eacf0f`) |
| `FIKA_VERSION` | - | Fika Version überschreiben |
| `NUM_HEADLESS_PROFILES` | - | Anzahl Headless-Profile |
| `INSTALL_OTHER_MODS` | `false` | Zusätzliche Mods automatisch installieren |
| `MOD_URLS_TO_DOWNLOAD` | - | URLs für zusätzliche Mods |

---

## 🙏 Credits

**Dieses Projekt wäre nicht möglich ohne:**

| Projekt | Autor | Beschreibung |
|---------|-------|--------------|
| [fika-spt-server-docker](https://github.com/zhliau/fika-spt-server-docker) | **[@zhliau](https://github.com/zhliau)** | Original Docker Image & Entrypoint-Logik |
| [SPT (Single Player Tarkov)](https://www.sp-tarkov.com/) | SPT Team | SPT Server & Mods |
| [Fika](https://github.com/project-fika) | Project Fika Team | Multiplayer Mod für SPT |

> Ein besonderer Dank geht an **[@zhliau](https://github.com/zhliau)** für die hervorragende Grundlage dieses Projekts!

---

## ⚠️ Hinweise

> [!WARNING]
> Mit SPT 4.0.0 und der Umstellung auf C# werden ältere Versionen nicht mehr unterstützt.
> Für SPT 3.11.4 (LTS), nutze das Original-Image: `zhliau/fika-spt-server-docker:3.11.4`

> [!WARNING]
> ARM64 (Raspberry Pi) wird derzeit nicht unterstützt.
> Siehe [Issue #33](https://github.com/zhliau/fika-spt-server-docker/issues/33)

---

## 📄 License / Lizenz

This project is licensed under the same license as the original project.
See [LICENSE](./LICENSE) for details.

Dieses Projekt steht unter derselben Lizenz wie das Original-Projekt.
Siehe [LICENSE](./LICENSE) für Details.
