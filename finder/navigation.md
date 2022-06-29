# Navigation

## pwd (Print Working Directory)

- pwd (현재 디렉토리의 절대 경로 출력)

## cd (Change Directory)

- cd / (root directory)
- cd .. (Upper directory)
- cd /etc (Sub directory: 절대 경로 지정)
- cd ~ (Home directory)
- cd (Home directory)
- cd - (Previous directory)

## Add directories to stack

- pushd /etc
- popd

## hash (Remember or display program locations.)

- hash

## Hash/Bang

- !! (바로 직전에 사용한 명령어)
- !-n (현재 이력 번호에서 n번 전의 명령어 실행)
- !str (str로 시작하는 가장 최근 명령어 실행)
- !$ (마지막으로 실행한 명령어의 마지막 인수 표시)

## home directory

- cd ~
- cd

- echo $HOME

## 명령어 자동 완성

- da [tab] [tab]
- cd / [tab] [tab]
- cd ~ [tab] [tab]


## ls (list directory contents)

- ls
- ls -1 (목록을 한줄에 표시)
- ls -al
- ls -al *.html
- ls -l | grep "^d" (only directory)

- ls -a (모든 파일을 촐력)
- ls -l (파일 유형, 파일 권한, 하드 링크수, 소유자, 그룹, 파일 크기, 마지막 변경날짜/시간, 파일명)

- ls -ld (list directories themselves, not their contents)
- ls -A (".", ".."을 제외)

- ls -F (append indicator (one of */=>@|) to entries)
- ls -alF
  - / : Directory
  - @ : Symbolic Link
  - '*' : 실행 가능 파일

- ls -R (하위 경로와 그 안에 있는 모든 파일들을 나열한다.)
- ls -1R (한 줄에 한 파일씩 나열)
- ls -lR

- ls -n (소유자를 UID, 소유 그룹을 GID로 표시한다.)

- ls -i (파일의 inode 출력)
- ls -li

- ls -s (파일 크기를 KB 단위로 출력)
- ls -lh (with -l and -s, print sizes like 1K 234M 2G etc.)

- ls -r (정렬 순서를 내림 차순으로 변경)
- ls -c (최근 변경 시간에 따라 정렬해서 출력)
- ls -t (파일 정렬을 최근에 사용한 순서대로 출력)

- ls -alh (with -l and -s, print sizes like 1K 234M 2G etc.)
- ls -alS (sort by file size, largest first)
- ls -alSr
- ls -alX (sort alphabetically by entry extension)

## ls - alias

- ls
- \ls (alias 기능 해제)
- \ls --color=auto

## dircolors

- dircolors
- dircolors | grep jpeg

- dircolors --help
- dircolors -b (output Bourne shell code to set LS_COLORS)
- dircolors -p
- dircolors -p > ~/.dir_colors
- vim .dir_colors

- source .dir_colors (파일 다시 불러오기, logout -> login)
- . .dir_colors (Execute commands from a file in the current shell.)

## dir (list directory contents)

- dir /etc (ls)
- dir /etc --color=auto
- dir /etc --color=tty

## vdir (list directory content)

- vdir /etc (ls -l)
- vdir /etc --color=auto
- vdir /etc --color=tty

## tree (list contents of directories in a tree-like format.)

- tree
- tree -a (All files are printed. By default tree does not print hidden files)
- tree -d (list directories only.)
- tree -L 1 (Max display depth of the directory tree.)

- tree -p (Print the file type and permissions for each file)
- tree -u (Print the username, or UID)
- tree -g (Print the group name, or GID)
- tree -s (Print the size of each file in bytes along with the name.)
- tree -h (Print the size of each file but in a more human readable way)
