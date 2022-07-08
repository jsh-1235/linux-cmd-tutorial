# Permissions

- 리눅스는 파일이나 디렉토리마다 읽기 권한, 쓰기 권한, 실행 권한을 설정한다.
- 계정명과 ui는 동일하게 취급되면 그룹명과 gid도 동일하게 취급된다.

- rwx:rwx:rwx [User/Grop/Others] => [u/g/o]
- rwx [Read/Write/Execute]

## umask (Display or set file mode mask.)

- 파일 생성 시 기본 모드값을 설정한다.

- help umask
- umask
- umask -p
- umask -S (makes the output symbolic; otherwise an octal number is output)

- umask 값             : 000 001 002 022
- File 기본 권한        : 666 665 664 644
- Directory 기본 권한   : 777 776 775 755

- 디렉토리 권한에서 x가 있으면 빼고 없으면 그대로 파일 권한

- umask 002
- 777-002(umask)=775 (rwxrwxr-x), 775-111 =644(rw-r--r--)
- umask -S (u=rwx,g=rwx,o=rx)

- umask 352
- 777-352(umask)=425 (r---w-r-x), 425-001 =424(r---x-r--)
- umask -S (u=r,g=w,o=rx)

- umask u=rwx,g=rx,o=rx (022)
- umask -S

## Special Permission (특별한 권한)

- SUID, SGID
  - SUID, SGID 비트가 설정되면 실행 중에 해당 파일의 소유자나, 소유 그룹의 권한을 가지게 된다.

- SetUID (4000)
  - 파일이 실행되는 동안 실행한 사용자가 아닌 파일의 소유자의 권한을 부여하게 된다.
  - SetUID는 실행 파일에만 명시할 수 있다.
  - 적용되면 소유자의 퍼미션 값에 실행권한에 x가 아닌 s로 명시된다.
  - ls -l /usr/bin/passwd
  - -rwsr-xr-x 1 root root 68208 Jul 15  2021 /usr/bin/passwd
  - touch FILE
  - chmod 4755 FILE
  - ls -l FILE (rwsr-xr-x)

- SetGID (2000)
  - 파일이 실행되는 동안 그룹 소유주의 권한을 갖게 된다.
  - 실행 파일 뿐만 아니라 디렉토리에도 명시될 수 있다.
  - 적용되면 그룹 소유주의 퍼미션 값에 실행권한에 x가 아닌 s로 명시된다.
  - touch FILE
  - chmod 2755 FILE
  - ls -l FILE (rwxr-sr-x)

- sticky bit (1000)
  - 디렉토리에 부여되는 권한으로 적용 시 모든 사용자가 읽고, 쓰고, 삭제가 가능하다.
  - 단, 삭제는 오로지 소유자만 가능하다.
  - 권한이 적용되면 other의 퍼미션에 실행권한이 x가 아닌 t로 명시된다.
  - 대표적인 Sticky Bit가 적용된 디렉토리는 /tmp와 /var/tmp가 있다.
  - ls -ld /tmp
  - drwxrwxrwt 2 root root 4096 May 23 09:17 /tmp
  - chmod 1755 DIR
  - ls -l DIR (drwxrwxrwt)

## chmod (change file mode bits)

- [+ 추가, - 삭제, = 지정, s 소유자 또는 그룹만 실행]

- 상대 모드 (기호 모드)
  - chmod u+r FILE
  - chmod u-r FILE
  - chmod g+w FILE
  - chmod g-w FILE
  - chmod o+x FILE
  - chmod o-x FILE
  - chmod a+r FILE
  - chmod a-r FILE

  - chmod u+x,g+x,o+x FILE
  - chmod u-x,g-x,o-x FILE

- 절대 모드 (숫자 모드)
  - chmod 777 FILE

## chown (change file owner and group)

- sudo chown [-R] OWNER FILE
- chown OWNER FILE (root permission)
- chown :GROUP FILE
- chown OWNER:GROUP FILE
- chown -r OWNER:GROUP FILE (하위 디렉토리까지 소유자와 그룹 소유자를 변경한다.)

## chgrp (change group ownership)

- chgrp GROUP FILE
- chgrp -R GROUP FILE (하위 디렉토리까지 그룹 소유자를 변경한다.)

## chattr (change file attributes on a Linux file system)

- 파일의 속성을 변경하여 실수나 고의로 파일을 변경, 삭제하지 못하도록 한다.
- sudo chattr +i FILE (immutable: 파일을 수정할 수 없으며, 오직 관리자만 이 속성을 설정하거나 변경할 수 있다.)
- lsattr FILE
- chattr -i FILE
- rm -f FILE

## lsattr (list file attributes on a Linux second extended file system)

- lsattr FILE

## iconv (convert text from one character encoding to another)

- iconv -l
- iconv -f 'us-ascii' -t 'UTF-8' FILE > FILE2
- iconv -c -f 'us-ascii' -t 'UTF-8' FILE > FILE2
- file -i *

## file (determine file type)

- file *

- file FILE
- file -i FILE (output MIME type strings [--mime-type and --mime-encoding])
- file /bin/ls
- file ~/.profile
- file /dev/*

## namei (follow a pathname until a terminal point is found)

- namei [options] pathname...
- name -m ~/DIR/FILE

## dirname

- 파일명을 제거한 경로명만을 표시한다.
- dirname DIR/FILE
  - DIR

## basename

- 경로명을 제거한 고유의 파일명을 표시한다.
- basename DIR/FILE
  - FILE
