# Debian-GNS3-Helper
## Purpose
The purpose of the script is to automate GNS3 installation on Debian Linux and Debian-based distros tested in UBUNTU.
## Pre-requisites
Internet Connection, A user with sudo privilidges & Git.

Install With

```sudo apt -y install git```

## Usage

Clone the repo into your computer

```https://github.com/tuxsource/Debian-GNS3-Helper.git```

Move to repo directory

```cd Debian-GNS3-Helper```

Install

```sudo ./installer.sh```

## Manual Installation
```
##Automate script for Isntall GNS3 in Debian Based

## Add GNS3 Repository
sudo add-apt-repository ppa:gns3/ppa
## Enable 32 bit support
sudo dpkg --add-architecture i386
## Update package
sudo apt update
## Install GNS3-GUI GNS3-Server Virtualbox QEMU Wireshark Git Ubridge
sudo apt -y install gns3-gui gns3-iou gns3-server virtualbox qemu wireshark libpcap-dev git ubridge
## Change Permission for Wireshark
sudo chmod 777 /usr/bin/dumpcap
## The installation process above will automatically install ubridge. It still seems better to compile ubridge yourself as follows
sudo su
apt -y install libpcap-dev git
cd /usr/local/src
rm -Rf /usr/local/src/ubridge/
git clone git://github.com/GNS3/ubridge.git
cd ubridge
make
make install
cp -p ubridge /usr/bin
setcap cap_net_admin,cap_net_raw=ep /usr//bin/ubridge
## Create Direcotry for GNS3
exit
mkdir -p ~/GNS3/projects
mkdir -p ~/GNS3/images

```
