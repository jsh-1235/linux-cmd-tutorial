# Find

## whatis (display one-line manual page descriptions)

- whatis ls

## which (which  returns  the pathnames of the files (or links) which would be executed in the current environment.)

- which date (지정한 명령어의 경로 확인)
- which -a date
- /usr/bin/date

## whereis (locate the binary, source, and manual page files for a command)

- whereis --help
- whereis [-bms] ls
- whereis -B /bin /usr/bin -f crontab

## locate (based in db)

- apt install mlocate
- updatedb
- locate ls
- locate ls -n 10
- locate index.html

## find (search for files in a directory hierarchy)

- find -name file1
- find -name "file*"
- find . -name file1 (현재 디렉토리 이하에서 검색)
- find / -name file1 (루트 디렉토리 이하에서 검색)
- find ~ -name file1 (홈 디렉토리 이하에서 검색)
- find ~ -mtime 1 (하루전에 갱신한 파일 목록 검색)
- find . -name test -exec /bin/rm {} \; (찾아서 삭제)
- find . -user bt1
- find . -user bt1 -ls
- find ~ -regex "./.*\.c$"

## find (type file or directory)

- find -type f
- find -type d
- find ./bin/ -type f
- find ./bin/ -type d
- find . -type f -name "c.log" -exec rm -f {} \;

## grep (grep, egrep, fgrep, rgrep - print lines that match patterns)

- grep [-vnlirs]
- grep s* south
- grep ^Al south
- grep -n ^Ala south
- Regular Expression
- [*.^] (asterisk)
- ls /etc | grep a
- ls -al | grep "f*"
- grep -rl "find text" a.txt b.txt

## uniq (report or omit repeated lines)

- uniq [-udcfsw]
- uniq north
- uniq -u north : 중복되지 않은 줄만 출력한다.
- uniq -d north : 중복된 줄만 표시한다.
- uniq -c north : 중복된 줄 수를 각 줄 옆에 표시한다.

## wc (print newline, word, and byte counts for each file)

- wc [-lwcm]
- wc south
- last | wc
- wc /etc/hosts

## comm (compare two sorted files line by line)

- comm a b

## cmp (compare two files byte by byte)

- cmp a b

## diff ( compare files line by line)

- diff [-irsbwBqu] a b
- diff -u a b (통합 diff[unified diff] 형식으로 출력)
- diff -q a b (파일 내용 일치 여부만 표시한다.)

## type (Display information about command type)

- type cd
- type ls
- type -a ls
