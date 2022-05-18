# daemon

- service (Ubuntu, Debian)
- systemctl (CentOS, Fedora)

## service (run a System V init script)

- service --status-all
- service --status-all | grep apache2
- service --status-all | grep +
- service apache2 status
- service apache2 start
- service apache2 stop

## systemctl (Control the systemd system and service manager)

- systemctl -a list-units
- systemctl -a list-units | grep ssh
- systemctl status sshd
- systemctl start sshd
- systemctl stop sshd

## service (apache2)

- whereis apache2
- which apache2
- cd /etc/init.d
- sudo service apache2 start
- service apache2 status
- ps -aux | grep apache2
- sudo service apache2 stop

## curl

- curl http://localhost
- elinks http://localhost

## rc.local

- cd /etc
- find *rc.local*
- su
- vi /etc/rc.local

```bash
  #! /bin/sh
  exit 0
```

- chmod +x /etc/rc.local

## Auto start

- ls -l /etc/rc?.d/*
- ls -l /etc/rc?.d/*apache2
- /etc/init.d/apache2 start

- cd /etc/init.d
- vim startup.sh
- chmode +x startup
- man update-rc.d
- update-rc.d startup defaults
- update-rc.d -f startup remove
- reboot

- systemctl enable apache2 (Enable Auto Start)
- systemctl disable apache2
