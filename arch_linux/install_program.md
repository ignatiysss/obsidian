
## Edit pacman config

	sudo nano /etc/pacman.conf
##### change this
	 ParallelDownloads = 5
	[core-testing]
	Include = /etc/pacman.d/mirrorlist
	[core]
	Include = /etc/pacman.d/mirrorlist
	[extra-testing]
	Include = /etc/pacman.d/mirrorlist
	[extra]
	Include = /etc/pacman.d/mirrorlist
	[multilib]  
	Include = /etc/pacman.d/mirrorlist

## Install program from pacman 
	sudo pacman -Syyu base-devel xorg xorg-xinit xorg-apps messa-libgl nvidia nvidia-settings gdm plasma konsole gnome git telegram-desktop nano ntfs-3g alsa-utils playerctl brightnessctl

## Create directory for programs 
	mkdir /home/ignatiys/program

## Install program from AUR
	cd program/
	git clone https://aur.archlinux.org/yay.git
	cd yay/
	makepkg -si
	cd /home/ignatiys/program
	git clone https://aur.archlinux.org/libinput-gestures.git
	cd libinput-gestures
	makepkg -si

