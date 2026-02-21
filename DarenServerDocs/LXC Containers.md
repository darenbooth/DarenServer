## 🌐 (101) - DDNS Updater

### ℹ️ Information

- **OS:** Ubuntu 24.04.3 LTS (Go `1.25.7`)
    
- **IPv4:** `192.168.1.25`
    

### 🛠️ Maintenance

1. **Stop Service:** `screen -r game` → `Ctrl+C` → `exit`.
    
2. **Update:**
    
    Bash
    
    ```
    apt update && apt upgrade -y && apt autoremove -y
    go install github.com/qdm12/ddns-updater/cmd/ddns-updater@latest
    ```
    
3. **Start:** `screen -S game` → `cd /etc/ddns-updater` → `./ddns-updater`.
    
4. **Detach:** `Ctrl+A` then `D`.
    

---

## 🛡️ (102) - Nginx Proxy Manager

### ℹ️ Information

- **OS:** Debian 12 (Bookworm)
    
- **IPv4:** `192.168.1.26`
    

### 🛠️ Maintenance

Bash

```
apt update && apt upgrade -y && apt autoremove -y
cd /opt/nginx-proxy-manager
docker compose pull && docker compose up -d
```

---

## 🌍 (103) - Nginx Web Server

### ℹ️ Information

- **OS:** Debian 12 (Bookworm)
    
- **IPv4:** `192.168.1.27`
    
- **Version Check:** `curl -I http://192.168.1.27`
    

### 🛠️ Maintenance

- **OS Update:** `apt update && apt upgrade -y`
    
- **Update Website Content:**
    
    Bash
    
    ```
    rm -rf /var/www/html/
    cd /var/www
    git clone https://github.com/darenbooth/DarenServer.git
    mv DarenServer html
    ```
    

---

## 📂 (104) - File Browser

### ℹ️ Information

- **OS:** Ubuntu 24.04.3 LTS
    
- **IPv4:** `192.168.1.28`
    

### 🛠️ Maintenance

Bash

```
apt update && apt upgrade -y && apt autoremove -y
curl -fsSL https://raw.githubusercontent.com/filebrowser/get/master/get.sh | bash
reboot
```

---

## ⚠️ (105) - Immich (LXC - DEPRECATED)

### ℹ️ Information

- **Status:** **Legacy Container** (Migrated to VM 400)
    
- **IPv4:** `192.168.1.29`
    

### 🛠️ Maintenance

_Keep offline unless needed for data verification._

Bash

```
cd /mnt/immich-data
docker compose pull && docker compose up -d
docker image prune -f
```

---

## 🚀 (106) - Tailscale

### ℹ️ Information

- **OS:** Ubuntu 24.04.3 LTS
    
- **IPv4:** `192.168.1.32`
    

### 🛠️ Maintenance

- **Update:** `apt update && apt upgrade -y`
    
- **Check Version:** `tailscale --version`
    

---

## 🧙‍♂️ (107) - Wizarr

### ℹ️ Information

- **OS:** Debian 12 (Bookworm)
    
- **IPv4:** `192.168.1.33`
    
- **Purpose:** Media Invitation Management
    

### 🛠️ Maintenance

Bash

```
# Update System
apt update && apt upgrade -y
apt autoremove -y

# Update Wizarr (using the built-in update script)
update
```

---

## 📂 (108) - SFTPGo

### ℹ️ Information

- **OS:** Debian 12 (Bookworm)
    
- **IPv4:** `192.168.1.34`
    
- **Purpose:** SFTP/HTTP/WebDAV File Transfer
    

### 🛠️ Maintenance

Bash

```
# Update System
apt update && apt upgrade -y
apt autoremove -y

# Update SFTPGo (using the built-in update script)
update
```
---

## 🎮 (109) - Paper-MC (Minecraft)

### ℹ️ Information

- **OS:** Ubuntu 24.04.3 LTS
    
- **IPv4:** `192.168.1.35`
    
- **Service User:** `papermc`
    

### 🛠️ Maintenance

1. **Stop:** `screen -r game` → type `stop` → `exit`.
    
2. **OS Update (root):** `apt update && apt upgrade -y`
    
3. **App Update (papermc user):**
    
    - Download latest `.jar` from [papermc.io](https://papermc.io/downloads/paper).
        
    - Replace old `.jar` in `/home/papermc/minecraft`.
        
    - Update `start.sh` with new filename.
        
    - Update Plugins (`plugins/` folder):
	    EssentialsX - https://essentialsx.net/downloads
		GriefPrevention - https://www.spigotmc.org/resources/griefprevention.1884/
		LuckPerms - https://luckperms.net/download
4. **Start:** `screen -S game` → `./start.sh`.
    

---

## 🥚 (110) - Palworld Server

### ℹ️ Information

- **OS:** Ubuntu 24.04.3 LTS
    
- **IPv4:** `192.168.1.36`
    
- **Service User:** `palworld`
    

### 🛠️ Maintenance

1. **Shutdown (In-Game):** `/AdminPassword {pw}` → `/Save` → `/DoExit`.
    
2. **Update Container (root):** `apt update && apt upgrade -y`.
    
3. **Update Server (palworld user):**
    
    Bash
    
    ```
    /home/palworld/.steam/steam/steamcmd/steamcmd.sh +force_install_dir /home/palworld/PalworldServer +login anonymous +app_update 2394010 validate +quit
    ```
    
4. **Start:** `screen -S game` → `cd PalworldServer` → `./PalServer.sh -publiclobby`.
    

---