# Simple Python gRPC Service

## Proto Definition
- Client send a count to server
- Server increases the count by 1 and return count back
- Client continue to send the received count to server
```
syntax = "proto3";

service PingPongService {
  rpc ping (Ping) returns (Pong) {}
}

message Ping {
  int32 count = 1;
}

message Pong {
  int32 count = 1;
}
```


## How to Run Services

### Start Server
```commandline
python server.py
```

### Start Single Client
```commandline
python client.py
```

### Start Multi Process Clients
```commandline
python multiprocess.py
```

## Sample Outputs

### Server
```
server on: threads 2
server on: threads 3
10000 calls in 11.015247106552124 seconds
server on: threads 3
10000 calls in 9.42374873161316 seconds
10000 calls in 8.20230507850647 seconds
server on: threads 3
```

### Client
```
0.000521 : resp=1000 : procid=11166
0.000547 : resp=2000 : procid=11166
0.000577 : resp=3000 : procid=11166
0.001827 : resp=4000 : procid=11166
0.000379 : resp=5000 : procid=11166
0.000573 : resp=6000 : procid=11166
0.000772 : resp=7000 : procid=11166
0.000614 : resp=8000 : procid=11166
0.000865 : resp=9000 : procid=11166
0.000815 : resp=10000 : procid=11166
0.001194 : resp=11000 : procid=11166
0.001803 : resp=12000 : procid=11166
0.000416 : resp=13000 : procid=11166
0.000583 : resp=14000 : procid=11166
0.000536 : resp=15000 : procid=11166
```