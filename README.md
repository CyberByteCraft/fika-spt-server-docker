# fika-spt-server-docker (CyberByteCraft Fork)

🐳 SPT + Fika Server in Docker mit **Pterodactyl/Pelican Panel Support** 🐳

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

## 📦 Features

- ✅ **Pterodactyl/Pelican Panel Ready** - Importierbare Egg-Datei
- ✅ **Automatische Updates** - SPT & Fika werden automatisch aktualisiert
- ✅ **Profil-Backups** - Automatische tägliche Backups
- ✅ **Mod-Installation** - Zusätzliche Mods über URLs installieren
- ✅ **Multi-Image Support** - Standard & Pterodactyl Images

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

## 📄 Lizenz

Dieses Projekt steht unter derselben Lizenz wie das Original-Projekt.
Siehe [LICENSE](./LICENSE) für Details.
