# Basic

## Testing

```sh
curl https://raw.githubusercontent.com/fluent/fluent-bit/master/conf/parsers.conf > parsers.conf
fluent-bit -c main.conf &
logger -P 15140 --server localhost --tcp test_message
```

## Pipeline

`logger` -> `syslog input` -> `stdout output`

## Example Output

```
$ fluent-bit -c main.conf 
Fluent Bit v1.8.0
* Copyright (C) 2019-2021 The Fluent Bit Authors
* Copyright (C) 2015-2018 Treasure Data
* Fluent Bit is a CNCF sub-project under the umbrella of Fluentd
* https://fluentbit.io

[2021/03/21 19:25:57] [ info] [engine] started (pid=64263)
[2021/03/21 19:25:57] [ info] [storage] version=1.1.1, initializing...
[2021/03/21 19:25:57] [ info] [storage] in-memory
[2021/03/21 19:25:57] [ info] [storage] normal synchronization mode, checksum disabled, max_chunks_up=128
[2021/03/21 19:25:57] [ info] [in_syslog] TCP server binding 0.0.0.0:15140
[2021/03/21 19:25:57] [ info] [sp] stream processor started
[0] syslog.0: [1616322510.966709000, {"pri"=>"13", "time"=>"2021-03-21T19:28:30.966709+09:00", "host"=>"locals", "ident"=>"taka", "pid"=>"-", "msgid"=>"-", "extradata"=>"[timeQuality tzKnown="1" isSynced="1" syncAccuracy="33000"]", "message"=>"test_message"}]
```