# info

- cat /etc/issue (Check Linux Version)

## uname (print system information)

- uname [-snrvmpio]
- uname -a [kernel name / hostname / kernel release /  kernel version /  machine hardware name /processor type /  hardware platform / OS]

- uname -s (print the kernel name)
- uname -n (print the network node hostname)
- uname -r (print the kernel release)
- uname -v (release)
- uname -m (print the machine hardware name)
- uname -p (print the processor type (non-portable))
- uname -i (print the hardware platform (non-portable))
- uname -o (print the operating system)

## arch (print machine hardware name)

- arch (시스템의 CPU에 대한 정보를 확인)

## tty (print the file name of the terminal connected to standard input)

- tty

cat /etc/issue (Check Linux Version)

## dmesg (print or control the kernel ring buffer)

- 시스템이 부팅할 때 기록된 메시지와 부팅 후 시스템이 기록하고 있는 로그 메시를 출력한다.
- /var/log/dmesg

- dmesg | less
- dmesg --kernel (display kernel messages)
-
- dmesg -l err (restrict output to defined levels)
- Supported log levels (priorities):
  - emerg - system is unusable
  - alert - action must be taken immediately
  - crit - critical conditions
  - err - error conditions
  - warn - warning conditions
  - notice - normal but significant condition
  - info - informational
  - debug - debug-level messages

- dmesg -C (clear the kernel ring buffer)
- dmesg | grep Memory

## uptime (Tell how long the system has been running.)

- uptime
- uptime -p (show uptime in pretty format)

## hostname (show or set the system's host name)

- hostname

## domainname (show or set the system's NIS/YP domain name)

- domainname

## ypdomainname (show or set the system's NIS/YP domain name)

- ypdomainname

## nisdomainname (show or set the system's NIS/YP domain name)

- nisdomainname

## dnsdomainname (show the system's DNS domain nam)

- dnsdomainname
