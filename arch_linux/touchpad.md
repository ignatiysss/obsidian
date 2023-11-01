	sudo pacman -S  alsamixer playerctl brightnessctl
## Install libinput
	cd program 
	git clone https://aur.archlinux.org/libinput-gestures.git
	cd libinput-gestures
	makepkg -si


## Configure libinput
	sudo nano ~/.config/libinput-gestures.conf
#### paste this
	gesture swipe up 4 amixer -D pulse sset Master 7.5%+  
	gesture swipe down 4 amixer -D pulse sset Master 0%  
	gesture swipe left 4 playerctl play-pause    
	gesture swipe right 4 playerctl next  
	gesture pinch in 3 brightnessctl set 1%  
	gesture pinch out 3 brightnessctl set +7.5%