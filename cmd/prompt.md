# Prompt

## clear (clear the terminal screen)

- clear
- Ctrl + L
- echo $TERM
- clear -T xterm-256color

## 화면 제어하기

- Ctrl + L (화면을 모드 지움)
- Ctrl + S (화면의 출력을 멈춤)
- Ctrl + Q (멈추었던 화면을 다시 재개함)
  - locate dir ->  Ctrl + S -> Ctrl + Q -> Ctrl + C

- Ctrl + C (현재 수행중인 작업을 종료시키고 프롬프트로 복귀한다.)
- Ctrl + D (현재 쉘 세션에서 로그아웃을 수행한다. 이는 exit 나 logout 명령어와 유사하다.)
- Ctrl + Z (현재 수행중인 foreground 프로세스를 일시정지 (pause) 시키고, 쉴 프롬프트로 복귀한다.)

- Tab (파일과 디렉토리 이름을 자동 완성시킨다.)
- Tab Tab (입력된 문자들이 특정 파일이나 디렉토리 이름과 단독으로 매칭되지 않은 경우, 모든 가능한 대상을 표시한다.)
  - da [tab] [tab]
  - cd / [tab] [tab]
  - cd ~ [tab] [tab]

- Ctrl + Shift + W (터미널 탭을 닫는다.)
- Ctrl + Shift + Q (터미널 전체를 닫는다.)

## move the cursor

- Ctrl + F (현재 입력중인 라인에서 한 글자 앞으로 이동한다.)
- Ctrl + B (현재 입력중인 라인에서 한 글자 뒤로 이동한다.)
- Alt + F (현재 입력중인 라인에서 한 단어를 건너뛰어 이동한다.)
- Alt + B (현재 입력중인 라인에서 앞쪽으로 한 단어를 건너뛰어 이동한다.)
- Ctrl + A (현재 입력중인 라인의 시작 위치로 이동한다.)
- Ctrl + E (현재 입력중인 라인의 마지막 위치로 이동한다.)
- Ctrl + XX (현재 입력중인 위치와 라인의 시작 위치를 번갈아 이동한다.)

- Ctrl + ← (한 단어 분량 왼쪽으로 이동)
- Ctrl + → (한 단어 분량 오른쪽으로 이동)

## copy & paste

- Ctrl + K (현재 입력중인 라인의 현재 위치부터 라인의 끝까지를 잘라내어 클립보드에 저장한다.)
- Ctrl + U (현재 입력중인 라인의 현재 위치부터 라인의 처음까지를 잘라내어 클립보드에 저장한다.)
- Ctrl + W (현재 커서 앞에 위치한 단어를 삭제하고, 클립보드에 추가한다.)
- Ctrl + Y (최근에 잘라내기를 수행한 클립보드의 가장 마지막 내용을 붙여넣기한다.)

## delete

- Ctrl + H (커서 이전의 글자 삭제)
- Ctrl + D (커서 이후 글자를 삭제)
- Alt + D (현재 커서로부터 단어의 마지막까지를 삭제한다.)

## change

- Alt + L (현재 커서에서 단어의 마지막까지를 소문자로 변경한다.)
- Alt + U (현재 커서에서 단어의 마지막까지를 대문자로 변경한다.)
- Alt + T  (현 커서 앞의 마지막 두개의 단어를 바꾼다.)
- Ctrl + T (커서 앞에 위치한 두 글자의 위치를 바꾼다.)
- Alt + . (이전 명령어에 사용된 마지막 단어를 출력한다.)

## search

- Ctrl + R (이전에 사용했던 명령어들을 검색할 수 있게 해준다.)
- Ctrl + G (명령어 실행 없이 히스토리 검색 모드를 종료한다.)
- Ctrl + J (현재 검색된 명령어를 바로 실행하지 않고 커맨드라인에 복사하여 실제 실행 전에 수정을 할 수 있도록 한다.)
- Alt + R (히스토리에서 추출한 명령어에 수정을 가한 경우, 해당 수정을 되돌린다.)

- Ctrl + P (마지막으로 실행한 명령어를 표시한다. 달리 표현하면, 명령어 히스토리를 반대 방향으로 하나씩 탐색한다. [위 방향 화살표와 유사하다])
- Ctrl + N (다음으로 실행한 명령어를 표시한다. 달리 표현하면, 명령어 히스토리를 정방향으로 하나씩 탐색한다. [아래 방향 화살표와 유사하다])

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
