# Network Interface

## ifconfig (configure a network interface)

- ifconfig

## WiFi

- sudo apt install wireless-tools
- iwconfig
- sudo lshw -c network

## gateway

- ip route
- default via 172.23.208.1 dev eth0

## dhcp

- IP 동적 할당
  - ip addr flush dev eth0
  - dhclient et0

- IPO 수동 할당
  - dhclient -r et0 (dhcp server stop)
  - ip addr flush dev eth0
  - ip addr add 10.0.2.12/24 dev eth0
