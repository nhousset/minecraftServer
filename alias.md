echo "export MON_IP=\$(ifconfig ens18 | awk '/inet / {print \$2}' | cut -d ':' -f2) " >> /root/.bash_profile
echo "PS1=\"FRONTAL - \u@\${MON_IP}:\[\e[01;32m\]\w\[\e[00m\] > \" " >> /root/.bash_profile
echo "RED='\033[031m' " >> /root/.bash_profile
echo "GREEN='\033[032m' " >> /root/.bash_profile
echo "YELLOW='\033[033m' " >> /root/.bash_profile
echo "BLUE='\033[034m' " >> /root/.bash_profile
echo "NC='\033[0m'  " >> /root/.bash_profile
echo "echo -en \"\${BLUE}\" "  >> ~/.bash_profile
echo "echo \" \" "  >> ~/.bash_profile
echo "figlet  \"Serveur frontal\" ">> ~/.bash_profile
echo "echo \" \" "  >> ~/.bash_profile
echo "echo -en \"\${NC}\" "  >> ~/.bash_profile
echo "echo \" \" "  >> ~/.bash_profile

echo "echo \" \" "  >> ~/.bash_profile
echo "alias start='/root/start.sh' "  >> ~/.bash_profile
echo "alias stop='/root/stop.sh' "  >> ~/.bash_profile
echo "alias log='/root/log.sh' "  >> ~/.bash_profile
echo "alias status='/root/status.sh' "  >> ~/.bash_profile
echo "alias admin='/root/admin.sh' "  >> ~/.bash_profile

echo "echo \"start : start serveur minecraft \" "  >> ~/.bash_profile
echo "echo \"stop : stop serveur minecraft \" "  >> ~/.bash_profile
echo "echo \"status : status serveur minecraft \" "  >> ~/.bash_profile
echo "echo \"log : journal serveur minecraft \" "  >> ~/.bash_profile
echo "echo \"admin : console /op serveur minecraft \" "  >> ~/.bash_profile
