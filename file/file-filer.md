# File Filter

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

## paste (merge lines of files)

- cat > name
- echo -e "90\n95\n95\n50\n50" > kor
- echo -e "955\n25\n95\n45\n50" > eng
- paste name kor eng
- paste name kor eng -s (serial : paste one file at a time instead of in parallel)
- paste name kor eng > score
- nl score

- paste name -s -d"," (delimiters)
- paste name -s -d"^"
- paste name -s -d"="
- paste name -s -d",^="

## join (join lines of two files on a common field)

- field[column]/record[row]
- join k1 e1
- join -e"00" -o 0,1.2,2.2 k1 e1 (e: replace missing input fields width EMPTY)

## cut (remove sections from each line of files)

- 파일에서 필드 구분자를 이용하여 특정 필드를 추출해 낸다.
- echo 'hello world' | cut -c 1-4

- cut  -d ':' -f 1 /etc/passwd
- cut  -d ':' -f5 /etc/passwd
- cut  -d ':' -f2,4  /etc/passwd

- date | cut -d' ' -f1

- echo {A..Z}
- echo {A..Z} | tr -d ' '
- echo {A..Z} | tr -d ' ' | cut -c1
- echo {A..Z} | tr -d ' ' | cut -c2
- echo {A..Z} | tr -d ' ' | cut -c1,2,3
- echo {A..Z} | tr -d ' ' | cut -c1-10
- echo {A..Z} | tr -d ' ' | cut -c-10
- echo {A..Z} | tr -d ' ' | cut -c10-

- echo {A..Z} | tr -d ' ' | cut -b-5
- echo {A..Z} | tr -d ' ' | cut -b5-

- echo "대한민국화이팅" | cut -c-5

- cat score | cut -f1
- cat score | cut -f2
- cat score | cut -f3
- cat score | cut -f1,2,3
- cat score | cut -f1,3

- cat p | cut -d':' -f3

- ps -ef | cut -d' ' -f1

## sed (stream editor for filtering and transforming text)

- sed -n '1p' score (첫번째 줄만 출력)
- sed -n '1, 3p' score

## awk (pattern scanning and processing language)

- ls -l | awk '{print $9 " " $5}'
- awk -F, '{print $2}' data.csv
- awk -F, '{print $3 / ($2 / 100) ^ 2}' data.csv (BMI 계산)
- awk -F, '{print $2 + $3}' data.csv
- tail /etc/group | awk -F: '{print $1}'

- ps -ef | awk '{print $1}'
- ps -ef | awk '{print $2,3}'
- ps -ef | awk '{print $1, "\t", $3}'
- ps -ef | awk '{print $3, "\t", $1}'

- cat score | awk '{print $1, "님, 국어: ", $2, "영어: ", $3}'
- cat score | awk '{print $1, "\b님, 국어: ", $2, "영어: ", $3}'

## grep (print lines that match patterns)

- 파일에서 특정한 패턴 또는 정규 표현식으로 나타낸 단어를 찾는 명령어이다.
- cat /etc/passwd | grep manager | cut -d ':' -f1,2,6

## sort (sort lines of text files)

- sort [-bfnRrh, -ckmotu]
- sort -k 2,3 sorting.txt (지정한 필드 (2~3번째)를 기준으로 정렬한다.)
- sort -r -k 2,3 sorting.txt
- sort north | uniq (sort -u north)

- ls -al | sort -r
- ls -alh | sort -rh

- nl kor
- sort kor
- sort kor -r
- sort kor -u | nl

- sort kor eng | nl
- sort -m kor eng | nl (정렬하지 않고 파일 병합)
- sort -u kor eng | nl (정렬 후 중복된 내용 제거)

- sort kor eng -o kor2

- sort -k 1 score | nl  (sort via a key; KEYDEF gives location and type)
- sort -k 2 score | nl
- sort -k 3 score | nl

- sort kor -R | nl (해시키값을 기준으로 랜덤 정렬)

- sort -c kor (check for sorted input; do not sort)
- echo $?

- sort -r /etc/passwd | nl
- sort -t: -k 3   /etc/passwd | nl
- sort -t: -k 3 /etc/passwd | awk -F: '{print $1, $3}' | nl (문자 비교)
- sort -t: -k 3 -n /etc/passwd | awk -F: '{print $1, $3}' | nl (숫자 비교)

- ll /var/log
- ll /var/log | sort -k 5 (Error)
- ll /var/log | sort -k 5 -n

- df | sort -k 3
- df | sort -k 3 -h

## uniq (report or omit repeated lines)

- nl bee
- uniq bee | nl
- sort bee | uniq
- uniq -c bee (prefix lines by the number of occurrences)
- uniq -i bee (ignore differences in case when comparing)
- uniq -u bee (only print unique lines)
- uniq -d bee (only print duplicate lines, one for each group)
- uniq -d -c bee
- uniq -D bee (print all duplicate lines)

- uniq -f 2 score (두번째 필드를 기준으로 중복되는 줄은 제외하고 출력)

## shuf (generate random permutations)

- shuf kor
- shuf -e 10 20 30 40 50
- shuf -e 서울 부산 광주 대구 울산 -n 1
- shuf -e 서울 부산 광주 대구 울산 -n 2

- shuf -i 1-10
- shuf -i 1-10 -n 3

- shuf -i 1-45
- shuf -i 1-45 -n 6
- shuf -i 1-45 -n 6 | paste - - -
- shuf -i 1-45 -n 6 -o lotto

- shuf -i 1-10 -r (output lines can be repeated)

## tr (translate or delete characters)

- echo "kbs"
- echo "kbs" | tr -d 'k'

- echo "kkkbbbsss" | tr -d 'k' | nl
- echo "kkkbbbsss" | tr -d 'kbs' | nl

- echo "kbsKBS12345" | tr -d '`kbs123' | nl
- echo "kbsKBS12345" | tr -d 'a-z' | nl
- echo "kbsKBS12345" | tr -d '[:lower:]' | nl
- echo "kbsKBS12345" | tr -d 'A-Z' | nl
- echo "kbsKBS12345" | tr -d '[:upper:]' | nl
- echo "kbsKBS12345" | tr -d 'a-z''A-Z' | nl
- echo "kbsKBS12345" | tr -d '0-9' | nl
- echo "kbsKBS12345" | tr -d '[:digit:]' | nl

- echo {1..9} | tr -d '1-4'

- echo "abc" | tr 'a' 'A' | nl
- echo "aabbcc" | tr 'abc' 'ABC' | nl
- echo "korea" | tr "korea" "KOREA"
- echo "korea" | tr 'a-z' 'A-Z' | nl

- echo "kkkbbbccc" | tr -s kbc
- last | tr -s " "
- df -h | tr -s ' '

- echo "서울 부산 대구 광주" | tr " " "\n"
- echo "서울 부산 대구 광주" | tr " " "\012"
- echo "서울 부산 대구 광주" | tr " " "\v"

- cat /etc/passwd | tr ':' '\t'
- cat /etc/passwd | tr ':' ','

- echo {a..z}
- echo {a..z} | tr '[a-z]' '[A-Z]'
- echo {a..z} | tr '[:lower:]' '[:upper:]'
- echo {a..z} | tr '[a-z]' '[A-Z]' | tr -d ' '

- echo {a..z}{1..3}

- echo {a..z}{1..3} | tr -d ' '
- echo {a..z}{1..3} | tr -d '123'
- echo {a..z}{1..3} | tr -d 'a-z'

- cat /etc/services | tr -d ' '
- cat /etc/services | tr -d '[a-z][A-Z][0-9]'

## expand (convert tabs to spaces)

- echo -e "aa\tbb\tcc"
- echo -e "aa\tbb\tcc" | expand -t 1
- echo -e "aa\tbb\tcc" | expand -t 4
- echo -e "aa\tbb\tcc" | expand -t 8

## unexpand (convert spaces to tabs)

- ps -aux | unexpand -t 4

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

- echo {A..Z}
- echo {a..z}
- echo {1..10}

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

## numfmt (Convert numbers from/to human-readable strings)

- numfmt --grouping 123456789
- numfmt --to=si 1024 (1.1K)
- numfmt --to=iec 1024 (1.0K)

- numfmt --from=si 1G
- numfmt --from=si 1M

- numfmt --from=iec 1G
- numfmt --from=iec-i 1Gi

- echo 1G | numfmt --from=si
- echo 1G | numfmt --from=iec

- df -B1 | numfmt --header --field 2-4 --to=si
- ls -l | numfmt --header --field 5 --to=si
- du -s * | numfmt --to=si --format="%5f"

- du -sh /etc
- du -sh /etc/*
- du -sh /etc/* | sort -n
- du -sh /etc/* | sort -n | numfmt --to=si
- du /etc/* 2>/dev/null | sort -n | numfmt --to=si | tail -5