# (100) - Home Assistant 

## Information

OS Version: Home Assistant OS 17.1
Home Assistant Core: 2026.2.2
ipv4 - 192.168.1.50/24

## Maintenance

Updates are handled through the GUI at ipv4 address. Update OS then Core.

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
curl -fsSL https://raw.githubusercontent.com/filebrowser/get/master/get.sh | bash
```
```
reboot
```

Updates are handled through the GUI for each service at ipv4 address:port

# (300) - Windows Server 2025

I'm not doing anything here.

