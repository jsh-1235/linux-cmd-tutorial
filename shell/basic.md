# Shell의 유형

- 본셸 계열
  - sh (bourne shell, 1922)
    - 1971년 유닉스 최초의 셸이었던 톰프슨 셸 대체
  - ksh (korn shell, 1983)
    - 명령어 히스토리 기응
    - 별칭(alias) 기능
    - 작업 제어 기능 추가
    - 명령행 편집 기능
  - bash (bourne again shell, 1989)
    - GPL v3
    - sh + ksh + csh
    - 디렉토리 스택, 명령어 치환, 명령어 자동 완성 기능

- C셸 계열
  - csh (C shell, 1978)
    - C 언어를 기반으로 강력한 프로그래밍 기능 제공
    - 히스토리, 별명, 작업 제어 기능 등
  - tsch (TC shell, 1981)
    - 티넥스 (Tenex) 시스템의 명령줄 완성 기능과 명령줄 편집 기능의 영향을 받아 tsch 개발
    - csh와 호환

- 로그인 셸
- 비로그인 셸
- Interactive Shell
- Non-interactive Shell (#!/bin/bash)

## Shell의 설정 및 확인

- echo $SHELL : 현재 로그인한 사용자의 셸 확인
- cat /etc/shells : 시스템이 지원하는 셸 목록 확인
- cat /etc/passwd : 모든 사용자의 셸 확인
- cat /etc/passwd | grep root : 특정 사용자의 셸 확인

## Shell의 변경

- chsh -s /bin/csh

## 환경 변수

- env

- echo $HOME
- printenv HOME
- export JOY="I am happy."
- echo $JOY

- echo $PATH
- export PATH=/coding:$PATH

- ./
- sh test.sh

## 셸의 설정 파일

- 시스템 설정 파일
  - /etc/profile : 시스템 전역으로 설정할 수 있는 셸 설정 파일이다.
  - /etc/profile.d/* : 사용자가 로그인 할 때 /etc/profile.d 디렉토리 안에 있는 모든 셸 스크립트를 실행한다.
  - /etc/bashrc : 시스템 전역의 성격을 갖고 있으며 셸에서 또 다른 셸을 실행하는 비로그인 셸을 실행할때 마다 로드되는 파일이다.

- 사용자 설정 파일
  - ~/.bash_profile or ~/.bash_login
    - 사용자가 시스템에 로그인할 때마다 실행된다.
    - 개별 사용자마다 설정이 필요한 내용이 있을 때 이 파일에 기재한다.
    - 한 번 로그인되면 로그아웃될 때까지 유지된다.
    - 만약 설정이 변경되었다면 source 명령어를 통해 즉시 반영이 가능하다.
  - ~/.profile
    - 사용자가 시스템에 로그인할 때마다 실행된다.
    - 주로 bash와는 직접 관련이 없는 사항을 기재한다.
  - ~/.bashrc
    - 비로그인 셸에서 실행된다.
    - 즉 로그인 상태에서 새로운 터미널을 열 때마다 이 파일이 로드된다.
    - 보통 alias 설정이난 함수를 지정한다.
  - ~/.bash_logout
    - 로그인할 셸을 로그아웃 할 때마다 실행되는 설정 파일이다.
    - 꼭 필요한 파일은 아니지만 사용자 계정의 임시 파일을 제거하는 등의 사용자 관리 목적으로 유용하게 사용할 수 있다.

## 셸의 기능

- 자동완성 기능 (bash-completion)
  - TAP
  - TAP + TAP

- 히스토리(history) 기능
  - history
  - history 5
  - history -c
  - !! (Previous command)

- Alias 기능
  - alias
  - alias cls="clear; ls -al; whoami; pwd"
  - alias cls
  - unalias cls

- 명령어 치환 기능 (Command substitution)
  - 명령어 실행 결과를 명령어의 인자로 바로 넘길 수 있는 기능이다.
  - touch "$(date)"

- 표준 입출력 기능
  - 리눅스 커널은 사용자로부터 기본으로 입력 받은 장치와 사용자에게 결과를 출력하는 장치라는 개념을 통해 사용자의 입력을 프로그램에게 전달하고 프로그램의 결과를 사용자에게 보여준다.
  - stdin (File descriptor: 0)
    - 프로그램에게 데이터를 전달할 때 사용하는 기본 장치를 의미한다.
    - 기본 표준 입력은 키보드이다.
  - stdout (File descriptor: 1)
    - 프로그램의 출력을 표시한 기본 장치를 의미한다.
    - 기본 표준 출력은 모니터로 설정되어 있다.
  - stderr (File descriptor: 2)
    - 프로그램에서 오류가 발행했을 때 출력할 기본 장치를 의미한다.
    - 기본 표준 에러는 모니터이다.

## 리눅스 셸의 종료

- logout
- exit
- Ctrl + D
- ~/.bash_logout

## 셸의 단축기

- 화면 제어하기
  - Ctrl + L : 화면을 모드 지움
  - Ctrl + S : 화면의 출력을 멈춤
  - Ctrl + Q : 멈추었던 화면을 다시 재개함

- 커서 제어
  - Ctrl + A : 줄의 맨 앞으로 이동
  - Ctrl + E : 줄의 맨 끝으로 이동
  - Alt + B : 왼쪽으로 한 단어 이동
  - Ctrl + B : 왼쪽으로 한 글자 이동
  - Alt + F : 오른쪽으로 한 단어 이동
  - Ctrl + F : 오른쪽으로 한 글자 이동

- Copy & Paste
  - Ctrl + W : 커서 위치 이전의 단어를 잘라 클립보드에 복사함
  - Ctrl + K : 커서 위치 이후의 줄을 잘라 클립보드에 복사함
  - Ctrl + U : 커서 위치 이전의 줄을 잘라 클립보드에 복사
  - Ctrl + Y : 클립보드의 내용을 붙여넣음

- 텍스트 삭제하기
  - Ctrl + D : 커서 위치의 글자를 삭제
  - Alt + D : 현재 커서 이후의 한 단어 삭제
  - Ctrl + H : 커서 이전의 글자 삭제

## Redirection

- ls -al > list-file
- ls -al | sort -r > list-file
- cat pop.mp3 > /dev/audio
- sort -n < list-file
- sort -r < list-file
- cat no-file 2> error-file
- cat no-file 2> /dev/null

## pipe

- 여러 프로그램의 기능을 하나의 명령줄로 효과적으로 구성할 수 있도록 프로그램의 출력 결과를 또 다른 프로그램의 입력으로 전달할 수 있다.
- 파이프는 일종의 프로세스 간 통신 (IPC : Inter Process Communication)을 말한다.
- ls -l || less

## 작업 제어 기능 (Job Control Command)

- 셸에서 실행하는 프로세스를 Job 혹은 작업이라고 한다.
- 작업 상태
  - Foreground
  - Background
    - vim file &
  - Stopped
- 작업 간 전환
  - fg
  - bg
- 현재 작업 목록 확인
  - jobs
  - kill %n

## 산술 논리 연산 기능

- +, - , * , /, %
- |, &, ^
- expr 1+2+3 (공백을 주지 않으면 문자열로 취급)
- expr 1 + 2 + 3
- expr 2 '*' 4
- expr 1 '|' 0
- expr 1 '&' 1

## 프롬프트 제어 기능

- echo $PS1
- printf "%srn" test
- read answer
- echo $answer
