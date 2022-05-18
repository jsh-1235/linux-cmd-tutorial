# Shell

- 사용자 명령어 해석기
- 사용자가 프롬프트에 입력한 명령을 해석해서 운영체제 커널에게 전달
- Bourne shell (sh) : Original Shell
- C Shell (csh, tsch)
- Korn Shell (ksh)
- Bourne-again Shell (bash) : GNU Project (csh, ksh 기능 포함)

## Find shells

- cat /etc/shells (List of currently available shells)
- eche $SHELL (Current Shell)

## chsh (change login shell)

- sudo chsh jsh
- chsh -s /bin/bash
- /bin/sh
- sudo grep jsh /etc/passwd
- jsh:x:1000:1000:,,,:/home/jsh:/bin/sh

## Shell Variable

- 변수명 : 문자, 숫자, _
- score=100 (Be careful with spacing)
- set
- echo $score
- set | grep score
- unset score

## Environment Variable

- 구동되는 프로그램에게 영향을 주는 변수
- 대문자로 작성
- printenv
- env
- echo $HOME
- echo $USER
- echo $SHELL
- echo $PATH
- export FNAME=seunghun.jeong
- echo $FNAME
- env | grep FNAME

## Meta Characters

- \ ? () $ ... * % {} []
- touch file{1..5}
- echo *
- echo f*
- echo file?

## Quoting Rule (메타문자의 의미를 제거하고 단순 문자로 변경)

- Backslash (\) : \  바로 뒤의 메타 문자의 특별한 의미를 제거한다.
- Double Quotes("") : "" 내의 모든 메타 문자의 의미 제거, 단 $, ``은 제외
- Single Quotes('') : '' 내의 모든 문자의 의미 제거
- touch '***'
- touch "**"
- touch \?\?\?
- touch my\*name
- touch "This is a file"
- touch '  '

## Nesting Command

- echo "Today is $(date)"
- date +%Y%m%d
- echo "today is $(date +%Y%m%d)"
- touch report-$(date +%Y%m%d)_v1
- touch report-$(date +%Y%m%d)_v2

## Alias

- Shell의 명령에 새로운 이름을 부여
- 명령들을 조합하여 새로운 이름을 부여
- alias or alias name
- alias name="command"
- alias rm="rm -i"
- alias rm
- unalias name
- unalias -a (설정된 모든 단축어 해제)
- vi ~/.bashrc (설정 저장)
  - alias c=clear
  - alias h=history

## Shell Prompt

- \h : Host name
- \u : User name
- \w : Working directory (절대 경로)
- \W : Working directory (상대 경로)
- \d : 오늘 날짜 (Today)
- \t : 현재 시간
- \$ : $ or # (Prompt 모양)
- echo $PS1
- vi ~/.bashrc (설정 저장)
  - PS1='\u@\h:\W\$ '