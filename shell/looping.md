# looping

## expr

- type expr (expr is hashed (/usr/bin/expr))
- 산술 연산 (+, -, *, /, %)
  - expr 10 + 5
  - expr 10 - 5
  - expr 10 '*' 5
  - expr 10 '/' 5
  - expr 10 '%' 4
  - x=1
  - x=$(expr $x + 1); echo $x
  - sum=`expr $x + 10`; echo $sum
- 관계 연산 (=, !=, >, >=, <, <=)
  - x=1
  - expr $x > 0; echo $?
  - expr $x < 0; echo $?
- 논리 연산 (|, &)

## let (산술 연산)

- type let (let is a shell builtin)
- 산술 연산 (+, -, *, /, %)
  - x=1
  - let sum=x+5; echo $sum
  - let x++
  - let x-=1
  - ((sum=x+5))
  - ((sum+))
  - ((x-=1))
- 관계 연산 (=, !=, >, >=, <, <=)
- 논리 연산 (&&, ||)
- bit 연산 (<<, >>)
- 단항 연산 (++. +=, --, -=)

## bc (An arbitrary precision calculator language)

- bc
- scale=5
- (1+1)*5/3
- 3.33333
- quit

```bash
#!/bin/bash
# bc

pi=3.14
r=$1
echo $r '*' $r '*' $pi = `echo "$r * $r * $pi" | bc`
```

## getopts (Parse option arguments.)

```bash
#!/bin/bash

FLAG=0
while getopts ab: OPT
do
  case $OPT in
    a) FLAG=1 ;;
    b) VALUE=$OPTARG ;;
  esac
done
shift `expr $OPTIND - 1`

echo FLAG: $FLAG
echo VALUE: $VALUE
echo '$1: ' $1
```

## while loop

```bash
#!/bin/bash

num=1
while test $num -le 5
do
  echo Number: $num
  ((num++))
done
```

## until loop

```bash
#!/bin/bash

num=1
until test $num -gt 5
do
  echo Number: $num
  ((num++))
done
```

```bash
#!/bin/bash
# Description: Create as user account

echo -n "New username: "
read username
while getent passwd $username &> /dev/null
do
  echo "Sorry, that account $username is already taken. Please pick a different username."
  echo -n "New username: " # The new user will be created using HOME_DIR, The name of the user's login shell.
  read username
done
sudo useradd -m -s /bin/bash $username
# id bt3
# passwd bt3
# login bt3
```

```bash
#!/bin/bash
# Description: Delete user account

echo -n "username to remove: "
read username
until getent passwd $username &> /dev/null
do
  echo "username dose not exist."
  echo -n "username to remove: "
  read username
done
sudo userdel -r $username
```

```bash
#!/bin/bash

num=0
while [ $num -lt 5 ]
do
  echo "Number: $num"
  ((num++))
  if [[ "$num" == '2' ]]; then
    break
  fi
done
```

```bash
#!/bin/bash

i=0

until [ ! $i -lt 5 ]
do
  echo $i
  i=`expr $i + 1`
done
```

```bash
#!/bin/bash

for var in 0 1 2 3 4
do
  echo $var
done
```

```bash
#!/bin/bash

num=1
while [ $num -le 5 ]
do
  echo num is $num
  num=`expr $num + 1`
done
```

```bash
#!/bin/bash
# infinite loop

num=1
while :
do
  echo num is $num

  if [ $num -ge 10 ]
  then
    break
  fi

  num=`expr $num + 1`
done
```
