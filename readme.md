# Minecraft Server Docker

## Install docker
```
yum install https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm -y   >/dev/null  
yum install libXext libXext.i686  libXp.x86_64 libXp libXp.i686 libXtst libXtst.i686 java nfs-utils.x86_64 gcc  compat-libstdc++-33 compat-glibc libuuid libSM libXrender fontconfig libstdc++ zlib apr ksh curl openldap-clients libXmu libpng12 iftop wget numactl unzip telnet sysstat strace wireshark htop sar lsof -y  | grep Package | grep -v Error
yum install  figlet  iotop nethogs yum-utils -y >/dev/null  



yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo >/dev/null
yum install docker-ce -y  | grep Package 
systemctl start docker >/dev/null
systemctl enable docker >/dev/null
systemctl status docker | grep -i status
```

## Minecraft server

```
mkdir /minecraft/
mkdir /minecraft/data

docker rm --force 
docker run -d -v /minecraft/data:/data     -e TYPE=SPIGOT  -e VERSION=1.19.3 -p 25565:25565     -e EULA=TRUE --name minecraft itzg/minecraft-server

```

Plugin Cross-plateform

https://wiki.geysermc.org/geyser/setup/


```
docker exec -it minecraft rcon-cli
```


https://johackim.com/installer-un-serveur-minecraft-avec-docker

