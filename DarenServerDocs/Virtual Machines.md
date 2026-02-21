# (100) - Home Assistant 

## Information

OS Version: Home Assistant OS 17.1
Home Assistant Core: 2026.2.2
ipv4 - 192.168.1.50/24

## Maintenance

Updates are handled through the GUI at ipv4 address. Update OS then Core.
http://home.darenserver.com

# (200) - Media Server

## Information

OS Version: Debian GNU/Linux 13 (trixie)
ipv4 - 192.168.1.52/24

### Services

Jellyfin v10.11.4 - Port:8096
qBittorrent v5.1.0 - Port:8080
Prowlarr v2.3.0.5236 - Port:9696
Sonarr v4.0.16.2944 - Port:8989
Radarr v6.0.4.10291 - Port:7878
Lidarr v3.1.0.4875 - Port:8686

## Maintenance

Connect via SSH:
```
ssh root@192.168.1.52
```
To update vm:
```
apt update && apt upgrade -y
apt autoremove -y
curl -fsSL https://raw.githubusercontent.com/filebrowser/get/master/get.sh | bash
```
```
reboot
```

Updates are handled through the GUI for each service at ipv4 address:port

# (300) - Windows Server 2025

I'm not doing anything here.


# (400) - debian-docker

### 🛠️ Maintenance Routine

#### Step 1: Update the OS (Debian)

This updates the Linux kernel and security packages.

Bash

```
ssh debian-docker-admin@192.168.1.51
```
```
sudo apt update && sudo apt upgrade -y
```

#### Step 2: Update Immich (Docker)

Since Immich is a fast-moving project, always check their [Release Notes](https://github.com/immich-app/immich/releases) first for "Breaking Changes."

Bash

```
cd /opt/immich
# Pull the latest images defined in your docker-compose.yml
docker compose pull

# Restart the containers with the new images
docker compose up -d

# Clean up old, unused images to save disk space
docker image prune -f
```

#### Step 3: Monthly Database Maintenance

Postgres benefits from an occasional "Vacuum" to keep things snappy.

Bash

```
docker exec -it immich_postgres vacuumdb -U Daren --all --analyze
```

---

### 🚨 Troubleshooting Commands

- **View Logs:** `docker compose logs -f --tail=100`
    
- **Check Container Status:** `docker ps`
    
- **Check Disk Usage:** `df -h`
    

---