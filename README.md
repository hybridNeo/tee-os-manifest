# tee-os-manifest
## Introduction
TEE-OS is a Google Summer Of Code project under to lowRISC organization. The project aims to develop a Trusted Execution Environment on top of
seL4 microkernel.

##Pre-requisites

sudo add-apt-repository universe
sudo apt-get install -y python-software-properties
sudo apt-get update

sudo apt-get install -y build-essential realpath
sudo apt-get install -y gcc-multilib ccache ncurses-dev
sudo apt-get install -y gcc-arm-linux-gnueabi
sudo apt-get install -y gcc-arm-none-eabi

sudo apt-get install -y python-pip python-jinja2 python-ply  python-tempita
sudo pip install --upgrade pip
sudo pip install pyelftools

sudo apt-get update
sudo apt-get install build-essential realpath
sudo apt-get install gcc-multilib ccache ncurses-dev
sudo add-apt-repository universe
sudo apt-get update
sudo apt-get install gcc-arm-linux-gnueabi
sudo apt-get install gcc-arm-none-eabi

sudo apt-get install qemu-system-arm qemu-system-x86
sudo apt-get install git phablet-tools

##Installation steps

repo init -u https://github.com/hybridNeo/tee-os-manifest -m tee-os.xml
repo sync
make kzm_debug_xml_defconfig
make silentoldconfig
make
make simulate-kzm
