# Docker

	docker build -t <image-name>
	docker tag <image-name> <docker-registry-host>/<space>/<image-name>
	docker login <docker-registry-host>
	docker push <image-name>
	
#### Unsecure docker registries

Add the registry url to /etc/docker/daemon.json:

	{ "insecure-registries": [ <docker-registry-host> ] }