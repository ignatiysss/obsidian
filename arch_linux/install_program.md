sudo nano /etc/pacman.conf

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


sudo pacman -Syyu
sudo pacman -Sy base-devel xorg xorg-xinit xorg-apps messa-libgl nvidia nvidia-settings gdm plasma konsole gnome git telegram-desktop nano ntfs-3g

mkdir /home/ignatiys/1
sudo nano /etc/fstab 
	/dev/sda2                                       /home/ignatiys/1         ntfs-3g         defaults        0 0
mkdir /home/ignatiys/program
cd /home/ignatiys/program

git clone https://aur.archlinux.org/yay.git
git clone https://aur.archlinux.org/intellij-idea-ultimate-edition.git

cd /home/ignatiys/program/yay
	makepkg -si
	cd /home/ignatiys/program
cd /home/ignatiys/program/intellij-idea-ultimate-edition
	makepkg -si
	cd /home/ignatiys/program
