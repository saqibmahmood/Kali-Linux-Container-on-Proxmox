# Kali-Linux-Container-on-Proxmox

1. Introduction
---------------------------------------------------
	- LXC
	- Proxmox

2. Download needed files and Create CT
---------------------------------------------------
	- Kali rootfs.tar.xz (https://uk.lxd.images.canonical.com/images/kali/current/amd64/default/20220619_18:09/rootfs.tar.xz)
	- Putty (optional) (https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html)

3. Create CT
---------------------------------------------------

4. Install base packages:
---------------------------------------------------
apt-get -y install wget inetutils-tools iputils-ping ssh man nano

5. Install ZSH Kali Theme
---------------------------------------------------
sudo apt-get -y install kali-defaults zsh zsh-syntax-highlighting zsh-autosuggestions

6. Create a traditional user:group (kali:kali)
---------------------------------------------------
adduser kali

7. Add kali user to SUDO group
---------------------------------------------------
usermod -aG sudo kali
id kali

8. Enable SSH Server and Login Using "kali" user (via Putty)
---------------------------------------------------
nano /etc/ssh/sshd_config
PermitRootLogin yes (optional)

systemctl enable ssh && systemctl start ssh
systemctl status ssh
sudo
11. Testing with SSH
---------------------------------------------------

9. Setting up RDP with Kali Base XFCE
---------------------------------------------------
apt-get update
apt-get dist-upgrade -y
apt-get install -y kali-desktop-xfce xorg xrdp firefox-esr
apt-get purge network-manager

7. Update and Upgrade the Kali Distro: 
---------------------------------------------------
sudo apt-get update && sudo apt-get -y dist-upgrade

sudo reboot now (optional)

sudo apt-cache search kali-linux

sudo apt-get -y install kali-linux-default

sudo apt-get purge network-manager

journ

11. Testing with RDP
---------------------------------------------------
systemctl status xrdp
systemctl enable xrdp && systemctl start xrdp
systemctl status xrdp

10. TightVNCServer Configuration
---------------------------------------------------
sudo apt-get install tightvncserver
tightvncserver -geometry 1280x1024 -depth 16 -pixelformat rgb565/rgb888
nano /etc/tightvncserver.conf

12. Testing with VNC
---------------------------------------------------
---- client connect using "[ip address]:1"
---- to kill the session use "vncserver -kill :1"
