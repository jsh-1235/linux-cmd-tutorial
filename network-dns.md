# Network

## hostname

- hostname - show or set the system's host name
- cat /etc/hostname

## Get IP

- ip addr             // private ip
- ip addr | grep 192.168.0.5
- curl ipinfo.io/ip   // public ip
- elinks https://whatismyipaddress.com/
- host localhost
- hostname -I

## WiFi

- apt install wireless-tools
- iwconfig
- sudo lshw -c network


## host

- host - DNS lookup utility
- host pm2.bt-product-app.link

## DNS

- nslookup pm2.bt-product-app.link
- nameserver 172.24.160.1

## Port

- netstat -nap | grep LISTENING

## ifconfig

- ifconfig - configure a network interface
- ifconfig

## ip

- ip addr show
- ip addr show dev eth0
- ip route show
- ip maddr show

## nmap

- nmap - Network exploration tool and security / port scanner
- nmap localhost

## netstat

- netstat -rn
- netstat -a

## route

- route - show / manipulate the IP routing table
- route

## traceroute

- traceroute - print the route packets trace to network host
- traceroute server.bt-product-app.link


# hosts file

- C:\Windows\System32\drivers\etc
- cat /etc/hosts
- cat /etc/resolv.conf
- host localhost
