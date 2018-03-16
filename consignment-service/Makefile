build:
	protoc -I. --go_out=plugins=micro:$(GOPATH)/src/github.com/Sh4d1/wat/consignment-service proto/consignment/consignment.proto
	#CGO_ENABLED=0 GOOS=linux GOARCH=amd64 go build -a -ldflags '-extldflags "-static"' .
	docker build -t consignment-service .

run:
	docker run -p 50051:50051 \
		-e MICRO_SERVER_ADDRESS=:50051 \
		-e MICRO_REGISTRY=mdns \
		consignment-service
