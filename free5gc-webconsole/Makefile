.PHONY: all build push

REGISTRY=docker.io
IMAGE=openverso/free5gc-webui
TAG=1.0.1

build:
	docker build -t ${IMAGE}:${TAG} --build-arg version=${TAG} . 
push:
	echo "Pushing the images ${IMAGE} to ${REGISTRY}"; \
	echo "Insert credentials to registry: "; \
	docker --config=.docker login ${REGISTRY}; \
	docker tag ${IMAGE}:${TAG} ${REGISTRY}/${IMAGE}:${TAG}; \
	docker --config=.docker push ${REGISTRY}/${IMAGE}:${TAG}; \
	rm -r .docker

all: build push
