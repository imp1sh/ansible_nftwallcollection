# ansible_netconfig
basic network configuration role for ansible. Not every scenario is being offered but we try to enhance this role in the future.
In order for the accept_ra option to work, ipm1sh.sysctl is needed and is to be associated to the host, too.
```
netinterfaces:
  - interface: "eth0"
    name: "WAN"
    accept_ra: "2"
    method: "dhcp"
    method6: "static"
    ip6: "2001:470:7e68::2/64"
    gateway6: "2001:470:7e68::1"
  - interface: "eth1"
    name: "LAN1"
    accept_ra: "0"
    method: "static"
    ip: "172.16.33.1/24"
    method6: "static"
    ip6: "2001:470:7e68:1000::1/64"
```
