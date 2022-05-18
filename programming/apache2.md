# apache2

## install

- apt update
- apt install apache2
- apt remove apache2
- apt purge --auto-remove apache2
- apache2 -v

## Directory List

- ls -al /etc/apache2
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
- vi /var/www/html/index.html

## start / stop

- sudo service apache2 start
- sudo service apache2 stop
- sudo service apache2 restart

## status

- sudo service apache2 status
- sudo systemctl status apache2

- dpkg -l | grep apache2
- dpkg -L apache2
- service --status-all | grep apache2
- ps -ef | grep apache2

## log

- cat /var/log/apache2/access.log
- tail -f /var/log/apache2/access.log
- tail -f /var/log/apache2/other_vhosts_access.log

## rsync

- cd /mnt/c/Products/"Software Devlopment"/Web/DevOps/Linux/Study/linux-apache2

- sudo rsync -ahrvz --delete --progress /mnt/c/Products/"Software Devlopment"/Web/DevOps/Linux/Study/linux-apache2/ -e "ssh -i aws-bt-key.pem" ubuntu@ec2-52-78-209-69.ap-northeast-2.compute.amazonaws.com:~/linux-apache2/

- sudo rsync -ahrvz --delete --progress /mnt/c/Products/"Software Devlopment"/Web/DevOps/Linux/Study/linux-apache2/ -e "ssh -i aws-bt-key.pem" ubuntu@ec2-52-78-209-69.ap-northeast-2.compute.amazonaws.com:/var/www/html

- sudo rsync -ahrvz --delete --progress --rsync-path="sudo rsync" /mnt/c/Products/"Software Devlopment"/Web/DevOps/Linux/Study/linux-apache2/ -e "ssh -i aws-bt-key.pem" ubuntu@ec2-52-78-209-69.ap-northeast-2.compute.amazonaws.com:/var/www/html

## php

- apt -y install php
- dpkg -l | grep php
- dpkg -L php
- http://localhost/a.php

## demon

- systemctl enable apache2 (Enable Auto Start)
- systemctl disable apache2
- systemctl status
