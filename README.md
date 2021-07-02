# thingstodofedora
Quelques installations et icons

sudo dnf update -y

sudo dnf install https://download1.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm

sudo dnf install https://download1.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm

##USB WIFI driver
sudo dnf -y install git dkms kernel-devel kernel-debug-devel

mkdir ~/src

cd ~/src

git clone https://github.com/morrownr/8812au.git

cd ~/src/8812au

sudo ./install-driver.sh

sudo reboot

##Nvidia drivers
sudo dnf -y install akmod-nvidia

sudo dnf install xorg-x11-drv-nvidia-cuda

##Tweaks & others
sudo dnf -y install gnome-tweak-tool

sudo dnf -y install gnome-extensions-app

sudo dnf groupupdate multimedia --setop="install_weak_deps=False" --exclude=PackageKit-gstreamer-plugin

sudo dnf groupupdate sound-and-video

##Hack bash to zsh
exec bash

echo $PATH

Copier le resultat

exec zsh

nano .zshrc

export Path=Copier le resultat
