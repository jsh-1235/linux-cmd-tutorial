# File Read

## file (determine file type)

- 지정한 파일의 유형을 확인 (text file or binary file)

- file *

- file test
- file -i test (파일 문자 코드 확인)

- file /bin/ls
- cat -n /bin/ls

## iconv (convert text from one character encoding to another)

- iconv -l
- iconv -f us-ascii -t CP949 test > test_cp949
- iconv -c -f us-ascii -t CP949 test > test_cp949

## cat (concatenate files and print on the standard output)

- cat test
- cat -n test
- cat -b test (빈줄은 번호를 표시하지 않는다.)
- cat -A test (모든 제어 문자를 표시한다.)
- cat > test (Output Redirection)
- cat >> test (Append)

## tac (concatenate and print files in reverse)

- tac test

## tee (read from standard input and write to standard output and files)

- 표준 입력으로부터 데이터를 읽어 표준 촐력으로 출력하거나 또는 이와 동시에 파일에 저장할 수 있다.
- 표준 출력과 파일 저장을 동시에 수생할 수 있기 때문에 파이프라인을 양 갈래로 나누어 보낼 수 있다.

- tee
- Ctrl + D (exit)

- echo "hello" | tee test

- ls -al / | tee test
- cat test1 | tee test2
- dpkg -l | tee test
- whoami | tee -a test (append)
- uname -a | tee -a test (append)

## more (file perusal filter for crt viewing)

- more test
- space : next page
- enter : next line
- q : exit

- more +10 test (display file beginning from line number)
- more -10 test (the number of lines per screenful)
- more +/string test (display file beginning from search string match)

## less (opposite of more)

- 압축 해제 기능 및 메모리만 절약 기능
- less test
- less -N test

- less +10 test
- less +/string test (key : n, b)

## head (file perusal filter for crt viewing)

- head test
- head -n 10 test (default: 처음부터 10번째줄 까지 표시한다.)
- head -n 10 test (head -n +10 test, head 10 test)
- head -n -10 test (뒤의 10줄을 제외하고 모두 보여준다.)
- head -c 100 test (100 bytes)

- head -n 5 city number (앞의 다섯줄만 보여준다.)
- head -n 5 city number -q (--quiet: never print headers giving file names)

## tail (file perusal filter for crt viewing)

- tail test
- tail -n 10 test (default: 끝에서 10번째줄 까지 표시한다.)
- tail -n 10 test (tail -n -10 test, tail -10 test)
- tail -n +10 test (앞의 10줄을 제외하고 모두 보여준다.)
- tail -n +5 number city -q
- tail -c 40 test (40 bytes)

- tail -f /var/log/test (output appended data as the file grows)

## nl (number lines of files)

- nl /etc/sources (cat -b /etc/sources)
- nl test1 test2 test3
- nl test | more

- nl -w1 test
- nl -w6 test (use NUMBER columns for line numbers)
- nl -w12 test

- nl -i2 test (line number increment at each line)
- nl -i2 -v2 test (first line number for each section)
- nl -i2 -v2 test1 > test2

## seq (print a sequence of numbers)

- seq 100 100 500
- seq 100 100 500 | nl > test

## split (split a file into pieces)

- alias lh='ls -Alh'

- split -l 100 test (줄 단위로 쪼개기)
- split -l 100 -d --additional-suffix=.txt test backup_
- wc *

- split -n 10 -d --additional-suffix=.txt test backup_ (똑같이 쪼개기)
- split -n 10 -d --numeric-suffixes=10 --additional-suffix=.txt test backup_ (파일 이름이 10부터 시작)

- split -C 3k test (put at most SIZE bytes of records per output file)

- split -b 1k test
- split -b 1k -d test (use numeric suffixes starting at 0, not alphabetic)
- split -b 1k -d -a 4 test
- split -b 1k -d --additional-suffix=.txt test (append an additional SUFFIX to file names)
- split -b 1k -d --additional-suffix=.txt test backup_
- wc *

## csplit (split a file into sections determined by context lines)

- csplit test 100 (100번째 줄을 기준으로 파일을 나눈다.)
- csplit test 100 200 300
- csplit test 100 200 300 -f t_
- csplit test /pattern/
- csplit test /pattern/1
- csplit test /pattern/-1

- csplit -f t_ /etc/services /smtp/
- csplit -f t_ /etc/services /smtp/ {*} (smtp가 들어있는 모든 줄을 기준으로 쪼개기)

- csplit -f c_ chapter /chapter/ {*}
- head c_*

## sort (sort lines of text files)

- sort [-tkbrf]
- sort -k 2,3 sorting.txt (지정한 필드 (2~3번째)를 기준으로 정렬한다.)
- sort -r -k 2,3 sorting.txt
- sort north | uniq

## cut (remove sections from each line of files)

- 파일에서 필드 구분자를 이용하여 특정 필드를 추출해 낸다.
- echo 'hello world' | cut -c 1-4
- cut  -d ':' -f 1 /etc/passwd
- cut  -d ':' -f5 /etc/passwd
- cut  -d ':' -f2,4  /etc/passwd

## sed (stream editor for filtering and transforming text)

- echo hello world | sed -e "s/world/jsh"
- ls *.txt | sed s/\.txt$//

## awk (pattern scanning and processing language)

- ls -l | awk '{print $9 " " $5}'
- awk -F, '{print $2}' data.csv
- awk -F, '{print $3 / ($2 / 100) ^ 2}' data.csv (BMI 계산)
- awk -F, '{print $2 + $3}' data.csv
- tail /etc/group | awk -F: '{print $1}'

## grep (print lines that match patterns)

- 파일에서 특정한 패턴 또는 정규 표현식으로 나타낸 단어를 찾는 명령어이다.
- cat /etc/passwd | grep manager | cut -d ':' -f1,2,6

## echo (display a line of text)

- type echo (echo is a shell builtin)
- help echo (--help)

- pi=3.14
- echo pi
- set | grep pi

- echo $USER
- echo $HOSTNAME
- echo $HISTSIZE (env)

- echo -n $USER (줄바꿈을 하지 않는다.)

- echo -e "aa \t bb \t cc" (enable interpretation of backslash escapes)
- echo -e "\uAC01"
- echo -e "\u2665"

## compgen

- compgen -b | column

## column (columnate lists)

- cat test | column

## printf (Formats and prints ARGUMENTS under control of the FORMAT.)

- man 1 printf
- man 3 printf

- a=100;b=3.14;c=korea
- printf "%d \t %f \t %s\n" $a $b $c
- printf "\u2665 \u2666 \u2667 \u2668 \n"
- printf "%d %o %x \n" 12 12 12
- printf "[%10d]\n" 100 (좌측 정렬)
- printf "[%-10d]\n" 100 (우측 정렬)
