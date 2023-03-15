# Minecraft Server Docker

## Install docker
```
yum install https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm -y   >/dev/null  
yum install libXext libXext.i686  libXp.x86_64 libXp libXp.i686 libXtst libXtst.i686 java nfs-utils.x86_64 gcc  compat-libstdc++-33 compat-glibc libuuid libSM libXrender fontconfig libstdc++ zlib apr ksh curl openldap-clients libXmu libpng12 iftop wget numactl unzip telnet sysstat strace wireshark htop sar lsof -y  | grep Package | grep -v Error
yum install  figlet  iotop nethogs yum-utils -y >/dev/null  
yum install https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm -y   >/dev/null 
yum install net-tools cifs-utils nfs-common nmap zip telnet php mod_ssl figlet  -y



yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo >/dev/null
yum install docker-ce -y  | grep Package 
systemctl start docker >/dev/null
systemctl enable docker >/dev/null
systemctl status docker | grep -i status
```

# Netdata

```
docker run -d --name=netdata \
  -p 19999:19999 \
  -v netdataconfig:/etc/netdata \
  -v netdatalib:/var/lib/netdata \
  -v netdatacache:/var/cache/netdata \
  -v /etc/passwd:/host/etc/passwd:ro \
  -v /etc/group:/host/etc/group:ro \
  -v /proc:/host/proc:ro \
  -v /sys:/host/sys:ro \
  -v /etc/os-release:/host/etc/os-release:ro \
  --restart unless-stopped \
  --cap-add SYS_PTRACE \
  --security-opt apparmor=unconfined \
  --restart always netdata/netdata
  ```

## Minecraft server

```
mkdir /minecraft/
mkdir /minecraft/data

docker rm --force minecraft
docker run -d -v /minecraft/data:/data --restart always     -e TYPE=SPIGOT  -e VERSION=1.19.3 -p 25565:25565     -e EULA=TRUE --name minecraft itzg/minecraft-server:java8-multiarch

```

Plugin Cross-plateform

https://wiki.geysermc.org/geyser/setup/


```
docker exec -it minecraft rcon-cli
```

/op <player> - Mettre un joueur en admin
/give <player> <item> - Donner un item à un joueur
/gamemode <mode> - Changer le mode de jeu
/tp <player> - Se téléporter vers un joueur
/list - Liste des joueurs connectés



https://johackim.com/installer-un-serveur-minecraft-avec-docker
  
https://www.snel.com/support/debian-vm-in-proxmox-and-networking-setup/
  

