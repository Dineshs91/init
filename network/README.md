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


### Clear DNS cache on OS X (Yosemite, El captain and Sierra)

`sudo dscacheutil -flushcache; sudo killall -HUP mDNSResponder`

For other check this [article](https://support.opendns.com/hc/en-us/articles/227988627-Clearing-the-DNS-Cache-on-Computers-and-Web-Browsers)

### Find all available ip's in local network

`nmap -sn 192.168.0.1/24`
