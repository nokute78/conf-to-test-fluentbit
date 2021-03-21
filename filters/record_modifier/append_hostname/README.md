# Append Hostname

## Testing

```sh
fluent-bit -c main.conf
```

## Pipeline

`dummy input` -> `record_modifier filter` -> `stdout output`

## Filtered Record

Before filtering:
```
{"message"=>"dummy"}
```

After filtering:
```
{"message"=>"dummy", "hostname"=>"locals"}
```


## Example output

```
$ fluent-bit -c main.conf
Fluent Bit v1.8.0
* Copyright (C) 2019-2021 The Fluent Bit Authors
* Copyright (C) 2015-2018 Treasure Data
* Fluent Bit is a CNCF sub-project under the umbrella of Fluentd
* https://fluentbit.io

[2021/03/21 19:38:10] [ info] [engine] started (pid=64452)
[2021/03/21 19:38:10] [ info] [storage] version=1.1.1, initializing...
[2021/03/21 19:38:10] [ info] [storage] in-memory
[2021/03/21 19:38:10] [ info] [storage] normal synchronization mode, checksum disabled, max_chunks_up=128
[2021/03/21 19:38:10] [ info] [sp] stream processor started
[0] dummy.0: [1616323091.289196529, {"message"=>"dummy", "hostname"=>"locals"}]
```