# SteamDeckAUR
# Just a setup to download yay through AUR on SteamOS's locked down distro.

sudo steamos-readonly disable
# Necessary to write over file system

sudo pacman-key --init
sudo pacman-key --populate archlinux
sudo pacman-key --populate holo 
# Makes sure keys are updated

sudo pacman -S --needed git base-devel
sudo pacman -S git base-devel
# Makes sure git and base-devel are installed

# YAY installation
git clone https://aur.archlinux.org/yay-bin.git
# installed from binary due to source being finnicky.
cd yay-bin
git checkout 96f90180a3cf72673b1769c23e2c74edb0293a9f
makepkg -si

# If errors are still churning out:
sudo pacman -Sy archlinux-keyring
sudo pacman-key --populate archlinux
sudo pacman-key --refresh keys
sudo pacman -Syu

# Then try again.
