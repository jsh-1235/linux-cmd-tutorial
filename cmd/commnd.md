# Command

## 명령행의 연결

- ls -al
  - ls \
  - -al

## semi-colon (;)

- mkdir web; cd web; pwd
- date; whoami

## && (Condition Command, Logical And)

- 앞의 명령어 성공한 경우에만 다음 명령어를 실행한다.
- ls /usr/bin/id && id root

## || (Condition Command, Logical Or)

- 앞의 명령어 성공하면 그 결과를 출력하고, 실패하면 그 다음 명령어를 실행한다.
- ls file.txt || touch file.txt
- ls file.txt 2> error.txt || touch file.txt
- data || whoami
- data 2> error || whoami

## time (run programs and summarize system resource usage)

- type time
  - time is a shell keyword

- time ls -al /etc

- time cal
- time date
