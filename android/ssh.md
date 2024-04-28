#### Install and generating key
	pkg install openssh
	ssh-keygen -A
	sshd
#### Find the ip and username
	su -c 'ip addr show'
	whoami
	passwd
#### Login form another device 
	ssh "username"@"ip-adress"
