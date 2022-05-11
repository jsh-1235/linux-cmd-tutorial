# branching

## exit

- 실행된 프로그램이 종료된 상태를 전달한다.
- 0 : 프로그램 또는 명령이 성공적으로 종료했음을 의미한다.
- 1 - 255 : 프로그램 또는 명령이 실패했음을 의미한다.
  - 1 : 일반적인 오류
  - 2 : 문법 오류 (Syntax error)
  - 126 : 명령을 실행할 수 없음
  - 127 : 명령 또는 파일이 존재하지 않음
  - 128 + N : 종료 시그널 + N (kill -9 PID로 종료 시 128+ 9 = 137)
- $? : 종료값 출력

- date > /dev/null
- echo $?
- cp file1 [file2]
- echo $?
- sleep 100
- ctrl+c
- echo $?

## test

- help test
- [eq/ne/lt/le/gt/ge/]
- 0 : True, 1 : False
- x=10
- test $x -eq 5; echo $?
- test $x -ne 5; echo $?
- test $x -lt 5; echo $?
- test $x -le 5; echo $?
- test $x -gt 5; echo $?
- test $x -ge 5; echo $?
- test -e /etc/passwd; echo $? (FILE exists)
- test -d /etc/passwd; echo $? (FILE exists and is a directory)
- test -f /etc/passwd; echo $? (FILE exists and is a regular file)

## if-then-fi & if-then-else-fi

```bash
#!/bin/bash

echo $0
x=$1
if test $x -gt $2
then
  printf "%d is greater than %d" $1 $2
else
  printf "%d is less than or equal to %d" $1 $2
fi
echo
```

```bash
#!/bin/bash

echo $0
x=$1
if [ $x -gt $2 ]
then
  printf "%d is greater than %d" $1 $2
else
  printf "%d is less than or equal to %d" $1 $2
fi
echo
```

```bash
#!/bin/bash

echo -n "input numbers "
read x y
if [ $x -gt $y ]
then
  printf "%d is greater than %d" $x $y
else
  printf "%d is less than or equal to %d" $x $y
fi
echo
```

```bash
# !/bin/bash

echo -n "input numbers "
read x y
if [ $x -eq $y ]
then
  printf "%d is equal %d" $x $y
else
  if [ $x -gt $y ]
  then
    printf "%d is greater than %d" $x $y
  else
    printf "%d is less then %d" $x $y
  fi
fi
echo
```

```bash
# !/bin/bash

if test -e /etc/passwd
then
  ls -l /etc/passwd
else
  echo "/etc/passwd file does not exist!"
fi
```

```bash
# !/bin/bash

echo -n "What do you want?"
read answer
case $answer in
  yes) echo "System restart.";;
  no) echo "Shutdown the system";;
  *) echo "entered incorrectly";;
esac
```

```bash
# !/bin/bash

echo -n "What do you want?"
read answer
case $answer in
  [yY]es) echo "System restart.";;
  [nN]o) echo "Shutdown the system";;
  *) echo "entered incorrectly";;
esac
```

```bash
# !/bin/bash

cat << END
=================================
Please select a number
---------------------------------
1: Check disk usage
2: Check the login user list
---------------------------------
END
echo -n "number: "
read number
case $number in
  1) df -h ;;
  2) whoami ;;
  *) echo "Bad choice"
     exit 1
esac
exit 0
# echo "result: $?"
```

```bash
# !/bin/bash

echo -n "Input a directory name: "
read dirname
if test -d $dirname
then
  ls -l $dirname > ./temp/$(date +%Y%m%d).txt
else
  echo "/etc/passwd file does not exist!"
fi
```

```bash
# !/bin/bash

a=20
b=30

if [ $a -gt $b ]
then
  echo "a > b"
else
  echo "a <= b"
fi
```

```bash
#!/bin/bash

if ! [ -d bak ]; then
  mkdir bak
fi

cp *.log bak
```
