# Basic

## Testing

```sh
sudo docker-compose up
```

## Pipeline

- flb_forwarder: `dummy input`   -> `forward output`
- flb_receiver : `forward input` -> `stdout output`


## Example Output

```
$ sudo docker-compose up
Creating network "basic_flb-network" with driver "bridge"
Creating flb_forwarder ... done
Creating flb_receiver  ... done
Attaching to flb_forwarder, flb_receiver
flb_forwarder | Fluent Bit v1.8.3
flb_forwarder | * Copyright (C) 2019-2021 The Fluent Bit Authors
flb_forwarder | * Copyright (C) 2015-2018 Treasure Data
flb_forwarder | * Fluent Bit is a CNCF sub-project under the umbrella of Fluentd
flb_forwarder | * https://fluentbit.io
flb_forwarder | 
flb_forwarder | [2021/08/08 01:21:03] [ info] [engine] started (pid=1)
flb_forwarder | [2021/08/08 01:21:03] [ info] [storage] version=1.1.1, initializing...
flb_forwarder | [2021/08/08 01:21:03] [ info] [storage] in-memory
flb_forwarder | [2021/08/08 01:21:03] [ info] [storage] normal synchronization mode, checksum disabled, max_chunks_up=128
flb_forwarder | [2021/08/08 01:21:03] [ info] [cmetrics] version=0.1.6
flb_forwarder | [2021/08/08 01:21:03] [ info] [sp] stream processor started
flb_receiver | Fluent Bit v1.8.3
flb_receiver | * Copyright (C) 2019-2021 The Fluent Bit Authors
flb_receiver | * Copyright (C) 2015-2018 Treasure Data
flb_receiver | * Fluent Bit is a CNCF sub-project under the umbrella of Fluentd
flb_receiver | * https://fluentbit.io
flb_receiver | 
flb_receiver | [2021/08/08 01:21:03] [ info] [engine] started (pid=1)
flb_receiver | [2021/08/08 01:21:03] [ info] [storage] version=1.1.1, initializing...
flb_receiver | [2021/08/08 01:21:03] [ info] [storage] in-memory
flb_receiver | [2021/08/08 01:21:03] [ info] [storage] normal synchronization mode, checksum disabled, max_chunks_up=128
flb_receiver | [2021/08/08 01:21:03] [ info] [cmetrics] version=0.1.6
flb_receiver | [2021/08/08 01:21:03] [ info] [input:forward:forward.0] listening on 0.0.0.0:24224
flb_receiver | [2021/08/08 01:21:03] [ info] [sp] stream processor started
flb_receiver | [0] dummy.0: [1628385663.755287853, {"message"=>"dummy"}]
flb_receiver | [1] dummy.0: [1628385664.755479322, {"message"=>"dummy"}]
flb_receiver | [2] dummy.0: [1628385665.755048660, {"message"=>"dummy"}]
flb_receiver | [3] dummy.0: [1628385666.755142668, {"message"=>"dummy"}]
```