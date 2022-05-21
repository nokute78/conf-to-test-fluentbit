# Basic 

## Testing

```
curl https://raw.githubusercontent.com/fluent/fluent-bit/master/conf/parsers.conf > parsers.conf
nc -lu 51400
fluent-bit -c main.conf
```

## Pipeline

`dummy input` -> `syslog output` -> `netcat`

## Example Output

```
$ nc -lu 51400
<14>1 2022-05-21T01:52:14.086987Z myhost myapp 1234 ID98 [uls@0 logtype="access" clustername="mycluster" namespace="mynamespace"] ﻿Sample app log message.
```