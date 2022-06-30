# Command

## coreutils

- info coreutils
- info coreutils | less

## compgen

- compgen -a | column (alias)
- compgen -k | column (Keyword)
- compgen -b | column (builtin-command)
- compgen -A function

## enable (Enable and disable shell builtins.)

- 내부 명령어 (bash에 포함된 명령어)
- echo $SHELL
- help enable

- enable
- enable | nl
- enable | column
- enable | nl | column

## Internal Command (builtin-command)

- shell에 포함된 명령어
  - echo $SHELL

- compgen -b | nl
- compgen -b | wc
- compgen -b | column

- type pwd
  - pwd is a shell builtin

## External Command

- type tree
  - tree is /usr/bin/tree

## function

- greeting() { echo 'hi'; }
- greeting
- type greeting (greeting is a function)

- set | grep 'greeting ()'
- compgen -A function | column | grep greeting

## which (which  returns  the pathnames of the files (or links) which would be executed in the current environment.)

- 환경변수 PATH 에 지정되어 있는 경로만을 검색하여 요청한 명령어가 있는지 알려준다.
- which date (지정한 명령어의 경로 확인)
- which -a date
- /usr/bin/date

## whereis (locate the binary, source, and manual page files for a command)

- whereis --help
- whereis [-bms] ls
- whereis -B /bin /usr/bin -f crontab

## type (Display information about command type.)

- type tree
- type -a tree (display all locations containing an executable named NAME)
- type -f tree (suppress shell function lookup)