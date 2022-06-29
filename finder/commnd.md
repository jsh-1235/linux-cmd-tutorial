# Command

## coreutils

- info coreutils
- info coreutils | less

## alias

- compgen -a | column

## Keyword

- compgen -k | column

- time ls -al /etc
- type time
  - time is a shell keyword

## function

- greeting() { echo 'hi'; }
- greeting
- type greeting (greeting is a function)

- set | grep 'greeting ()'

## Internal Command (builtin-command)

- shell에 포함된 명령어
- echo $SHELL

- compgen -b | nl
- compgen -b | wc
- compgen -b | column

- enable
- enable | nl
- enable | column

- type pwd
  - pwd is a shell builtin

## External Command

- type tree
  - tree is /usr/bin/tree

## type (Display information about command type.)

- type tree
- type -a tree (display all locations containing an executable named NAME)
- type -f tree (suppress shell function lookup)

## which (which  returns  the pathnames of the files (or links) which would be executed in the current environment.)

- 환경변수 PATH 에 지정되어 있는 경로만을 검색하여 요청한 명령어가 있는지 알려준다.
- which date (지정한 명령어의 경로 확인)
- which -a date
- /usr/bin/date

## whereis (locate the binary, source, and manual page files for a command)

- whereis --help
- whereis [-bms] ls
- whereis -B /bin /usr/bin -f crontab

## .profile

```bash
if [ -n "$BASH_VERSION" ]; then
    # include .bashrc if it exists
    if [ -f "$HOME/.bashrc" ]; then
      . "$HOME/.bashrc"
    fi
fi
```

## .bashrc

- vim .bashrc
- . .profile
- source .profile (Execute commands from a file in the current shell.)

- bash (child shell)
  - bash
    - bash
    - pstree
    - exit
  - pstree
  - exit

## .bash_logout

- vim .bash_logout

```bash
echo "Good bye !!!" >> bye
```

- logout
  - cat bye

## .bash_history

- echo $HISTSIZE
- HISTSIZE=2000
- set | grep HISTSIZE

- vim .bash_history
- history -a (append history lines from this session to the history file)
- 0>.bash_history

## user

- 관리자
  - root:x:0:0:root:/root:/bin/bash

- 시스템 사용자
  - mail:x:8:8:mail:/var/mail:/usr/sbin/nologin

- 일반 사용자
  - jsh:x:1000:1000:admin:/home/jsh:/bin/bash