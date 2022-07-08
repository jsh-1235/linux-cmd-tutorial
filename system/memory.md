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

## sync (Synchronize cached writes to persistent storage)

- 메모리상의 데이터들 하드 디스크에 기록한다.
- 리눅스 운영체제는 시스템의 효율성 향상을 위해서 상대적으로 속도가 느린 하드 디스크로의 접근 횟수를 최소화한다.
- 발생된 데이터를 하드 디스크에 바로 기록하는 것이 아니라 메모리상에 먼저 기록하게 된다.
- 이 때 메모리상의 데이터와 하드 디스크상의 파일의 내용을 서로 정합(synchronize)시키는 명령이 sync이다.