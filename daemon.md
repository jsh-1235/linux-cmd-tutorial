# daemon

- whereis apache2
- which apache2
- cd /etc/init.d
- sudo service apache2 start
- curl http://localhost
- elinks
- sudo service apache2 stop
- ps -aux | grep apach2

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

## cron (How to run a command regularly)

- crontab -e
- date >> date.log
- crontab --help
- crontab -e
- cd ~
- tail -f date.log