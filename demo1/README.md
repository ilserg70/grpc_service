## Demo 1

Contents:

```
$ tree -L 2 demo1
demo1
├── grpc-services
│   ├── client_wrapper.py
│   ├── protos
│   └── users
├── requirements.txt
└── webapp
    ├── app.py
    └── run-server.sh
```

- `grpc-services/protos`: `protobuf` definitions for a service `users`
- `grpc-services/users`: Sample client and server for the `users` service
- `grpc-services/client_wrapper.py`: A generic gRPC client wrapper
- `webapp`: A simple Flask application which interfaces with the `users` service

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


