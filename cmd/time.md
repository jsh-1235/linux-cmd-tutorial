# time & date

## date (print or set the system date and time)

- date (Display the current time in the given FORMAT, or set the system date.)
- date 0110130021 (MMDDhhmmYY)

## timedatectl (Control the system time and date)

- timedatectl
- timedatectl | grep Time
- timedatectl status
- timedatectl list-timezones (사용 가능한 모든 시간대 출력)
- timedatectl list-timezones |  egrep  -o "Asia/S.*"
- timedatectl set-timezone "Asia/Seoul"
- timedatectl set-timezone UTC
- timedatectl set-time '2015-11-20 16:14:50'

## hwclock (time clocks utility)

- sudo hwclock -r (display the RTC time)
- sudo hwclock -s (set the system time from the RTC)
- sudo hwclock -w (set the RTC from the system time)

## rdate (set the system's date from a remote host)

- rdate time.bora.net (time.bora.net의 시간 정보 확인)
- rdate -p time.bora.net (time.bora.net과 시스템 시간 동기화)

## cal (displays a calendar and the date of Easter)

- cal
- cal -y
- cal 1983
- cal 10 1983

## ncal (displays a calendar and the date of Easter)

- ncal
- ncal 10 1983
