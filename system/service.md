# daemon

- whereis apache2
- which apache2
- cd /etc/init.d

## Service

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
