## Netstat

### Kernel routing table

`netstat -nr`

### Display interface statistics

`netstat -i`

### Display connections

`netstat -ta`

### List out only listening connections

`netstat -tnl`

### Get process name/pid and user id

`netstat -nltp`

### Display only established connections

`netstat -atnp | grep ESTA`

### Find out which process occupies the port

`lsof -nP | grep LISTEN`
