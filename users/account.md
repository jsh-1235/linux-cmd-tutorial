
# account

## /etc/passwd

- 계정 정보를 가지고 있는 파일로 리눅스에 로그인할 때 사용된다.
- ls -al /home
- cat /etc/passwd
- cut -f1 -d: /etc/passwd
- grep /bin/bash /etc/passwd (adduser)
- grep /bin/bash /etc/passwd | cut -f1 -d:
- grep /bin/bash /etc/passwd | cut -d: -f 1 | wc -l
- tail -n 3 /etc/passwd
- grep manager /etc/passwd (Check Login Shell)
- jsh:x:1000:1000:,,,:/home/jsh:/bin/bash

## /etc/shadow

- 사용자의 패스워드가 암호화 되어 있는 파일로 암호화 패스워드 및 계정의 유효 기간 등을 기록하고 있다.
- sudo cat /etc/shadow
- jsh:$6$EkLmaqtlJTzlBHPE$9w1s4Q0sXQLVcP/WJWGaln2R2l5umMckcmIW8CWaJ68zgJe/ehOvk24hcshWacetKNexd1cH4bljkC/uRJ5R10:19122:0:99999:7:::

## /etc/group

- 사용자 그룹에 대해 정의되어 있는 파일이다.
- cat /etc/group
- groups

## /etc/gshadow

- 그룹의 암호를 MD5 형식으로 저장하여 그룹의 소유자, 구성원 설정이 가능하다.
- cat /etc/gshadow

## /etc/sudoers

- sudo cat /etc/sudoers
- su -
- visudo

## /etc/useradd

- 명령어 useradd로 사용자 계정을 추가할 때 사용되는 정보를 읽어오는 파일이다.

## /etc/login.defs

- 사용자 계정 설정과 관련된 기본값을 정의한 파일이다.
- 새로운 계정을 생성할 때 반드시 참조하는 파일이다.

## adduser

- adduser manager

## useradd

- useradd [-mcdefP] manager
- useradd -m manager (create home directory)
- useradd manager -d /home/manager_dir
- sudo useradd -g users username (특정 그룹 지정)
- useradd -e 2022-12-30 -m user
- passwd manager
- chsh

## userdel (delete a user account and related files)

- userdel manager
- userdel -f manager
- userdel -r manager (사용자 홈디렉토리도 함께 삭제한다.)
- sudo userdel -r manager

## chage (change user password expiry information)

- 패스워드의 만료 정보를 변경하는 명령어이다.

## login (begin session on the system)

- login
- su - manager
- su --login manager
- exit (logout)
- logout

## passwd  (change user password)

- sudo passwd root
- passwd manger

## usermod (modify a user account)

- sudo usermod -aG sudo manager (add sudoers)
- usermod -u 1001 manager

## chsh (change login shell)

- chsh -s /bin/bash
- logout

## last (show a listing of last logged in users)

- last
- last jsh
- sudo find /var -name wtmp
- sudo cat /var/log/wtmp
- touch /var/log/wtmp