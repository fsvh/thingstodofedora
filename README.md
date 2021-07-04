# thingstodofedora
Quelques installations et icones

sudo dnf update -y

sudo dnf install https://download1.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm

sudo dnf install https://download1.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm

## USB WIFI driver
sudo dnf -y install git dkms kernel-devel kernel-debug-devel

mkdir ~/src

cd ~/src

git clone https://github.com/morrownr/8812au.git

cd ~/src/8812au

sudo ./install-driver.sh

sudo reboot

## Nvidia drivers
sudo dnf -y install akmod-nvidia

sudo dnf install xorg-x11-drv-nvidia-cuda

## others
sudo dnf -y install gnome-tweak-tool

sudo dnf -y install gnome-extensions-app

sudo dnf groupupdate multimedia --setop="install_weak_deps=False" --exclude=PackageKit-gstreamer-plugin

sudo dnf groupupdate sound-and-video

sudo reboot

## Google chrome

sudo dnf install fedora-workstation-repositories

sudo dnf config-manager --set-enabled google-chrome

sudo dnf install google-chrome-stable

## Install & hack bash to zsh

sudo dnf install zsh

sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"

git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting

git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions

plugins=( [plugins...] zsh-syntax-highlighting zsh-autosuggestions)

exec bash

echo $PATH

Copier le resultat

exec zsh

nano .zshrc

export Path=Copier le resultat

## Flatpak apps

flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo

flatpak install flathub com.spotify.Client

flatpak install flathub org.videolan.VLC

flatpak install flathub org.inkscape.Inkscape

sudo reebot

## Spicetify 

curl -fsSL https://raw.githubusercontent.com/khanhas/spicetify-cli/master/install.sh | sh

spicetify

Ajouter le chemin prefs au fichier .xml

sudo chmod a+wr /var/lib/flatpak/app/com.spotify.Client/x86_64/stable/active/files/extra/share/spotify

sudo chmod a+wr -R /var/lib/flatpak/app/com.spotify.Client/x86_64/stable/active/files/extra/share/spotify/Apps

## Tweaks 

### Gedit dark theme

mkdir -p ~/.local/share/gedit/plugins

cd ~/.local/share/gedit/plugins

git clone https://github.com/fernzi/gedit-darktheme.git

### Dracula Gdit theme

wget https://raw.githubusercontent.com/dracula/gedit/master/dracula.xml

mv dracula.xml $HOME/.local/share/gedit/styles/

### Dracula Gnome terminal

git clone https://github.com/dracula/gnome-terminal

cd gnome-terminal

./install.sh

## Wine & Lutris
```
sudo dnf config-manager --add-repo https://dl.winehq.org/wine-builds/fedora/34/winehq.repo
```
```
sudo dnf install winehq-stable
```
```
sudo dnf install lutris
```
## Plex media server 
```
sudo tee /etc/yum.repos.d/plex.repo<<EOF
[Plexrepo]
name=plexrepo
baseurl=https://downloads.plex.tv/repo/rpm/\$basearch/
enabled=1
gpgkey=https://downloads.plex.tv/plex-keys/PlexSign.key
gpgcheck=1
EOF
```
```
sudo dnf install plexmediaserver -y
```
```
sudo systemctl start plexmediaserver
```
```
sudo systemctl enable plexmediaserver
```
```
systemctl status plexmediaserver
```
