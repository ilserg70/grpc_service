# grpc_service
Example of Remote Procedure Call (RPC)

# Explanation

https://blog.codeship.com/using-grpc-in-python/

gRPC is an HTTP/2-based Remote Procedure Call (RPC) framework that uses protocol buffers (protobuf) as the underlying data serialization framework. It is an alternative to other language-neutral RPC frameworks such as Apache Thrift and Apache Arvo.

This gRPC service is a users service that exposes two functionalities: user signup and getting user details.


### Make venv 

```
python3 -m venv ~/.virtualenvs/grpc
. ~/.virtualenvs/grpc/bin/activate
python3 -m pip install grpcio grpcio-tools
```


### Build protos

```
cd demo1/grpc-services/protos/
./build.sh
```


### Run server

```
cd demo1/grpc-services/users/
./run-server.sh
```

### Client

```
cd demo1/grpc-services/users 
PYTHONPATH=../protos/gen-py/ python sample_client_demo.py
```

