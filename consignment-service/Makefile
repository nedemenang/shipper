build:
	protoc -I. --go_out=plugins=micro:$(GOPATH)/src/github.com/nedemenang/shipper/consignment-service \
		proto/consignment/consignment.proto

	docker build -t consignment-service .
run:
	docker run -p 50052:50052 \
		-e MICRO_SERVER_ADDRESS=:50052 \
		-e MICRO_REGISTRY=mdns consignment-service