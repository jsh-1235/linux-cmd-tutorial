# apache2

## install

- apt update
- apt install apache2
- apt update
- apt install apache2

## Command

- apache2 -v
- sudo service apache2 start
- sudo service apache2 stop

## Monitoring

- htop
- htop : Filter
- ps -aux | grep apache2

## IP

- ip addr             // private ip
- curl ipinfo.io/ip   // public ip
- elinks ipinfo.io

## netstat (Port)

- netstat
- netstat -tnlp
- netstat -lntup

## lsof (Port)

- lsof
- lsof -i
- lsof -i -nP
- lsof -i -nP | grep LISTEN

## nmap (Port)

- nmap localhost
- nmap -PN localhost -p80 | grep ^80
- nmap -PN localhost -p81 | grep ^81
- nmap -PN daum.net -p80 | grep ^80

## Remote port check

- nc -zv localhost 80
- nc -zv daum.net 80
