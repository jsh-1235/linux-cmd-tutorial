# Find


## type (Display information about command type.)

- type [-atp] cat
- type -t cat (지정한 명령어 종류 표시)
- type ls
- type -a ls (display all locations containing an executable named NAME)

## apropos (search the manual page names and descriptions)

- man page 설명에서 지정한 키워드를 포함하고 있는 명령어이다.
- whatis 데이터베이스에서 포함하는 문자열을 검색한다.
- whatis 데이터이스가 만들어져 있어야 이 명령어를 쓸 수 있다.

- apropos dir
- apropos -e dir (search each keyword for exact match)

## locate (based in db)

- apt install mlocate
- updatedb
- locate ls
- locate ls -n 10
- locate index.html

## find (name)

- find . -name file1 (현재 디렉토리 이하에서 검색)
- find / -name file1 (루트 디렉토리 이하에서 검색)
- find ~ -name file1 (홈 디렉토리 이하에서 검색)
- find /usr /home /tmp -name "*.jar" 2> /dev/null

- b : block device (buffered) special
- c : character device (unbuffered) specail
- p : named pipe (FIFO)
- s : socket

## find (regx)

- find ~ -regex "./.*\.c$"
- find ~ -name "file*"
- find . -name '[r,a][c,d]*' -print
- find /usr -name '[a-z]???' -print

## find (user)

- find . -user manager
- find . -user manager -ls

## find (group)

- sudo find . -type f -group manager
- find . -type d -gid 1001
- find . -type f -gid 1001

## find (mtime)

- find ~ -mtime 1 (하루전에 갱신한 파일 목록 검색)

## find (exec)

- find . -name file1 -exec /bin/rm {} \; (찾아서 삭제)
- find . -type f -name "file1" -exec rm -f {} \;
- find . –name file1 –exec ls –al {} \;

- find / -type l -exec ls -al {} \; 2> /dev/null (link)
- find / -type s -exec ls -al {} \; 2> /dev/null (socket)
- find / -type p -exec ls -al {} \; 2> /dev/null (pipe)

## find (type)

- find ./bin/ -type d
- find ./bin/ -type f
- find ./bin/ -type l

## find (inum)

- find . -inum 1105

## find (size)

- find / -size +5M 2> /dev/null
- find . -size 0 -exec mv {} ./zeros \;

## find (perm)

- find . -type f -perm a=rwx
- find . -type f -perm 777 -exec ls -l {} \;

## grep (grep, egrep, fgrep, rgrep - print lines that match patterns)

- grep [-vnlirs]

- option
  - grep -c a rc (검색 결과를 출력하는 대신, 찾아낸 행의 총 수를 출력한다.)
  - grep -h a rc (파일 이름을 출력하지 않는다.)
  - grep -i a rc (대소문자를 구분하지 않는다.)
  - grep -n a rc (파일 내에서 행 번호를 함께 출력한다.)
  - grep -s a rc (에러 메시지 외에 출력하지 않는다.)
  - grep -v a rc (패터이 존재하지 않는 행만 출력한다.)
  - grep -w a rc (패터 표현식을 하나의 단어로 취급하여 검색한다.)
  - grep -in a rc
  - grep -inv a rc

- 정규 표현식 (Regular Expression)
  - grep -i a* rc
  - grep ^a rc (시작이 Al로 시작하는 문자열)
  - grep 1$ rc
  - grep -rl "find text" a.txt b.txt

- Pipeline
  - ls /etc | grep a
  - ls -al | grep "f*"
  - cat rc | grep -i a

- find ~ -name rc -exec ls -al {} \;
- find ~ -name rc -exec grep a {} \;

## egrep (확장 정규 표현식을 통하여 더 다양한 패턴 검색)

- cat rc | egrep -i a
- egrep '(a|b)' rc

## fgrep (정규식을 사용하지 않고 입력한 패턴 그대로 인식)

- grep '^a' rc
- fgrep '^a' rc

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
- wc -c file1 (print the byte counts)
- wc -m file1 (print the character counts)
- wc -l file1 (print the newline counts)
- wc -w file1 (print the word counts)
- wc -L file1 (print the maximum display width)

## comm (compare two sorted files line by line)

- 두 개의 파일의 행과 행을 비교하여 출력하는 명령이다.
- comm a b

## cmp (compare two files byte by byte)

- 두 개의 파일을 바이트(문자) 단위로 비교하여 출력하는 명령어다.
- cmp a b

## diff ( compare files line by line)

- 두 개의 파일을 행 단위로 비교하여 다른 부분을 출력하는 명령어이다.
- diff [-irsbwBqu] a b
- diff -u a b (통합 diff[unified diff] 형식으로 출력)
- diff -q a b (파일 내용 일치 여부만 표시한다.)
- diff -c a b (두 파일간 다른 부분을 !을 통해 표시해준다.)