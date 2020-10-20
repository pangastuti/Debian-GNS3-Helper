# Debian-GNS3-Helper
## Purpose
The purpose of the script is to automate GNS3 installation on Debian Linux and Debian-based distros tested in UBUNTU.
## Pre-requisites
Internet Connection, A user with sudo privilidges & Git.

Install Git with

``sudo apt -y install git``

## Usage

Clone the repo into your computer

``https://github.com/tuxsource/Debian-GNS3-Helper.git``

Move to repo directory

``cd Debian-GNS3-Helper``

Install

``sudo ./installer.sh``

## Manual Installation
### Add GNS3 Repository
``sudo add-apt-repository ppa:gns3/ppa``
### Add i386 Architecture
``sudo dpkg --add-architecture i386``
### Update Repo
```sudo apt update```
### Install GNS3 & Depedencies
```sudo apt -y install gns3-gui gns3-iou gns3-server virtualbox qemu wireshark libpcap-dev git ubridge```
### Change Permission for Wireshark
```sudo chmod 777 /usr/bin/dumpcap```
### The installation process above will automatically install ubridge. Ubridge from apt seems unstable. It still seems better to compile ubridge yourself as follows
```
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
```
The last three (3) lines will overwrite ubridge from apt install Next, as a **normal user**, prepare a directory.
```
mkdir -p ~/GNS3/projects
mkdir -p ~/GNS3/images
```
Inspired from https://github.com/SirToffski/Arch-GNS3-Helper
## Reference
* https://lms.onnocenter.or.id/wiki/index.php/GNS3:_Instalasi

* http://www.unixmen.com/install-gns3-graphical-network-simulator-ubuntu-13-04/

* https://community.gns3.com/people/rednectar/blog/2014/10/22/installing-gns3v1-on-linux
