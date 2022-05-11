# Positional Parameter

- 위치 매개변수
- $0 : name of shell script
- $1 : first argument
- $2 : second argument
- ${10} ~ ${N}
- $# : Number of arguments
- $@,$* : List of all parameters

## Special shell variables

- $$ : 로그인 shell의 PID
- ps -f
- kill -9 $$
- $PWD : 현재 작업 디렉토리
- echo $PWD
- $PPID : 부모 프로세서 ID
- echo $PPID

## Shell Programming

```bash
#!/bin/bash
echo "This script name : $0"
echo "This first argument : $1"
echo "This second argument : $1"
echo "The number of arguments : $#"
echo "This list of argument : $@"
echo "This list of argument : $*"
echo "Line number : $LINENO"
cho "PWD : $PWD"
echo "PID : $$"
echo "PPID: $PPID"
```

```bash
#!/bin/bash
echo "=========================================="
echo $PWD
echo $0
pos=$(date +%Y%m%d).txt
ls -al $1 > ./$pos
cat $pos
```
