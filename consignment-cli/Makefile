build:
	CGO_ENABLED=0 GOOS=linux GOARCH=amd64 go build -a -ldflags '-extldflags "-static"' .
	docker build -t consignment-cli .

run:
	docker run \
		-e MICRO_REGISTRY=mdns \
		consignment-cli
