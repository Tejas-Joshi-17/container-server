
1. Server login

```sh
ssh root@localhost -p 2222
```

2. Welcome Poster

```sh
cat << 'EOF' > /etc/profile.d/welcome.sh
#!/bin/bash
clear

# Define Colors
RED='\033[1;31m'
GREEN='\033[1;32m'
BLUE='\033[1;34m'
YELLOW='\033[1;33m'
CYAN='\033[1;36m'
RESET='\033[0m'

echo -e "${CYAN}=============================================${RESET}"
echo -e "${GREEN}🚀 Welcome to Tejas' Ubuntu Server 🚀${RESET}"
echo -e "${CYAN}=============================================${RESET}"

echo -e "${YELLOW}Hostname      : ${RESET}$(hostname)"
echo -e "${YELLOW}OS Version    : ${RESET}$(lsb_release -d | cut -f2)"
echo -e "${YELLOW}Kernel        : ${RESET}$(uname -r)"
echo -e "${YELLOW}Uptime        : ${RESET}$(uptime -p)"

echo -e "${YELLOW}Memory Usage:${RESET}"
free -h

echo -e "${YELLOW}Disk Usage:${RESET}"
df -h /

echo -e "${CYAN}=============================================${RESET}"
EOF

chmod +x /etc/profile.d/welcome.sh

```