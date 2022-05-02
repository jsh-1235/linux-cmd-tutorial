# apache2

## install

- apt update
- apt install apache2

## Directory List

- /etc/apache2/apache2.conf – The main Apache global configuration file, that includes all other configuration files.
- /etc/apache2/conf-available – stores available configurations.
- /etc/apache2/conf-enabled – contains enabled configurations.
- /etc/apache2/mods-available – contains available modules.
- /etc/apache2/mods-enabled – contains enabled modules.
- /etc/apache2/sites-available – contains configuration file for available sites (virtual hosts).
- /etc/apache2/sites-enabled – contains configuration file for enabled sites (virtual hosts).
- /etc/apache2/ports.conf

## Virtual Hosting

- 단일 서버에서 둘 이상의 웹 사이트 및 응용프로그램을 운영하는 방식
- ls -l /var/www/html/
- cd /var/www/html
- vi index.html

## Edit

- $APACHE_RUN_DIR

## Control

- apache2 -v
- sudo service apache2 start
- sudo service apache2 stop
- sudo service apache2 status
- sudo systemctl status apache2
- cat /var/log/apache2/access.log
- tail -f /var/log/apache2/access.log
- tail -f /var/log/apache2/other_vhosts_access.log

## Firewall (UFW)

- ufw - program for managing a netfilter firewall
- sudo ufw enable
- sudo ufw disable
- sudo ufw allow 'Apache Full'
- sudo ufw allow http : sudo ufw allow 80/tcp
- sudo ufw allow https : sudo ufw allow 443/tcp
- sudo ufw reload
- sudo ufw status
- <http://172.23.209.60:4000/>
- <http://localhost:4000/>

## Monitoring

- htop
- htop : Filter
- ps -aux | grep apache2

## IP

- ip addr             // private ip
- hostname -I
- curl ipinfo.io/ip   // public ip
- elinks ipinfo.io
- curl ifconfig.co
- curl ifconfig.me
- curl icanhazip.com

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

## gateway

- ip route
- default via 172.23.208.1 dev eth0

## Bitnami WAMP Stack

- Root 경로 변경
  - C:\Bitnami\wampstack-7.4.11-0\apache2\conf\bitnami\bitnami.conf

  ```xml
    <VirtualHost _default_:3456>
      DocumentRoot "C:/Products/Software Devlopment/New Web/Client Side/React/Study/react-firebase-app/build"
      <Directory "C:/Products/Software Devlopment/New Web/Client Side/React/Study/react-firebase-app/build">
        Options Indexes FollowSymLinks
        AllowOverride All
        <IfVersion < 2.3 >
          Order allow,deny
          Allow from all
        </IfVersion>
        <IfVersion >= 2.3 >
          Require all granted
        </IfVersion>
      </Directory>
    </VirtualHost>
  ```

- Port 변경
  - C:\Bitnami\wampstack-7.4.11-0\apache2\conf\httpd.conf

  ```xml
    Listen 3456
  ```

## rsync

- cd /mnt/c/Products/"Software Devlopment"/Web/DevOps/Linux/Study/linux-apache2

- sudo rsync -ahrvz --delete --progress /mnt/c/Products/"Software Devlopment"/Web/DevOps/Linux/Study/linux-apache2/ -e "ssh -i aws-bt-key.pem" ubuntu@ec2-52-78-209-69.ap-northeast-2.compute.amazonaws.com:~/linux-apache2/

- sudo rsync -ahrvz --delete --progress /mnt/c/Products/"Software Devlopment"/Web/DevOps/Linux/Study/linux-apache2/ -e "ssh -i aws-bt-key.pem" ubuntu@ec2-52-78-209-69.ap-northeast-2.compute.amazonaws.com:/var/www/html

- sudo rsync -ahrvz --delete --progress --rsync-path="sudo rsync" /mnt/c/Products/"Software Devlopment"/Web/DevOps/Linux/Study/linux-apache2/ -e "ssh -i aws-bt-key.pem" ubuntu@ec2-52-78-209-69.ap-northeast-2.compute.amazonaws.com:/var/www/html
