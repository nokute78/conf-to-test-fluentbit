# Output_Japanese

## Testing

```
fluent-bit -c main.conf
```

## Pipeline

`dummy input` -> `stdout output`


## Example Output

```
$ fluent-bit -c main.conf 
Fluent Bit v1.8.0
* Copyright (C) 2019-2021 The Fluent Bit Authors
* Copyright (C) 2015-2018 Treasure Data
* Fluent Bit is a CNCF sub-project under the umbrella of Fluentd
* https://fluentbit.io

[2021/03/26 21:48:33] [ info] [engine] started (pid=133674)
[2021/03/26 21:48:33] [ info] [storage] version=1.1.1, initializing...
[2021/03/26 21:48:33] [ info] [storage] in-memory
[2021/03/26 21:48:33] [ info] [storage] normal synchronization mode, checksum disabled, max_chunks_up=128
[2021/03/26 21:48:33] [ info] [sp] stream processor started
{"date":1616762914.200443,"val":"\u3042\u3044\u3046\u3048\u304a"}
^C[2021/03/26 21:48:38] [engine] caught signal (SIGINT)
```

## Note

v1.7.2 mishandles this configuration. https://github.com/fluent/fluent-bit/issues/3280