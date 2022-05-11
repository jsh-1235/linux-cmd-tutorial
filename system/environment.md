# Environment

- 셸 변수는 변수를 설정하는 Shell 에서만 유효하다.
- 환경 변수는 해당 셸에서 실행한 프로세스에도 설정할 수 있다.
- man bash
- echo $BASH
- echo \$BASH (Escape Sequence)
- .bashrc : bash를 시작할 때마다 읽습니다.
- .profile : 로그인할 때 한 번만 읽습니다.
- .bash_logout : 로그아웃할 때 읽습니다.

## env

- env [-iu]
- export NAME=seunghun.jeong (새로운 환경 변수 생성)
- export DEFINENAME (기존 변수를 환경 변수로 설정)
- env LANG=C bash (앞으로 실행할 프로세스와 자식 프로세스에만 유효한 환경 변수 설정)
- env | grep NAME
- echo $NAME
- unset NAME

## .bashrc (환경변수 영구 저장)

- vi ~/.bashrc
- vi /etc/bash.bashrc
- source ~/.bashrc (셸 재시작 없이 설정 파일 내용 반영)

## source (Execute commands from a file in the current shell.)

- source ~/.bashrc

## set & unset

- score=100
- echo $score
- set | grep score
- unset score

## declare (Set variable values and attributes.)

- 현재 유효한 모든 셀 변수를 표시한다.
- declare
- declare | head -n
- declare | grep ^PS1 (PS1으로 시작하는 줄 검색)
- declare | grep ^PATH

## printenv (print all or part of environment)

- 현재 유효한 모든 환경 변수를 표시한다.
- printenv
- printenv | head -n
- printenv | grep ^HOME (PS1으로 시작하는 줄 검색)

## alias (Define or display aliases.)

- alias rm="rm -i"
- alias rm
- alias
- unalias -rm
- unalias -a (설정된 모든 단축어 해제)
- vi ~/.bashrc (설정 저장)
  - alias c=clear
  - alias h=history
