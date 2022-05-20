# Pipeline

- 명령의 실행 결과를 다음 명령의 입력으로 전달
- 리눅스의 명령어를 조합하여 사용

## ls | more

- ls --help | more  (q: exit)
- ls -l /etc | more

## cat | more

- cat result.txt | more

## du | sort | tail

- du /etc | sort -n | tail -n 5

## ls | sort

- ls -al | sort -n
- ls -al | sort -r
- sort north | uniq

## ls | wc

- ls -al | wc
- ls -al | wc -l
- ps -aux | grep jsh | wc -l

## cat | cut (remove sections from each line of files)

- cat /etc/passwd
- cat /etc/passwd | cut -d: -f 1
- cat /etc/passwd | cut -d: -f 1 | wc -l
- grep /bin/bash /etc/passwd | cut -f1 -d:
- grep /bin/bash /etc/passwd | cut -d: -f 1 | wc -l
- alias usercount='grep /bin/bash /etc/passwd | cut -d: -f 1 | sort| wc -l'

## tee (Copy standard input to each FILE, and also to standard output.)

- 파일과 화면 양쪽에 출력하기
- ps | tee pslog
- ps | tee -a pslog
- cat pslog

## xargs (build and execute command lines from standard input)

- 표준 입력에서 인수를 받아서 실행하기
- cat states | xargs echo
- cat states | xargs -n 5 -d '\n' echo
