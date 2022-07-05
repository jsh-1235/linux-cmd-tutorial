# daemon

- 항상 동작하는 프로세스를 데몬이라고 한다.
- 일부로 끄지 않는 한 Shutdown 할 때까지 계속 동작한다.

## sleep (delay for a specified amount of time)

- sleep 1s
- sleep 1m
- sleep 1m 1s
- sleep 1.5m (90초)
- sleep 5; pwd;

## crop

- 관리자가 원하는 작업을 예약해 두고 정해진 시간에 주기적으로 반복하여 실행할 수 있다.
- 주기적인 서버의 백업이나 로그를 관리할 때 유용하다.

## cron (How to run a command regularly)

- */1 * * * * date >> date.log
- [분 시 일 월 요일 명령어]

## example

- crontab --help
- crontab -e (create)
- crontab -l (check)
- crontab -r (remove)

- sudo service cron start
- service --status-all | grep cron
- ps -ef | grep crond
- pgrep cron (look up or signal processes based on name and other attributes)
- sudo service cron stop

- cd ~
- tail -f date.log
- ctrl + z
- bg %%
- fg %%
- kill %n
- kill -KILL 1025(PID)
