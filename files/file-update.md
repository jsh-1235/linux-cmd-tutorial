# File Update

## rename.ul (rename files)

- rename.ul f a f*
- rename.ul -v a f a*
- rename.ul -v .txt .backup *

## rename (renames multiple files)

- rename -v 's/.txt/.pdf/' *.txt (s/search_pattern/replacement/)
- rename -n 's/.pdf/.txt/' *.pdf (dry run)
- rename -f 's/.pdf/.txt/' *.pdf (기존 파일 덮어쓰기)

- rename 'y/a-z/A-Z/' * (파일 이름을 대문자로 변경)
- rename 'y/A-Z/a-z/' * (파일 이름을 소문자로 변경)
- rename 'y/ /_/' * (파일 이름의 공백을 밑줄로 변경)
- rename 's/\.txt$//' *.txt (.txt 확장자 제거)

## mv (move (rename) files)

- mv [−ifvbu] source_file target_file
- mv [−if] a.txt b.txt (rename)

## cp (copy files and directories)

- cp [−ifrdpvau] source_file target_file
- cp -r source_file target_file (디렉토리를 통째로 복사한다.)
- cp -r source_file target_file 2>/dev/null (Black-hole)

## rm (remove files or directories)

- rm [-if] file (...)
- rm -rf * (Deletes all files and directories belonging to the current directory)
- rm -f file{1..3}

- rm -rf [a-t]*
- rm -rf [^r]* (r로 시작하는 파일 및 디렉토리를 제외하고 모두 삭제)
- rm -rf [!r]*
