
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
	sudo pacman -Syyu base-devel xorg xorg-xinit xorg-apps mesa nvidia nvidia-settings gdm plasma konsole gnome git telegram-desktop nano ntfs-3g alsa-utils playerctl brightnessctl

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



## Configure obsidian

##### Hotkey
![hotkey1](drawble/obsidian_hotkey_1.png)
![hotkey1](drawble/obsidian_hotkey_2.png)


##### Style settings
	{
	  "aura@@aura-h1-color": "aura-h1-green",
	  "aura@@cpt-accent": "var(--cpt-orange)",
	  "aura@@aura-rainbow-tags": true,
	  "aura@@aura-rainbow-folders": false,
	  "aura@@aura-h2-color": "aura-h2-orange",
	  "aura@@h3-font": "Rubik",
	  "aura@@aura-h3-color": "aura-h3-blue",
	  "aura@@aura-h4-color": "aura-h4-cyan",
	  "aura@@aura-h5-color": "aura-h5-yellow",
	  "aura@@aura-h6-color": "aura-h6-purple",
	  "aura@@aura-layout-select": "aura-card-layout",
	  "aura@@aura-disable-borders": true,
	  "aura@@aura-card-shadows": false,
	  "aura@@aura-card-layout-actions": true,
	  "aura@@aura-workspace-background": true,
	  "aura@@aura-workspace-background-image-dark": "aura-workspace-background-image-custom",
	  "aura@@aura-file-icons": false,
	  "aura@@aura-folder-icons": false,
	  "aura@@aura-colorful-frame": false,
	  "aura@@aura-colorful-frame-opacity": 1,
	  "aura@@aura-translucent-window": false,
	  "aura@@aura-floating-titlebar": false,
	  "aura@@aura-floating-status-bar": false,
	  "aura@@aura-hide-status-bar": false,
	  "aura@@aura-scrollbar-toggle": true,
	  "aura@@aura-toggle-metadata": false,
	  "aura@@aura-tooltip-toggle": false,
	  "aura@@aura-vault-name-toggle": true
	}


