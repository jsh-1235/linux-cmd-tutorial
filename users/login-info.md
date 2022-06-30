# login

## w (Show who is logged on and what they are doing.)

- 접속한 사용자 정보 보기
- w
- w -h (do not print header)
- w -f (show remote hostname field)
- w -s (short format)
- w -o (old style output)

## who (show who is logged on)

- 현재 시스템에 로그인한 모든 사용자를 출력
- who
- who -H (헤더라인 출력)
- who -m (whoami)
- who -q (로그인명과 로그인한 횟수 출력)

## logname (print user´s login name)

- logname (시스템에 로그인한 사용자명 출력)

## whoami (print effective userid)

- 현재 시스템을 사용하고 있는 자신이 누구인지 확인
- whoami
- Print the user name associated with the current effective user ID.  Same as id -un.

## who am i (show who is logged on)

- 'whoami' 명령어 보다 더 상세하게 정보를 보여준다.
- who am i
- who am i -aH

## users (print the user names of users currently logged in to the current host)

- 시스템 로그인한 사용자 정보를 출력하는 명령어이다.
- users

## id (print real and effective user and group IDs)

- id
- id -u
- id -g

- id [-Ggun] manager
- id -u manager
- id -gn manager

## tty

- tty
- echo "hi" > /dev/pts/2
- echo "hello" > /dev/pts/1

## login file

- /var/log/wtmp
  - 시스템에 접속하는 사용자들의 로그인 정보를 저장하고 있는 로그 파일이다.
  - ASCII File
  - last (Login 정보, 재부팅 정보)

- /var/log/lastlog
  - 시스템의 모든 사용자가 접속한 최근 접속 정보를 저장하고 있는 파일이다.
  - lastlog (/etc/passwd 파일에 정의되어 있는 모든 계정 사용자의 최근의 접속 정보를 확인할 수 있다.)

- /var/log/utmp
  - 현재 시스템에 로그인한 각 사용자의 상태 정보 저장
  - w, who, users, whoami, w am i, logname

- /var/log/btmp
  - 실패한 로그인 시도를 기록한다.
  - lastb

- /var/log/cron
  - 예약한 작업의 정상 실행 여부 확인
  - crontab -l

- /var/log/secure
  - ssh, telnet, su, 등의 로그인 인증 기록

## last (show a listing of last logged in users)

- last
- last -n 5
- last jsh
- last -R (접속 위치를 제외한 정보 출력)
- last -a (접속 위치를 마지막 열에 출력)
- last -d (외부 접속 정보와 재부팅 정보만 출력)
- last -t 20220519000000(특정 시간 이전의 정보 출력)
- last reboot (접속 위치를 마지막 열에 출력)

- last manager | less -N
- last manager | grep pts/* | wc -l

- sudo find /var -name wtmp
- sudo cat /var/log/wtmp
- touch /var/log/wtmp

## lastlog (reports the most recent login of all users or of a given user)

- 마지막으로 접속한 사용자 정보 출력
- lastlog
- lastlog -u jsh

## lastb (show a listing of last logged in users)

- 실패한 로그인 시도에 대한 출력
- lastb
- lastb -a (Display the hostname in the last column.)
- lastb -d (This option translates the IP number back into a hostname.)
- lastb -f /var/log/wtmp

## getent (get entries from Name Service Switch libraries)

- getent passwd
- getent passwd | grep jsh
- getent passwd | grep jsh | cut -f1 -d:
- getent passwd | grep jsh | cut -f2 -d:
- getent passwd | awk -F: '{print $1}'
- getent group users

## login (begin session on the system)

- login
- su - manager
- su --login manager
- exit (logout)
- logout

## su (run a command with substitute user and group ID)

- su (Switch user or substitute user)
- 현재의 사용자 계정에서 로그아웃하지 않고 다른 사용자 계정으로 로그인하여 해당 사용자의 권한을 획득하는 명령어이다.
- su root
- su - (root 사용자의 환경변수도 로드하면서 로그인한다.)
- su - root (사용자의 환경 변수를 이어 받지 않는다. 새롭게 로그인한 것과 동일하다.)

## sudo (execute a command as another user)

- sudo (substitute user do)
- sudo -i (root user login)
- sudo -l (현재 사용자에게 허가된 권한 목록을 표시한다.)
- sudo rm -r root

- sudo -u jsh touch ~jsh/test.txt (인증을 한번 해두면 한동안 암호를 입력하지 않아도 sudo 명령어를 사용할 수 있다.)
- sudo -u root rm root-file
- sudo -u jsh rm jsh-file
