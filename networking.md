# Networking

https://www.digitalocean.com/community/tutorials/understanding-ip-addresses-subnets-and-cidr-notation-for-networking

IPv4 has a concept of _classes_, the address space is divided into 5 classes (A, B, C, D, E). No longer really used in practice.

## Expressing subnets

Can use CIDR to indicate which bits of the prefix are significant. Can also use a netmask.

In examples we will use the loopback range of 127.0.0.0 to 127.255.255.255.

### CIDR

127.0.0.0/8

/8 indicates that only the first 8 bits are significant

### Netmask

Address: 127.0.0.0

Netmask: 255.0.0.0 in decimal, or 1111 1111.0000 0000.0000 0000.0000 0000 in binary

Netmask shows which 

## Reserved IP address ranges

https://en.wikipedia.org/wiki/Reserved_IP_addresses

Some of the most common ones:

* Loopback range (connect to self): 127.0.0.0/8
* Private network: 10.0.0.0/8, 192.168.0.0/16