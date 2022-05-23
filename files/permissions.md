
# Permissions

- 리눅스는 파일이나 디렉토리마다 읽기 권한, 쓰기 권한, 실행 권한을 설정한다.
- 계정명과 ui는 동일하게 취급되면 그룹명과 gid도 동일하게 취급된다.

- rwx:rwx:rwx [User/Grop/Others] => [u/g/o]
- rwx [Read/Write/Execute]

## umask (Display or set file mode mask.)

- umask
- umask -p
- umask -S (makes the output symbolic; otherwise an octal number is output)

- umask 값             : 000 001 002 022
- File 기본 권한        : 666 665 664 644
- Directory 기본 권한   : 777 776 775 755

## Special Permission (특별한 권한)

- SetUID (4000)
  - 파일이 실행되는 동안 실행한 사용자가 아닌 파일의 소유자의 권한을 부여하게 된다.
  - SetUID는 실행 파일에만 명시할 수 있다.
  - 적용되면 소유자의 퍼미션 값에 실행권한에 x가 아닌 s로 명시된다.
  - ls -l /usr/bin/passwd
  - -rwsr-xr-x 1 root root 68208 Jul 15  2021 /usr/bin/passwd
  - touch file
  - chmod 4755 file
  - ls -l file

- SetGID (2000)
  - 파일이 실행되는 동안 그룹 소유주의 권한을 갖게 된다.
  - 실행 파일 뿐만 아니라 디렉토리에도 명시될 수 있다.
  - 적용되면 그룹 소유주의 퍼미션 값에 실행권한에 x가 아닌 s로 명시된다.
  - touch file
  - chmod 2755 file
  - ls -l file

- sticky bit (1000)
  - 디렉토리에 부여되는 권한으로 적용 시 모든 사용자가 읽고, 쓰고, 삭제가 가능하다.
  - 단, 삭제는 오로지 소유자만 가능하다.
  - 권한이 적용되면 other의 퍼미션에 실행권한이 x가 아닌 t로 명시된다.
  - 대표적인 Sticky Bit가 적용된 디렉토리는 /tmp와 /var/tmp가 있다.
  - ls -ld /tmp
  - drwxrwxrwt 2 root root 4096 May 23 09:17 /tmp

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

