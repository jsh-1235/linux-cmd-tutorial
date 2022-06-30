# memory

## free (Display amount of free and used memory in the system)

- free
- free [-bkmg]

- free -h (Show all output fields automatically scaled to shortest three digit unit and display the units of print out.)
  - B = bytes
  - Ki = kibibyte
  - Mi = mebibyte
  - Gi = gibibyte
  - Ti = tebibyte
  - Pi = pebibyte

- free -t (Display a line showing the column totals.)

## vmstat (Report virtual memory statistics)

- 메모리 사용을 실시간으로 출력한다.

- vmstat [options] [delay [count]]
- vmstat 5 4 (메모리 사용량을 5초에 한번식 4번 출력한다.)

- vmstat -s (event counter statistics)
- vmstat -d (disk statistics)
- vmstat -D (summarize disk statistics)
- vmstat -p /dev/sda1 (partition specific statistics)
