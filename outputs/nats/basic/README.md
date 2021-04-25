# Basic

## Testing

```
sudo docker run -p 4222:4222 -ti --rm nats
fluent-bit -c main.conf
```

## Pipeline

`cpu input` -> `nats output`

## Example Output

```
$ fluent-bit -i cpu -t cpu_input -o nats
Fluent Bit v1.8.0
* Copyright (C) 2019-2021 The Fluent Bit Authors
* Copyright (C) 2015-2018 Treasure Data
* Fluent Bit is a CNCF sub-project under the umbrella of Fluentd
* https://fluentbit.io

[2021/04/25 13:39:08] [ info] [engine] started (pid=23453)
[2021/04/25 13:39:08] [ info] [storage] version=1.1.1, initializing...
[2021/04/25 13:39:08] [ info] [storage] in-memory
[2021/04/25 13:39:08] [ info] [storage] normal synchronization mode, checksum disabled, max_chunks_up=128
[2021/04/25 13:39:08] [ info] [sp] stream processor started
```

## Subscribe by telnet


### Connect to NATS server.

https://docs.nats.io/nats-protocol/nats-protocol-demo

```
$ telnet localhost 4222
Trying 127.0.0.1...
Connected to localhost.
Escape character is '^]'.
INFO {"server_id":"NDHLL4GBXUKAWH5MIR3IPC7DYGN277DQTSL6W3K7SWWG3PKXEPQTDYMU","server_name":"NDHLL4GBXUKAWH5MIR3IPC7DYGN277DQTSL6W3K7SWWG3PKXEPQTDYMU","version":"2.2.2","proto":1,"git_commit":"a5f3aab","go":"go1.16.3","host":"0.0.0.0","port":4222,"headers":true,"max_payload":1048576,"client_id":7,"client_ip":"172.17.0.1","cluster":"A4EVDKBDGHJ90aM74ovfiQ"}
```

### Configuration for `cpu_input`.

https://docs.nats.io/nats-protocol/nats-protocol#sub

```
sub cpu_input 1
```

### Subscribe message

```
MSG cpu_input 1 537
[[1619325886.87345,{"tag":"cpu_input","cpu_p":5.0,"user_p":5.0,"system_p":0.0,"cpu0.p_cpu":5.0,"cpu0.p_user":5.0,"cpu0.p_system":0.0}],[1619325887.87537,{"tag":"cpu_input","cpu_p":5.0,"user_p":4.0,"system_p":1.0,"cpu0.p_cpu":5.0,"cpu0.p_user":4.0,"cpu0.p_system":1.0}],[1619325888.87394,{"tag":"cpu_input","cpu_p":6.0,"user_p":5.0,"system_p":1.0,"cpu0.p_cpu":6.0,"cpu0.p_user":5.0,"cpu0.p_system":1.0}],[1619325889.87437,{"tag":"cpu_input","cpu_p":4.0,"user_p":4.0,"system_p":0.0,"cpu0.p_cpu":4.0,"cpu0.p_user":4.0,"cpu0.p_system":0.0}]]
```


