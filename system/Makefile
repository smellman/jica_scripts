all: install

install: upgrade p7zip charites mbutil tileserver-gl-light

upgrade:
	@echo upgrade
	apt update
	apt dist-upgrade -y

p7zip:
	@echo install p7zip-full
	apt install -y p7zip-full

charites:
	@echo install unvt/charites
	npm install -g @unvt/charites

mbutil:
	@echo install mb-util
	apt install -y python3 python3-pip
	pip3 install smellman-mbutil --break-system-packages

tileserver-gl-light:
	@echo install tileserver-gl-light
	npm install -g tileserver-gl-light
