# SteamDeckAUR
## Just a setup to download yay through AUR on SteamOS's locked down distro.
> Necessary to write over file system
 
sudo steamos-readonly disable

> Makes sure keys are updated
 
sudo pacman-key --init  
sudo pacman-key --populate archlinux  
sudo pacman-key --populate holo   

> Makes sure git and base-devel are installed

sudo pacman -S --needed git base-devel  
sudo pacman -S git base-devel  


# YAY installation
> installed from binary due to source being finnicky.

git clone https://aur.archlinux.org/yay-bin.git  
cd yay-bin  
git checkout 96f90180a3cf72673b1769c23e2c74edb0293a9f  
makepkg -si  

> If errors are still churning out:

sudo pacman -Sy archlinux-keyring  
sudo pacman-key --populate archlinux  
sudo pacman-key --refresh keys  
sudo pacman -Syu  

> Then try again.
