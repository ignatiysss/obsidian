##### create new directory and file
	mkdir /opt/mosquitto/
	mkdir /opt/mosquitto/config
	nano /opt/mosquitto/config/mosquitto.conf
##### sudo
	sudo mkdir /opt/mosquitto/
	sudo mkdir /opt/mosquitto/config
	sudo nano /opt/mosquitto/config/mosquitto.conf
##### /opt/mosquitto/config/mosquitto.conf
	persistence true
	persistence_location /mosquitto/data/
	log_dest file /mosquitto/log/mosquitto.log
	listener 1883
	
	## Authentication ##
	allow_anonymous false
	password_file /mosquitto/config/password.txt

##### open portainer and run this command in sh
	mosquitto_passwd -c /mosquitto/config/password.txt USER_NAME

