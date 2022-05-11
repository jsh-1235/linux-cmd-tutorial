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
- systemctl status ssh
- systemctl start ssh
- systemctl stop ssh

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
