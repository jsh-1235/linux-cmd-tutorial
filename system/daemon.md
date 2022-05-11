# daemon

- 항상 동작할 프로세스를 데몬이라고 한다.
- 일부로 끄지 않는 한 Shutdown할 때까지 계속 동작한다.

## sleep (delay for a specified amount of time)

- sleep 1s
- sleep 1m
- sleep 1m 1s
- sleep 1.5m (90초)
- sleep 5; pwd;

## cron (How to run a command regularly)

- */1 * * * * date >> date.log
- [분 시 일 월 요일 명령어]

## cron sample

- crontab --help
- crontab -e (create)
- crontab -l (check)
- crontab -r (remove)
- sudo service cron start
- sudo service cron stop
- pgrep cron
- cd ~
- tail -f date.log