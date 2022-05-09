# Input & Output

## echo

- print text to standard output
- echo -n (줄바꿈 방지)
- echo -e (backslash escape: \t \n \a)
- echo -e "First/tSecond\n\a"

## read

- reads text from standard input
- read name
- n : 지정한 문자수만큼 입력 받는다.
- t : 지정한 시간안에 입력 받는다.
- s : 입력하는 글자가 보이지 않는다. (silent mode)
- read name score
- echo $name $score
- read -t10 -n8 pw
- read -t10 -n8 -s pw
- echo $pw
- echo -n "Input your name : "; read name; echo $name

## printf

- 서식 있는 출력 (formatting)
- %d or %i : Number
- %s : string
- %f : floating point number
- printf "Hello linux shell\n"
- printf "Name: %s\tScore: %i\n" jsh 100
- today=`date +%Y%m%d`
- printf "date is %s\n" $today
- printf "number is %.3f\n" 3.147169
- printf "|%10s|%10s|%10.2f\n" ubuntu jsh 10
- printf "|%-10s|%-10s|%-10.2f\n" ubuntu jsh 10

## shell programming

```bash
#!/bin/bash
#: Title        : Sample bash script
#: Date         : 2022-05-09
#: Author       : "jsh"
#: Version      : 1.0
#: Description  : sample shell
echo -n "Input a directory name : "
read dirname
echo "=========================================="
date +%Y-%m-%d
echo "=========================================="
du -sh $dirname 2> /dev/null
echo
```
