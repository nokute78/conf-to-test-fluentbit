# Performance

To measure `rewrite_tag` performance.

## Testing

```
fluent-bit -c main.conf
```

`no_filter.conf` is to measure performance without `rewrite_tag` filter.

## Pipeline

`dummy input` -> `rewrite_tag filter` -> `(re emit)` ->`flowcounter output`

## Example Output

```
$ fluent-bit -c main.conf 
Fluent Bit v1.8.0
* Copyright (C) 2019-2021 The Fluent Bit Authors
* Copyright (C) 2015-2018 Treasure Data
* Fluent Bit is a CNCF sub-project under the umbrella of Fluentd
* https://fluentbit.io

[2021/03/31 08:03:32] [ info] [engine] started (pid=4412)
[2021/03/31 08:03:32] [ info] [storage] version=1.1.1, initializing...
[2021/03/31 08:03:32] [ info] [storage] in-memory
[2021/03/31 08:03:32] [ info] [storage] normal synchronization mode, checksum disabled, max_chunks_up=128
[2021/03/31 08:03:32] [ info] [sp] stream processor started
[out_flowcounter] [1617145412, {"counts":1727, "bytes":67353, "counts/second":1727, "bytes/second":67353 }]
[out_flowcounter] [1617145413, {"counts":32260, "bytes":1258140, "counts/second":32260, "bytes/second":1258140 }]
[out_flowcounter] [1617145414, {"counts":31605, "bytes":1232595, "counts/second":31605, "bytes/second":1232595 }]
[out_flowcounter] [1617145415, {"counts":31586, "bytes":1231854, "counts/second":31586, "bytes/second":1231854 }]
[out_flowcounter] [1617145416, {"counts":32072, "bytes":1250808, "counts/second":32072, "bytes/second":1250808 }]
```