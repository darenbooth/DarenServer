## 🏠 (100) - Home Assistant (HAOS)

### ℹ️ Information

- **Type:** Home Assistant OS (Managed VM)
    
- **IPv4:** `192.168.1.50`
    
- **Web UI:** [home.darenserver.com](http://home.darenserver.com)
    
- **OS Version:** 17.1
    
- **Core Version:** 2026.2.2
    

### 🛠️ Maintenance

- **Updates:** Managed via **Settings > System > Updates**.
    
- **Order:** Update **Operating System** first → Reboot → Update **Core**.
    
- **Backups:** Always verify a "Full Backup" exists before updating the OS.
    

---

## 🎬 (200) - Media Server

### ℹ️ Information

- **Type:** Debian VM (Docker-based)
    
- **IPv4:** `192.168.1.52`
    
- **SSH:** `ssh root@192.168.1.52`
    

### 🛠️ Maintenance

Run these commands monthly to keep the OS and the Filebrowser binary updated.

Bash

```
# Update System
apt update && apt upgrade -y
apt autoremove -y

# Update Filebrowser Binary
curl -fsSL https://raw.githubusercontent.com/filebrowser/get/master/get.sh | bash

# Reboot to apply kernel updates
reboot
```

### 📦 Services & GUI Access

_Services on this VM run on specific ports. Update these via their respective "Check for Update" buttons in their Web UIs._

| Service         | Port   | Description           |
| --------------- | ------ | --------------------- |
| **Jellyfin**    | `8096` | Media Streaming       |
| **Filebrowser** | `8081` | Cloud File Management |
| **qBittorrent** | `8080` | Torrent Client        |
| **Prowlarr**    | `9696` | Media Indexer         |
| **Radarr**      | `7878` | Movies                |
| **Sonarr**      | `8989` | Shows                 |
| **Lidarr**      | `8686` | Music                 |

## 🖥️ (300) - Windows Server

### ℹ️ Information

- **Type:** Windows Server (VM)
    
- **IPv4:** `[TBD]`
    
- **RDP:** `[TBD]`
    
- **Purpose:** `[TBD - e.g., Active Directory, Game Server, BlueIris]`
    

### 🛠️ Maintenance

- **Windows Update:** Settings > Update & Security > Windows Update.
    
- **VirtIO Drivers:** Periodically check for VirtIO driver updates in Proxmox to ensure disk/network stability.
    
- **Disk Cleanup:** Run `Optimize Drives` (defrag) monthly. Since it's a VM, Windows will issue a `TRIM` command to the Proxmox storage, which helps reclaim unused space on the host.
    

---

## 🐳 (400) - Debian-Docker (Immich)

### ℹ️ Information

- **Type:** Debian 13 VM (Docker)
    
- **IPv4:** `192.168.1.51`
    
- **SSH:** `ssh debian-docker-admin@192.168.1.51`
    
- **Path:** `/opt/immich`
    

### 🛠️ Maintenance

Bash

```
# 1. Update OS
sudo apt update && sudo apt upgrade -y

# 2. Update Immich Stack
cd /opt/immich
docker compose pull && docker compose up -d
docker image prune -f

# 3. Database Health
docker exec -it immich_postgres vacuumdb -U Daren --all --analyze
```

---