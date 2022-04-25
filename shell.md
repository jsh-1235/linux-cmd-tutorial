# Shell

- echo $0
- ls /bin | grep bash
- vi backup.sh
- chmod u+x backup
- chmod +x backup
- ./backup

## Shell Script

```bash
#!/bin/bash
if ! [ -d bak ]; then
  mkdir bak
fi

cp *.log bak
```

```bash
#!/bin/bash

echo "Hello, World!"
```

```bash
#!/bin/bash

read NAME
echo "Hello, $NAME!"
```

```bash
#!/bin/bash

read NAME
echo -e "Hello\n$NAME!"
```

```bash
#!/bin/bash

h="Hello"
w="World"
echo "${h}, ${w}"
```

```bash
#!/bin/bash

echo "parameter: ${0}"
echo "parameter length: ${#}"
echo "parameter length: ${*}"
echo "parameter: ${1}"
echo "parameter: ${2}"
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

sum() {
  echo "result: $1 $2"
  #return $(($1+$1))
  return `expr $1 + $2`
}

ret=$(sum 5 8)

echo "Return value : $ret"
```
