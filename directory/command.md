# CURD

## mkdir (make directories)

- mkdir DIR
- mkdir DIR1 DIR2
- mkdir DIR{1..10}
- mkdir -p a/b/c (no error if existing, make parent directories as needed)
- ls -R

## rmdir (remove empty directories)

- rmdir 명령으로 디렉터리를 삭제할 때 해당 디렉터리가 비어 있어야 한다.

- rmdir DIR
- rmdir DIR{1..10}
- rmdir -p a/b/c (인수로 지정한 디렉터리 경로가 존재하면 그 중간 디렉터리도 포함해서 삭제한다.)

## rm (remove files or directories)

- rm -r DIR
- rm -ri DIR (prompt before every removal)
- rmdir -v * (output a diagnostic for every directory processed)

- alias rm='rm -i'
- \rm FILE
- rm -f FILE

## mv (move (rename) files)

- mv DIR1 DIR2 (rename)

## cp (copy files and directories)

- cp -r DIR1 DIR2 (copy directories recursively)
