# mqtt-bridge-compose

build image mosca
			cd ~
			git clone git@github.com:magimat/mosca.git
			cd mosca
			docker build -f Dockerfile-rpi -t magimat/mosca .
			docker push magimat/mosca

		build image mqtt-bridge
			cd ~
			git clone git@github.com:magimat/smartthings-mqtt-bridge.git
			cd smartthings-mqtt-bridge
			docker build -f Dockerfile-rpi -t magimat/smartthings-mqtt-bridge .
			docker push magimat/smartthings-mqtt-bridge


		start compose mqtt
			cd ~
			git clone git@github.com:magimat/mqtt-bridge-compose.git
			cd mqtt-bridge-compose


			docker stack deploy -c docker-compose.yml mqtt-bridge-service
