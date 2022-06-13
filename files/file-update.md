# File Update

## mv (move (rename) files)

- mv [−ifvbu] source_file target_file
- mv [−if] a.txt b.txt (rename)

## cp (copy files and directories)

- cp [−ifrdpvau] source_file target_file
- cp -r source_file target_file (디렉토리를 통째로 복사한다.)
- cp -r source_file target_file 2>/dev/null (Blackhole)

## rm (remove files or directories)

- rm [-if] file (...)
- rm -rf * (Deletes all files and directories belonging to the current directory)
- rm -f file{1..3}

- rm -rf [a-t]*
- rm -rf [^r]* (r로 시작하는 파일 및 디렉토리를 제외하고 모두 삭제)
- rm -rf [!r]*
