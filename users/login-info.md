# login

## w (Show who is logged on and what they are doing.)

- w
- w [-hfs]

## who (show who is logged on)

- who

## whoami (print effective userid)

- whoami
- Print the user name associated with the current effective user ID.  Same as id -un.

## logname (print user´s login name)

- logname (시스템에 로그인한 사용자명 출력)

## id (print real and effective user and group IDs)

- id
- id [-Ggun] manager
- id -u manager
- id -gn manager

## users (print the user names of users currently logged in to the current host)

- 시스템 로그인한 사용자 정보를 출력하는 명령어이다.
- users

## last (show a listing of last logged in users)

- last
- last jsh
- sudo find /var -name wtmp
- sudo cat /var/log/wtmp
- touch /var/log/wtmp

## getent (get entries from Name Service Switch libraries)

- getent passwd
- getent passwd | grep jsh
- getent passwd | grep jsh | cut -f1 -d:
- getent passwd | grep jsh | cut -f2 -d:
- getent passwd | awk -F: '{print $1}'
- getent group users
