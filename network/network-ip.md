# ip (Internet Protocol)

- IANA (Internet Assigned Number Authority)
- Ethernet (고유 주소로 MAC 주소 할당)
- IP Addres (Network Address + Host Address: IPv4 32bit)
- Subnet Mask
- Class : A (8), B (16), C (24)
- Public IP / Private IP
- NAT (Network Address Transfer)
- IPv6 (128bit)

## private ip

- ip addr
- hostname -I
- host localhost

## public ip

- curl ipinfo.io/ip
- curl ifconfig.co
- curl ifconfig.me
- curl icanhazip.com
- elinks ipinfo.io
- elinks https://whatismyipaddress.com/

## host

- host www.example.com (get ip)
- host 93.184.216.34 (get domain)

## ip

- ip addr show
- ip addr list
- inet 172.26.31.58/20 brd 172.26.31.255 scope global eth0 (Network addr: 20, Host addr: 12)

## ifconfig (configure a network interface)

- ifconfig
- inet 172.26.31.58  netmask 255.255.240.0  broadcast 172.26.31.255
