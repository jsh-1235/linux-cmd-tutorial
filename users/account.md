
# account

- OS는 사용자를 고유한 User ID로 관리한다.
- 사용자가 시스템에 로그인(login)하기 위해서는 계정이 있어야 한다.
- 사용자는 반드시 하나의 그룹에 속해야 하며, 사용자가 주로 속하는 그룹을 Primary Group 이라고 한다.
- 그룹도 Group ID라는 번호를 할당받아서 관리된다.

## 사용자 분류

- Root 계정
  - 시스템에 대한 모든 권한을 가진 특별한 사용자다. (superuser)
  - UID : 0
  - sudo passwd root
  - 현재 사용자를 root 사용자로 지정하는 방법
    - vim /etc/passwd
    - 사용자 UID를 0으로 설정
  - root 사용자는 시스템 초기 환경설정 시에만 이용하고 SSH를 통해 root 사용자로 로그인이 되지 않도록 설정한다.
  - root 계정으로 로그인하는 것을 지양하고 필요시 sudo 명령을 사용하여 명령어를 실행하는 것이 좋다.

- 시스템 계정
  - 리눅스 설치 시 기본적으로 생성되는 계정이며 각 역할별로 제한적인 권한을 갖는다.

- 사용자 계정
  - 실제 리눅스 사용자를 위한 계정이다.

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
  - [User Account/Passwd/UID/GID/Commnet/HOME-DIR/SHEL]
  - [jsh:x:1000:1000:,,,:/home/jsh:/bin/bash

## /etc/shadow

- 사용자의 패스워드가 암호화 되어 있는 파일로 암호화 패스워드 및 계정의 유효 기간 등을 기록하고 있다.
- sudo cat /etc/shadow
- jsh:$6$EkLmaqtlJTzlBHPE$9w1s4Q0sXQLVcP/WJWGaln2R2l5umMckcmIW8CWaJ68zgJe/ehOvk24hcshWacetKNexd1cH4bljkC/uRJ5R10:19122:0:99999:7:::

- nl /etc/shadow | cut -d':' -f 1,2
- nl /etc/shadow | cut -d':' -f 1,2 | grep !

## /etc/group

- 사용자 그룹에 대해 정의되어 있는 파일이다.
- cat /etc/group
- groups

## /etc/gshadow

- 그룹의 암호를 MD5 형식으로 저장하여 그룹의 소유자, 구성원 설정이 가능하다.
- cat /etc/gshadow

## /etc/default/useradd

- 사용자 계정 생성 시 기본 정보를 가지고 있는 파일이다.
- cat /etc/default/useradd

## /etc/login.defs

- 리눅스 시스템 사용자의 전체를 제한하기 위해 사용하는 설정 파일
- 사용자 계정 설정과 관련된 기본값을 정의한 파일이다.
- 새로운 계정을 생성할 때 반드시 참조하는 파일이다.
- less /etc/login.defs

## /etc/skel

- 사용자 계정 생성 시, 홈 디렉토리에 기본적으로 생성되는 파일들이 위치한다.
- .bash_logout
- .bashrc
- .profile

## /etc/sudoers

- sudo cat /etc/sudoers
- su -
- visudo

## FILES

- /etc/group
  - Group account information.

- /etc/gshadow
  - Secure group account information.

- /etc/login.defs
  - Shadow password suite configuration.

- /etc/passwd
  - User account information.

- /etc/shadow
  - Secure user account information.

- /etc/subgid
  - Per user subordinate group IDs.

- /etc/subuid
 - Per user subordinate user IDs.
