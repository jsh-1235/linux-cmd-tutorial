# File Read

## file (determine file type)

- 지정한 파일의 유형을 확인
- text file or binary file
- file *
- file test.txt
- file -i test.txt (파일 문자 코드 확인)
- iconv -f us-ascii -t CP949 test.txt > test_cp949.txt
- iconv -c -f us-ascii -t CP949 test.txt > test_cp949.txt
- file ../../bin/ls
- cat -n ../../bin/ls

## cat (concatenate files and print on the standard output)

- cat file
- cat -n index.html
- cat -b index.html (빈줄은 표시하지 않는다.)
- cat -A index.html (모든 제어 문자를 표시한다.)
- cat > file (Output Redirection)
- cat >> file (Append)

## tac (concatenate and print files in reverse)

- tac backup

## tee (read from standard input and write to standard output and files)

- tee
- cat a1 | tee a2
- ls -al / | tee a1
- dpkg -l | tee a1
- whoami | tee -a a1 (append)

## more (file perusal filter for crt viewing)

- more filename
- more +15 filename
- more +/string filename
- space : next page
- enter : next line
- q : exit

## less (opposite of more)

- less filename
- less -N filename
- 압축 해제 기능 및 메모리만 절약 기능

## head (file perusal filter for crt viewing)

- head filename
- head -n 10 filename (default: 처음부터 10째줄 까지)
- head -n 5 filename (head -n +5 filename, head 5 filename)
- head -n -5 filename
- head -c 40 filename (40 bytes)

- head -n 5 city number (앞의 다섯줄만 보여준다.)
- head -n 5 city number -q (--quiet: never print headers giving file names)

## tail (file perusal filter for crt viewing)

- tail filename
- tail -n 10 filename (default: 끝에서 10째줄 까지)
- tail -n 5 filename (tail -n -5 filename, tail -5 filename)
- tail -n +5 filename (5 ~ end : 앞의 다섯줄은 제외하고 보여준다.)
- tail -n +5 number city -q
- tail -c 40 filename (40 bytes)

- tail -f /var/log/filename (output appended data as the file grows)

## nl (number lines of files)

- nl /etc/sources (cat -b)
- nl a1 a2 a3

- nl -w1 a1
- nl -w6 a1
- nl -w10 a1

- nl -i2 a1
- nl -i2 -v2 a1
- nl -i2 -v2 a1 > a2
- nl a2 | more

## seq (print a sequence of numbers)

- seq 100 100 500
- seq 100 100 500 | nl > a

## split (split a file into pieces)

- alias lh='ls -Alh'
- split -C 3k file
- split -b 1k file
- split -b 1k -d file (use numeric suffixes starting at 0, not alphabetic)
- split -b 1k -d -a 4 file
- split -b 1k -d --additional-suffix=.txt file (append an additional SUFFIX to file names)
- split -b 1k -d --additional-suffix=.txt file backup_
- split -l 100 -d --additional-suffix=.txt file backup_ (줄 단위로 쪼개기)
- wc backup_00.txt
- split -n 10 -d --additional-suffix=.txt file backup_ (똑같이 쪼개기)
- split -n 10 -d --numeric-suffixes=10 --additional-suffix=.txt file backup_ (파일 이름이 10부터 시작)

## csplit (split a file into sections determined by context lines)

- csplit file 100 (100번째 줄을 기준으로 파일을 나눈다.)
- csplit file -f t_ 100
- csplit file 100 200
- csplit file /pattern/
- csplit file /pattern/1
- csplit file /pattern/-1

- csplit -f t_ /etc/services /smtp/
- csplit -f t_ /etc/services /smtp/ {*} (smtp가 들어있는 모든 줄을 기준으로 쪼개기)

## sort (sort lines of text files)

- sort [-tkbrf]
- sort -k 2,3 sorting.txt (지정한 필드 (2~3번째)를 기준으로 정렬한다.)
- sort -r -k 2,3 sorting.txt
- sort north | uniq

## hash (Remember or display program locations.)

- hash

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