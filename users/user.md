# User

- 네트워크로 정보를 공유하는 서비스를 디렉토리 서비스라고 부른다.
- LDAP, PAM, NSS

## w (Show who is logged on and what they are doing.)

- w
- w [-hfs]

## who (show who is logged on)

- who

## whoami (print effective userid)

- whoami
- Print the user name associated with the current effective user ID.  Same as id -un.

## id (print real and effective user and group IDs)

- id
- id [-Ggun] manager
- id -u manager
- id -gn manager

## su (run a command with substitute user and group ID)

- su root
- su - root (사용자의 환경 변수를 이어 받지 않는다. 새롭게 로그인한 것과 동일하다.)

## sudo (execute a command as another user)

- sudo -i (root user login)
- sudo -l (현재 사용자에게 허가된 권한 목록을 표시한다.)
- sudo rm -r root
- sudo -u jsh touch ~jsh/test.txt (인증을 한번 해두면 한동안 암호를 입력하지 않아도 sudo 명령어를 사용할 수 있다.)
- sudo -u root rm root-file
- sudo -u jsh rm jsh-file

## passwd (change user password)

- sudo passwd -u root (unlock)
- sudo passwd -l root

## usermod (modify a user account)

- sudo usermod -aG sudo manager (add sudoers)
- usermod -u 1001 manager

## user, group, permission

- OS는 사용자를 고유한 User ID로 관리한다.
- 사용자는 반드시 하나의 그룹에 속해야 하며, 사용자가 주로 속하는 그룹을 Primary Group 이라고 한다.
- 그룹도 Group ID라는 번호를 할당받아서 관리된다.
- 리눅스는 파일이나 디렉토리마다 일기 권한, 쓰기 권한, 실행 권한을 설정한다.
