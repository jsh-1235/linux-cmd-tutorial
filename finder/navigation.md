# Navigation

## pwd (Print Working Directory)

- pwd (현재 디렉토리의 절대 경로 출력)

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
- ls -a (모든 파일을 촐력)
- ls -i (파일의 inode 출력)
- lis -il
- ls -k (파일의 크기를 KB 단위로 출력)
- ls -l (파일 목록의 형태, 권한, 소유자 그룹, 크기, 시간, 파일명을 자세하게 나열)
- ls -m (목록을 가로로 나열)
- ls -n (소유자를 UID, 소유 그룹을 GI로 표시한다.)
- ls -s (파일 크키글 KB 단위로 출력)
- ls -r (정렬 순서를 내림 차순으로 변경)
- ls -c (최근 변경 시간에 따라 정렬해서 출력)
- ls -t (파일 정렬을 최근에 사용한 순서대로 출력)
- ls -F (append indicator (one of */=>@|) to entries)
- ls -alF
  - / : Directory
  - @ : Symbolic Link
  - '*' : 실행 가능 파일

- ls -ld (list directories themselves, not their contents)

- ls -A (".", ".."을 제외)
- ls -R (하위 경로와 그 안에 있는 모든 파일들을 나열한다.)
- ls -R
- ls -lR
- ls -1R (한 줄에 한 파일씩 나열)

- ls -alh (with -l and -s, print sizes like 1K 234M 2G etc.)
- ls -alS (sort by file size, largest first)
- ls -alX (sort alphabetically by entry extension)

- ls -al
- ls -al *.html
- ls -l | grep "^d" (only directory)

## tree (list contents of directories in a tree-like format.)

- tee
- Ctrl + D (exit)
- echo "hello" | tee file-name

## tee (read from standard input and write to standard output and files)

- 표준 입력으로부터 데이터를 읽어 표준 촐력으로 출력하거나 또는 이와 동시에 파일에 저장할 수 있다.
- 표준 출력과 파일 저장을 동시에 수생할 수 있기 때문에 파이프라인을 양 갈래로 나누어 보낼 수 있다.

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
