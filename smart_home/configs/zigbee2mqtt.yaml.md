	homeassistant: true
	permit_join: true
	mqtt:
	  base_topic: zigbee2mqtt
	  server: mqtt://172.19.0.3:1883
	  user: hass
	  password: ghjkhgfd
	serial:
	  adapter: ezsp
	  port: /dev/ttyACM0
	frontend:
	  port: 8080
	devices:
	  '0xa4c13889a01e6338':
	    friendly_name: '0xa4c13889a01e6338'
	  '0xa4c138a285302731':
	    friendly_name: '0xa4c138a285302731'
	  '0xa4c13867ea1e27bf':
	    friendly_name: '0xa4c13867ea1e27bf'
	advanced:
	  homeassistant_legacy_entity_attributes: false
	  legacy_api: false
	  legacy_availability_payload: false
	device_options:
	  legacy: false