# mqtt-bridge-compose

		checkout repo
			cd ~
			git clone git@github.com:magimat/mqtt-bridge-compose.git

		build image mosca
			cd mqtt-bridge-compose/mosca
			docker build -f Dockerfile-rpi -t magimat/mosca .
			docker push magimat/mosca

		build image mqtt-bridge
			cd mqtt-bridge-compose/smartthings-mqtt-bridge
			docker build -f Dockerfile-rpi -t magimat/smartthings-mqtt-bridge .
			docker push magimat/smartthings-mqtt-bridge


		start compose mqtt
			cd mqtt-bridge-compose
			docker stack deploy -c docker-compose.yml mqtt-bridge-service
