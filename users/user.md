# User

## adduser

- adduser manager

## useradd

- useradd [-mcdefP] manager
- useradd -m manager (create home directory)
- useradd -m -c comment manager (create home directory)
- useradd manager -d /home/manager_dir (사용자의 홈 디렉토리 지정)
- useradd -g users username (사용자 그룹의 UID 지정)
- useradd -e 2022-12-30 -m user (사용자의 계정 만기일 지정)

## userdel (delete a user account and related files)

- userdel manager
- userdel -f manager
- userdel -r manager (사용자 홈디렉토리도 함께 삭제한다.)
- sudo userdel -r manager

## chage (change user password expiry information)

- 사용자 패스워드 관리
- 패스워드의 만료 정보를 변경하는 명령어이다.
- chage -l jsh (chage 설정 확인)
- chage -m 5 -M 100 -W 10 -E 2023/01/01 jsh
  - jsh 계정의 패스워드를 5일 후에 변경할 수 있도록 설정
  - 100일 이내에 변경해야만 하고, 만기일 10일 전부터 패드워드를 변경하도록 메시지 전달
  - 계정의 사용은 2023년 1월 1일 까지 제한하도록 구성

## passwd  (change user password)

- sudo passwd root
- passwd manger
- sudo passwd -u root (unlock)
- sudo passwd -l root

## usermod (modify a user account)

- 사용자 계정 속성 변경 [-ugGcdefs]
- sudo usermod -aG sudo manager (add sudoers)
- usermod -u 1001 manager
- usermod -c owner jsh (사용자 정보(comment) 수정)
- usermod -s /bin/bash jsh (로그인 시 사용할 기본 쉘 지정)
- usermod -G bt bt1 (사용자 계정의 2차 그룹의 GID 지정)

## chsh (change login shell)

- chsh -s /bin/bash
- logout

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
- su - root (사용자의 환경 변수를 이어 받지 않는다. 새롭게 로그인한 것과 동일하다.)

## sudo (execute a command as another user)

- sudo (substitute user do)
- sudo -i (root user login)
- sudo -l (현재 사용자에게 허가된 권한 목록을 표시한다.)
- sudo rm -r root
- sudo -u jsh touch ~jsh/test.txt (인증을 한번 해두면 한동안 암호를 입력하지 않아도 sudo 명령어를 사용할 수 있다.)
- sudo -u root rm root-file
- sudo -u jsh rm jsh-file