# Bash Shell Script

- 리눅스 명령어들을 모아 놓은 ASCII Text File
- 실행 퍼미션을 할당해야 실행 가능하다.
- '#' : Commit
- '#!/bin/bash' : '#!' (shebang, hashbang)
- Shell 구문은 기본 top-down 방식으로 해석해서 실행된다.
- Sub Shell을 포함할 수 있다.

## Sub Shell

- pwd (/home/jsh) (login shell)
- ls -al /bin/bash
- /bin/bash (실행) (sub shell)
- ps -aux
- cd /proc/
- pwd (/proc)
- exit
- pwd (/home/jsh)

## sample

- vi test.sh

```bash
#!/bin/bash
#: Title        : Sample bash script
#: Date         : 2022-05-09
#: Author       : "jsh"
#: Version      : 1.0
#: Description  : sample shell
echo "=========================================="
echo "Today is $(date +%Y-%m-%d)"
echo "=========================================="
df -h /
```

- sh test.sh
- ls -al test.sh
- chmod +x test.sh
- ./test.sh

## Environment settings

- mkdir bin
- cd bin
- echo $PATH
- export PATH=$PATH:~/bin
- echo $PATH | grep /home/jsh/bin
- cat  ~/.bashrc

## samples

```bash
#!/bin/bash
sum=$(($1+$2))
echo "$1 + $2 =  $sum"
```

```bash
#!/bin/bash
echo "[/var Directory]"
echo "=========================================="
echo "Today is $(date +%Y-%m-%d)"
echo "=========================================="
du -sh $1 2> /dev/null
echo
```

```bash
#!/bin/bash
echo "=========================================="
ls -al . > ~/tmp/$(date +%Y%m%d).txt
echo "=========================================="
```

```bash
# !/bin/bash

echo "Hello"
sleep 5
echo "Bye"
```
