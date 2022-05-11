# info

## history (GNU History Library)

- history
- history 5
- !444
- history -c (delete all)
- history -d 1
- history | awk '{a[$2]++}END{for(i in a){print a[i] " " i}}' | sort -rn | head -10

## help

- ls --help

## man (an interface to the system reference manuals)

- man ls
- man ls | grep 'sort'
- man ls | grep 'sort' | grep 'file'
- /search (navigation => n : forward, b: backward)

## date (print or set the system date and time)

- date
- sudo date 051013092022 [월일시분년도.초]

## cal (displays a calendar and the date of Easter)

- cal
- cal -y
- cal 1983
- cal 10 1983

## uptime (Tell how long the system has been running.)

- uptime
- uptime -p

## uname (print system information)

- uname [-snrvmpio]
- uname -a [시스템명 / 호스트명 / kernel releas /  kernel version / 머신 타입 / 프로세스 타입 / 하드웨어 플랫폼 / OS]

## dmesg (print or control the kernel ring buffer)

- dmesg
- dmesg -c (시스템 메시지를 출력한 수 시스템 버퍼를 비운다.)
- dmesg | grep Memory
