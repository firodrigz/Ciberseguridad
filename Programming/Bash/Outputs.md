```bash
# Identify Network range for the specified IP address(es)
function network_range {
	for ip in $ipaddr
	do
		netrange=$(whois $ip | grep "NetRange\|CIDR" | tee -a CIDR.txt)
		cidr=$(whois $ip | grep "CIDR" | awk '{print $2}')
		cidr_ips=$(prips $cidr)
		echo -e "\nNetRange for $ip:"
		echo -e "$netrange"
	done
}

<SNIP>

# Identify IP address of the specified domain
hosts=$(host $domain | grep "has address" | cut -d" " -f4 | tee discovered_hosts.txt)
```


```shell-session
firodrigz@test$ cat discovered_hosts.txt CIDR.txt

165.22.119.202
NetRange:       165.22.0.0 - 165.22.255.255
CIDR:           165.22.0.0/16
```
