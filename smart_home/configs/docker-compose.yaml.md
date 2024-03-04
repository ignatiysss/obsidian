	version: '3.0'
	services:
	  homeassistant:
	    container_name: homeassistant
	    image: "ghcr.io/home-assistant/home-assistant:stable"
	    volumes:
	      - /opt/homeassistant/config:/config
	      - /etc/localtime:/etc/localtime:ro
	    restart: unless-stopped
	    privileged: true
	    network_mode: host
	    devices:
	      - /dev/ttyACM0:/dev/ttyAMC0
	  mosquitto:
	    image: eclipse-mosquitto
	    container_name: mosquitto
	    volumes:
	      - /opt/mosquitto:/mosquitto
	      - /opt/mosquitto/data:/mosquitto/data
	      - /opt/mosquitto/log:/mosquitto/log
	    ports:
	      - 1883:1883
	      - 9001:9001
	    networks:
	      my_network:
	        ipv4_address: 172.19.0.3  
	
	  zigbee2mqtt:
	    container_name: zigbee2mqtt
	    image: koenkk/zigbee2mqtt
	    restart: unless-stopped
	    volumes:
	      - /opt/z2m/data:/app/data
	      - /run/udev:/run/udev:ro
	    ports:
	      - 8080:8080
	    environment:
	      - MQTT_SERVER=mqtt://172.19.0.3
	      - TZ=Europe/Dublin
	    devices:
	      - /dev/ttyACM0:/dev/ttyACM0
	    networks:
	      my_network:
	        ipv4_address: 172.19.0.4
	
	  portainer:
	    container_name: portainer
	    image: portainer/portainer-ce
	    restart: always
	    ports:
	      - "9000:9000/tcp"
	    environment:
	      - TZ=Europe/London
	    volumes:
	      - /var/run/docker.sock:/var/run/docker.sock
	      - /opt/portainer:/data
	    networks:
	      my_network:
	        ipv4_address: 172.19.0.5
	
	networks:
	  my_network:
	    driver: bridge
	    ipam:
	      config:
	        - subnet: "172.19.0.0/24"
