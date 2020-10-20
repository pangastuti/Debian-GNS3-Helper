# Debian-GNS3-Helper
## Purpose
The purpose of the script is to automate GNS3 installation on Debian Linux and Debian-based distros tested in UBUNTU.
## Pre-requisites
Internet Connection, A user with sudo privilidges & Git.

Install With

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
