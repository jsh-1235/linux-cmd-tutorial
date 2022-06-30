# inspection

## file (determine file type)

- file FILE
- file DIR

## stat (display file or file system status)

- stat FILE
- stat DIR

- stat -f FILE (display file system status instead of file status)

- touch -a FILE (change only the access time)

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
- ls -aF
  - / : Directory
  - @ : Symbolic Link
  - '*' : 실행 가능 파일

- ls -R (하위 경로와 그 안에 있는 모든 파일들을 나열한다.)
- ls -1R (한 줄에 한 파일씩 나열)

- ls -n (소유자를 UID, 소유 그룹을 GID로 표시한다.)

- ls -i (print the index number of each file)
- ls -li

- ls -s (print the allocated size of each file, in blocks/)
- ls -lh (with -l and -s, print sizes like 1K 234M 2G etc.)

- ls -r (reverse order while sorting)
- ls -c (sort by, and show, ctime [time of last modification of file status information])
- ls -t (sort by modification time, newest first)

- ls -alh (with -l and -s, print sizes like 1K 234M 2G etc.)
- ls -alS (sort by file size, largest first)
- ls -alSr
- ls -alX (sort alphabetically by entry extension)

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
