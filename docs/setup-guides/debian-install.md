# Debian Installation

I installed a lightweight debian 12 to the server for optimal idel processing.

## Server Hardware

- 10+ year old CPU
- 10+ year old GPU
- 24gb RAM
- HDD (an upgrade to SSD would be ideal)

## Install Steps

1. Installed Debian 12 (Bookworm)
2. Selected only SSH Sever and Standard System Utilities
3. Initial system update
```bash
sudo apt update
sudo apt upgrade -y
```
4. Set up SSH remote access
```bash
# generate key
ssh-keygen

# link to server
ssh username@server-ip
```
5. Configure static IP on router
6. Configure UFW firewall
```bash
# install
apt install ufw

# allow SSH service
ufw allow 22/tcp

# enable
ufw enable

# verify 
ufw status
```
7. Update packages
