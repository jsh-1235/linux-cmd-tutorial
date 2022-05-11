# Navigation

## pwd (Print Working Directory)

- pwd

## cd (Change Directory)

- cd /etc
- cd .. (Upper directory)
- cd ~ (Home directory)
- cd - (Previous directory)
- cd $TEMP (Change current directory to the directory defined by the environment variable "TEMP".)
- !! (바로 직전에 사용한 명령어)
- !-n (현재 이력 번호에서 n번 전의 명령어 실행)
- !str (str로 시작하는 가장 최근 명령어 실행)
- !$ (마지막으로 실행한 명령어의 마지막 인수 표시)

## Add directories to stack

- pushd /etc
- popd

## ls (list directory contents)

- ls
- ls -l
- ls -al
- ls -ld (list directories themselves, not their contents)
- ls -alh (with -l and -s, print sizes like 1K 234M 2G etc.)
- ls -alS (sort by file size, largest first)
- ls -alX (sort alphabetically by entry extension)
- ls -al *.html
- ls -l | grep "^d" (only directory)
- ls -F (append indicator (one of */=>@|) to entries)
- ls -alF
  - / : Directory
  - @ : Symbolic Link
  - '*' : 실행 가능 파일

## tree (list contents of directories in a tree-like format.)

- tree
- tree -p

## 명령어 자동 완성

- da [tab] [tab]
- cd / [tab] [tab]
- cd ~ [tab] [tab]

## Cursor

- ctrl + ← (한 단어 분량 왼쪽으로 이동)
- ctrl + → (한 단어 분량 오른쪽으로 이동)
- ctrl + a (줄 처음으로 이동)
- ctrl + e (줄 마지막으로 이동)
- ctrl + h (커서 왼쪽쪽으로 한 글자 삭제)
- ctrl + d (커서 오른쪽으로 한 글자 삭제)
- ctrl + u (커서 왼쪽쪽으로 문자열 삭제)
- ctrl + k (커서 오른쪽으로 문자열 삭제)
- ctrl + r (과거에 실행한 명령어 검색)
