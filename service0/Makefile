export tag=v1.0
root:
	export ROOT=github.com/cncamp/service0

build:
	echo "building service0 binary"
	mkdir -p bin/amd64
	CGO_ENABLED=0 GOOS=linux GOARCH=amd64 go build -o bin/amd64 .

release: build
	echo "building service0 container"
	docker build -t cncamp/service0:${tag} .

push: release
	echo "pushing cncamp/service0"
	docker push cncamp/service0:${tag}