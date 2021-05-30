# pdnsmasq
Add or delete A record in PowerDNS via API invoked by Dnsmasq on every DHCP lease, expire or update.

### Setup
Configure Dnsmasq as DHCP server and point the `dhcp-script` to the pdnsmasq script like
```
dhcp-script=/usr/local/bin/pdnsmasq
```


Dnsmasq calls the script with the following arguments
```
<add|del|old> <MAC address> <IP address> (<Client-Hostname>)
```
like
```
add c4:06:84:97:73:2a 10.11.12.14 Client-Host
```
