
# Permissions

- 계정명과 ui는 동일하게 취급되면 그룹명과 gid도 동일하게 취급된다.

- rwx:rwx:rwx [User/Grop/Others] => [u/g/o]
- rwx [Read/Write/Execute]

## chmod (change file mode bits)

- [+ 추가, - 삭제, = 지정, s 소유자 또는 그룹만 실행]

- 상대 모드
  - chmod a+r filename
  - chmod a-r filename
  - chmod u+r filename
  - chmod u-r filename
  - chmod g+w filename
  - chmod g-w filename
  - chmod o+x filename
  - chmod o-x filename

  - chmod u+x,g+x,o+x filename
  - chmod u-x,g-x,o-x filename

- 절대 모드
  - chmod 777 filename

## chown (change file owner and group)

- sudo chown [-R] username filename
- chown username filename (root permission)
- chown :usergroup filename
- chown username:usergroup filename
- chown -r username:usergroup filename (하위 디렉토리까지 소유자와 그룹 소유자를 변경한다.)

## chgrp (change group ownership)

- chgrp usergroup filename
- chgrp -R usergroup filename (하위 디렉토리까지 그룹 소유자를 변경한다.)
