# (101) - ddns-updater v2.9

## Information

OS - Ubuntu 24.04.3 LTS
Go Version - go1.25.7 linux/amd64
ipv4 - 192.168.1.25/24

## Maintenance

To Update:
```
screen -r game
```
Stop the service: "Ctrl + C"
```
exit
```
Then update.
```
apt update && apt upgrade -y
apt autoremove -y
go install github.com/qdm12/ddns-updater/cmd/ddns-updater@latest
```

To Start:

This needs to be started in a screen when the container restarts.
```
screen -S game
```
```
cd /etc/ddns-updater
./ddns-updater
```

Detach from screen "Ctrl + A" then "D"
# (102) - Nginx Proxy Manager v2.14.0

## Information

OS - Debian GNU/Linux 12 (bookworm)
ipv4 - 192.168.1.26/24

## Maintenance

To update:
```
apt update && apt upgrade -y
apt autoremove -y
cd /opt/nginx-proxy-manager
docker compose pull
docker compose up -d
```

# (103) - Nginx Web Server v1.22.1

## Information

OS - Debian GNU/Linux 12 (bookworm)
ipv4 - 192.168.1.27/24

## Maintenance

To Update:
```
apt update && apt upgrade -y
apt autoremove -y
```

To update website:
```
rm -rf /var/www/html/
cd /var/www
git clone https://github.com/darenbooth/DarenServer.git
mv DarenServer html
cd
```

To see version:
```
curl -I http://192.168.1.27
```
# (104) - File Browser v2.59.0

## Information

OS Version: Ubuntu 24.04.3 LTS
ipv4 - 192.168.1.28/24

## Maintenance

To update version:
```
apt update && apt upgrade -y
apt autoremove -y
curl -fsSL https://raw.githubusercontent.com/filebrowser/get/master/get.sh | bash
```
```
reboot
```

# (105) - Immich v2.5.6

## Information

OS - Debian GNU/Linux 12 (bookworm)
ipv4 - 192.168.1.29/24

## Maintenance

To update Immich version:
```
apt update && apt upgrade -y
apt autoremove -y
cd /mnt/immich-data
docker compose pull && docker compose up -d
docker image prune
cd
```

# (106) - Tailscale v1.94.2

## Information

OS - Ubuntu 24.04.3 LTS
ipv4 - 192.168.1.32/24

## Maintenance

To update:
```
apt update && apt upgrade -y
apt autoremove -y
```

To check version:
```
tailscale --version
```
# (107) - Wizarr v2025.12.0

## Information

OS - Debian GNU/Linux 12 (bookworm)
ipv4 - 192.168.1.33/24

## Maintenance

To update:
```
apt update && apt upgrade -y
apt autoremove -y
update
```

# (108) - SFTPGo v2.7.0

## Information

OS - Debian GNU/Linux 12 (bookworm)
ipv4 - 192.168.1.34/24

## Maintenance

To update:
```
apt update && apt upgrade -y
apt autoremove -y
update
```

# (109) - Paper-MC v1.21.11-116

## Information

OS - Ubuntu 24.04.3 LTS
ipv4 - 192.168.1.35/24

## Maintenance

To update:

Stop server:
```
screen -r game
```
```
stop
```
```
exit
```

update container:
```
su root
```
```
cd
apt update && apt upgrade -y
apt autoremove -y
```

update paper server:
navigate to https://papermc.io/downloads/paper
right click latest version and copy link
```
su papermc
```
```
cd
cd minecraft
```
wget  paste url link
```
ls
```
rm "old_paper.jar"
```
nano start.sh
```
replace old paper.jar filename with new paper.jar filename.
"Ctrl + X", "Y", "ENTER" to save

update essentials:
navigate to https://essentialsx.net/downloads
copy link of latest stable release of EssentialsX
```
cd plugins
ls
```
wget paste url link
rm "old_EssentialsX.jar"

update grief prevention:
navigate to https://www.spigotmc.org/resources/griefprevention.1884/
click downlod via external sight
copy link of latest stable release
wget paste url link
rm "old_greif_prevention.jar"

update luck perms:
navigate to https://luckperms.net/download
copy link of latest stable release for Paper
wget paste url link
rm "old_luck_perms.jar"

To start server:
-run as papermc user-
```
screen -S game
```
```
cd minecraft
./start.sh
```

# (110) - Palworld v0.7.1.87654

## Information

OS - Ubuntu 24.04.3 LTS
ipv4 - 192.168.1.36/24

## Maintenance

### How to shutdown server:

In game:
/AdminPassword {password}
/Save

For Immediate shutdown:
/DoExit

For timed shutdown:
/Shutdown {seconds} {"message"}

### To update server:
```
screen -r game
```
```
exit
```
```
su root
```
```
cd
apt update && apt upgrade -y
apt autoremove -y
```
```
su palworld
```
```
cd
/home/palworld/.steam/steam/steamcmd/steamcmd.sh +force_install_dir /home/palworld/PalworldServer +login anonymous +app_update 2394010 validate +quit
```

### To start server:
```
cd
screen -S game
```
```
cd PalworldServer
./PalServer.sh -publiclobby
```

