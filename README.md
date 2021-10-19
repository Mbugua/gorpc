This is basic example of gRPC based microservice to serve a Virtual Stack Machine over HTTP2.0 network.

# Pre-requisites
```bash
# install protobuf compiler
~/gorpc
$ go get -u -v github.com/golang/protobuf/{proto,protoc-gen-go}

# install grpc
~/gorpc
$ go get -u -v google.golang.org/grpc
```
# Generate Go Source Code from Protobuf
```bash
~/gorpc
$ SRC_DIR=./
$ DST_DIR=$SRC_DIR
$ protoc -I=$SRC_DIR --go_out=plugins=grpc:$DST_DIR $SRC_DIR/machine/machine.proto
```

# Run
```bash
~/gorpc
$ go run cmd/run_machine_server.go
$ go run client/machine.go
```