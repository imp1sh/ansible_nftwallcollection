# ansible_dnsmasq
Ansible role in order to configure dnsmasq solution in multi purpose environment as recursve dns, optionally also as authoritative (for local net only) nameserver. It also shall act as DHCP server.
Main function is IPv6 so Router Advertisement and DHCPv6.

Currently only very basic configuration is possible. There's more to come.
This is how a variables need to be set for exmaple:

    dnsmasq_dnsport: 53
    dnsmasq_domainneeded: true
    dnsmasq_boguspriv: false
    dnsmasq_dnssec: false
    dnsmasq_dnssec_checkunsigned: false
    dnsmasq_localservice: true
    dnsmasq_dhcpenable: true
    dnsmasq_dhcp4ifs:
      - interface: "eth1"
        ranges:
        - start: "172.16.33.10"
          end: "172.16.33.20"
          leasetime: "24h"
        - start: "172.16.33.100"
          end: "172.16.33.120"
    # options like in pfSense: disabled, Router Only, Unmanaged, Managed, Assisted, Stateless DHCP
    # https://docs.netgate.com/pfsense/en/latest/book/services/ipv6-dhcp-server-and-router-advertisements.html
    # currently only managed and unmanaged is implemented. start and end are being ignored if it's set to unmamaged
    dnsmasq_ipv6mode: "managed"
    dnsmasq_dhcpifs:
      - interface: "eth1"
        start: "::1000"
        end: "::2000"


