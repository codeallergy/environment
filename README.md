# environment
Development Environment Instructions


### Configure (mac):

Install golang 1.17.13
```
wget [go1.17.13.darwin-amd64.pkg](https://go.dev/dl/go1.17.13.darwin-amd64.pkg)
```

Fix Goland IDE
```
sudo nano /usr/local/go/src/runtime/internal/sys/zversion.go
```
Add line:
```
const TheVersion = `go1.17`
```

Setup env
```
export PATH=$PATH:~/go/bin
export GOROOT=/usr/local/go  
export GOPATH=~/go
```

Setup env (optional)
```
export GONOSUMDB=github.com
```

Create dirs
```
mkdir ~/go
mkdir ~/go/bin
mkdir ~/go/src
```

Download and install Protoc 3.20.2 for your OS
```
open https://github.com/protocolbuffers/protobuf/releases/tag/v3.20.3
wget [protoc-3.20.3-osx-x86_64.zip](https://github.com/protocolbuffers/protobuf/releases/download/v3.20.3/protoc-3.20.3-osx-x86_64.zip)
unzip protoc-3.20.3-osx-x86_64.zip -d ~/go
```

Verify
```
protoc --version
libprotoc 3.20.3
```

Install protocol buffers src (optional)
```
cd ~/go/src/github.com/protocolbuffers
git clone https://github.com/protocolbuffers/protobuf
cd protobuf 
git checkout v3.20.3
```

Install protoc golang compiler
```
go install google.golang.org/protobuf/cmd/protoc-gen-go@v1.28.1
```

Install gRPC compiler
```
go install google.golang.org/grpc/cmd/protoc-gen-go-grpc@v1.3.0
```

Install gRPC gateway
```
go get -u github.com/grpc-ecosystem/grpc-gateway/v2@v2.15.2
```

Compile and install protoc-gen-grpc-gateway
```
cd ~/go/src/github.com/grpc-ecosystem
git clone https://github.com/grpc-ecosystem/grpc-gateway
cd grpc-gateway
git checkout v2.15.2
cd ~/go/src/github.com/grpc-ecosystem/grpc-gateway/protoc-gen-grpc-gateway
go install
```

Compile and install protoc-gen-openapiv2
```
cd ~/go/src/github.com/grpc-ecosystem/grpc-gateway/protoc-gen-openapiv2
go install
```

Install support libs
```
go install github.com/codeallergy/go-bindata/go-bindata@v1.0.0
go install github.com/google/go-licenses@v1.2.1
```

### Verify

```
cd ~/go/bin
ls
go-bindata
go-licenses
protoc-gen-go		
protoc-gen-go-grpc	
protoc-gen-grpc-gateway	
protoc-gen-openapiv2
```
