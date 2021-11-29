export tag=v1.0
root:
	export ROOT=github.com/cncamp/service1

build:
	echo "building service1 binary"
	mkdir -p bin/amd64
	CGO_ENABLED=0 GOOS=linux GOARCH=amd64 go build -o bin/amd64 .

release: build
	echo "building service1 container"
	docker build -t cncamp/service1:${tag} .

push: release
	echo "pushing cncamp/service1"
	docker push cncamp/service1:${tag}