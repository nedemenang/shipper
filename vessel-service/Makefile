build:
	protoc -I. --go_out=plugins=micro:$(GOPATH)/src/github.com/nedemenang/shipper/vessel-service \
	proto/vessel/vessel.proto
	docker build -t vessel-service .

run:
	docker run -p 50053:50052 -e MICRO_SERVER_ADDRESS=:50052 -e MICRO_REGISTRY=mdns vessel-service
