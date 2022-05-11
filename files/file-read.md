# File Read

## file (determine file type)

- text file or binary file
- file *
- file test.txt
- file -i test.txt (파일 문자 코드 확인)
- iconv -f us-ascii -t CP949 test.txt > test_cp949.txt
- iconv -c -f us-ascii -t CP949 test.txt > test_cp949.txt
- file ../../bin/ls
- cat -n ../../bin/ls

## cat (concatenate files and print on the standard output)

- cat backup
- cat -n index.html
- cat -b index.html (빈줄은 표시하지 않는다.)
- cat -A index.html (모든 제어 문자를 표시한다.)

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
- head -n filename
- head -n 5 filename
- head -5 filename

## tail (file perusal filter for crt viewing)

- tail filename
- tail -n filename
- tail -n 5 filename
- tail -5 filename
- tail -f /var/log/filename

## sort (sort lines of text files)

- sort [-tkbrf]
- sort -k 2,3 sorting.txt (지정한 필드 (2~3번째)를 기준으로 정렬한다.)
- sort -r -k 2,3 sorting.txt
- sort north | uniq

## type (Display information about command type.)

- type [-atp] cat
- type -t cat (지정한 명령어 종류 표시)
- type ls
- type -a ls

## hash (Remember or display program locations.)

- hash

## cut (remove sections from each line of files)

- echo 'hello world' | cut -c 1-4

## sed (stream editor for filtering and transforming text)

- echo hello world | sed -e "s/world/jsh"
- ls *.txt | sed s/\.txt$//

## awk (pattern scanning and processing language)

- s -l | awk '{print $9 " " $5}'
- awk -F, '{print $2}' data.csv
- awk -F, '{print $3 / ($2 / 100) ^ 2}' data.csv (BMI 계산)
- awk -F, '{print $2 + $3}' data.csv
- tail /etc/group | awk -F: '{print $1}'
