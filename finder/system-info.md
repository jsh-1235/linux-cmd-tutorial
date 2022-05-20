# info

- cat /etc/issue (Check Linux Version)

## history (GNU History Library)

- history
- history 5
- !444
- history -c (delete all)
- history -d 1
- history | awk '{a[$2]++}END{for(i in a){print a[i] " " i}}' | sort -rn | head -10

## timedatectl (timedatectl)

- timedatectl
- timedatectl | grep Time
- timedatectl status
- timedatectl list-timezones (사용 가능한 모든 시간대 출력)
- timedatectl list-timezones |  egrep  -o "Asia/S.*"
- timedatectl set-timezone "Asia/Seoul"
- timedatectl set-timezone UTC
- timedatectl set-time '2015-11-20 16:14:50'

## locale (get locale-specific information)

- locale
- nl /etc/default/locale
- sudo apt -y install language-pack-ko
- sudo update-locate LANG=C.UTF-8 (default)
- sudo update-locale LANG=ko_KR.UTF-8 LC_MESSAGES=POSIX
- logout (session 종료)

## date (print or set the system date and time)

- date (현재 시스템 시간과 날짜를 확인)
- date [MMDDhhmmYY]
- date 0110130021

## cal (displays a calendar and the date of Easter)

- cal
- cal -y
- cal 1983
- cal 10 1983

- ncal

## hwclock (time clocks utility)

- sudo hwclock -r (하드웨어 시간 확인)
- sudo hwclock -s (하드웨어 시간을 시스템 시간에 동기화)
- sudo hwclock -w (시스템 시간을 하드웨어 시간과 동기화)

## rdate (타임 서버와 시스템 시간 동기화)

- rdate -s time.bora.net (time.bora.net의 시간 정보 확인)
- rdate -p time.bora.net (time.bora.net과 시스템 시간 동기화)

## uptime (Tell how long the system has been running.)

- uptime
- uptime -p
- cat /etc/issue

## tty (print the file name of the terminal connected to standard input)

- tty

## uname (print system information)

- uname [-snrvmpio]
- uname -a [시스템명 / 호스트명 / kernel releas /  kernel version / 머신 타입 / 프로세스 타입 / 하드웨어 플랫폼 / OS]
- uname -m (하드웨어 타입 출력)
- uname -n (호스트명 출력)
- uname -r (운영체제 릴리즈 번호 출력)
- uname -s (운영체제 이름 출력)
- uname -v (운영체제 버전 출력)

## arch (print machine hardware name)

- arch (시스템의 CPU에 대한 정보를 확인)

## dmesg (print or control the kernel ring buffer)

- dmesg
- dmesg -c (시스템 메시지를 출력한 수 시스템 버퍼를 비운다.)
- dmesg | grep Memory

## time (run programs and summarize system resource usage)

- time cal
- time date