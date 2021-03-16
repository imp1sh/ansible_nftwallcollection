# ansible_sysctl
Part of nftwall. Sets kernel parameters that are often needed in a firewall.
Sets good default parameters for firewall system. On top of basic parameters you can also set accept_ra parameters for netinterfaces. Usually used together with imp1sh.netinterfaces.

Example of netinterfaces variables making use of this role:
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
