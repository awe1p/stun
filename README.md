## stun extension for openwrt, which inclides stund and stun-client

Compile
---
```
# cd to OpenWrt source path
# Clone this repo
git clone https://github.com/awe1p/stun.git package/network/stun
# Select Network -> stun-client and Network -> stund
make menuconfig
# Compile
make V=s
```

Usage
---
```
# you should have at least two routers as server and client
# run in stun server with two interface connected to the Internet
stund -v
# run in stun client to get your NAT type in response
stun-client {server IP} -v
```
Result
---
```
when you get 
Independent Mapping, Independent Filter = Fullcone NAT
Independent Mapping, Address Dependent Filter = Restricted Cone NAT
Independent Mapping, Port Dependent Filter = Port-Restricted Cone NAT
Dependent Mapping = Symmetric NAT
```
