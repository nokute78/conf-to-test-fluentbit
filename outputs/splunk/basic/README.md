# Basic

## Testing

```
SPLUNK_PASSWORD=<password> docker-compose up -d
fluent-bit -c main.conf
```

Note: `docker-compose.yml` is here.
https://splunk.github.io/docker-splunk/EXAMPLES.html#create-standalone-with-hec

## Pipeline

`cpu input` -> `splunk output`

## Example Output

```
$ fluent-bit -c a.conf 
Fluent Bit v1.8.0
* Copyright (C) 2019-2021 The Fluent Bit Authors
* Copyright (C) 2015-2018 Treasure Data
* Fluent Bit is a CNCF sub-project under the umbrella of Fluentd
* https://fluentbit.io

[2021/04/05 09:18:28] [ info] [engine] started (pid=28371)
[2021/04/05 09:18:28] [ info] [storage] version=1.1.1, initializing...
[2021/04/05 09:18:28] [ info] [storage] in-memory
[2021/04/05 09:18:28] [ info] [storage] normal synchronization mode, checksum disabled, max_chunks_up=128
[2021/04/05 09:18:28] [ info] [sp] stream processor started
^C[2021/04/05 09:18:37] [engine] caught signal (SIGINT)
[2021/04/05 09:18:37] [ warn] [engine] service will stop in 5 seconds
^C[2021/04/05 09:18:38] [engine] caught signal (SIGINT)
```