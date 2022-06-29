# Directory

- Tree 모양의 계층적 구조(Hierarchical Structure)를 가진다.
- FHS (Filesystems Hierarchy System)
- Root Directory (/)
  - Upper Directory (..)
    - Current Directory (.)
      - Lower Directory (./sub)

- 절대 경로명 (Absolute Path Name)
  - 최상위 디렉토리(/)를 기준으로 파일이나 디렉토리의 위치를 나타낸다.
- 상태 경로명 (Relative Path Name)
  - 현재의 위치를 기존으로 파일이나 디렉토리 위치를 나타낸다.

- 네트워크로 정보를 공유하는 서비스를 디렉토리 서비스라고 부른다.
  - LDAP, PAM, NSS

## mkdir (make directories)

- mkdir backup
- mkdir dir{1..10}
- mkdir -p a/b/c
- ls -R

## rmdir (remove empty directories)

- rmdir [-p] backup (인수로 지정한 디렉토리 경로가 존재하면 그 중간 디렉토리도 포함해서 삭제한다.)
- rmdir backup
- rmdir dir{1..10}
- rmdir -p a/b/c

## rm (remove files or directories)

- rm -r backup
- rm -ri backup (prompt before every removal)
- rmdir -v * (output a diagnostic for every directory processed)

- alias rm='rm -i'
- \rm test
- rm -f test

## mv (move (rename) files)

- mv backup backup2 (rename)

## cp (copy files and directories)

- cp -r backup backup2 (copy directories recursively)

## Structure

- /
  - 루트 디렉토리. 모든 디렉토리의 최상위 경로이다.
  - 기본적으로 리눅스 파티션의 마운트 포인트가 된다.

- /root
  - 루트 계정을 위한 디렉토리입니다. /home/root 는 없습니다. /root는 일반 계정이 접근할 수 없습니다.
  - 소유자만 rwx할 수 있는 것을 확인해볼 수 있습니다.

- /boot - Boot Loader Files
  - 부트로더와 부팅을 위한 파일들이 들어 있음
  - 커널과 부팅에 필요한 핵심 파일이 들어 있는 중요 디렉토리이다.
  - /boot 디렉토리리를 보호하기 위해 리눅스 설치 시 따로 파티션을 나누기도 한다.

- /bin - User Binaries
  - 기본적인 명령어와 유틸리티들의 실행 파일(Binary File)이 들어 있는 디렉토리이다.
  - 일반 사용자를 위한 가장 기본적인 명령어들이 위치해 있습니다. 이 부분은 python, go 등 다른 언어 등에서도 공통적인 관습입니다.

- /sbin - System Binaries
  - 시스템 관리자용 명령어들이 존재한다.
  - bin과 같이 명령어가 모여있는 곳이지만 sudo 권한이 필요합니다.
  - 시스템 수정, 복구 등의 많은 작업이 가능한 명령어들이 존재한다.

- /etc - Configuration Files
  - 시스템 설정 파일이 들어 있는 디렉토리이다.
  - 사용자, 그룹 등 시스템의 환경 뿐만 아니라 설치된 외부 패키지들의 설정들도 살필 수 있습니다.

- /dev - Device Files
  - 시스템 주변 장치들, 즉, 마우스 모니터 비디오카드 하드디스크 등이 '파일' 로 등록되어 있는 디렉토리이다.
  - udev라는 데몬이 관리한다.

- /proc - Process Information
  - 시스템 정보를 제공하는 가상 파일 시스템 디렉토리입니다.
  - 이 디렉토리를 확인해서 cpu 정보, 입출력 주소 목록 등 시스템 상태를 모니터링 할 수 있습니다.
  - 대부분 읽기 전용이지만 쓰기 가능한 파일이 존재하는데 이런 파일을 이용하여 커널의 기능을 변경할 수 있다.

- /var - Variable Files
  - 시스템을 운영하면서 생기는 임시 파일들(시스템 로그, 스풀, 전자 메일) 등을 저장하는 디렉토리입니다.
  - 로그 파일과 같이 크기가 계속해서 변하는 임시 파일을 저장합니다.

- /tmp - Temporary Files
  - 임시 파일 생성, 삭제하는 공간입니다.
  - 임시로 필요한 것들을 넣어두면 좋습니다.
  - 언제든지 삭제되어도 무리가 없는 것들을 넣어두는 것이 좋습니다.

- /usr - User Programs
  - 일반 사용자들을 위한 대부분의 프로그램이 위치한다.
  - 시스템, 응용 프로그램에서 필요한 파일들이 저장되어 있는 디렉토리입니다.
  - 일반적으로 /usr에는 선택적으로 설치되는 응용 프로그램들이 저장됩니다.
  - 유저가 만든 쉘 스크립트는 일반적으로 /usr/local/bin에 저장하여 $PATH에 등록하고 경로 불문 명령어 처럼 사용하는 관습이
  있습니다.

- /home - Home Directories
  - 사용자를 만들면 /home/[username] 꼴로 사용자 디렉토리가 생성됩니다.
  - 사용자는 각자 파일을 사용자 홈 디렉토리에 저장합니다.

- /lib - System Libraries
  - 공유 라이브러리 파일이 저장되어 있는 디렉토리입니다. 시스템의 부팅, 응용 프로그램 실행에 필요한 코드들이 있습니다.

- /opt - Optional add-on Application
  - 애드온 소프트웨어를 설치할 수 있도록 만들어진 디렉토리이다.

- /mnt - Mount Directory
  - NFS와 같은 파일시스템이 임시로 마운트되는 곳이다.

- /media - Removable Media Devices
  - FDISK, CDDROM, DVD등의 이동식 디스크들이 Mount된 곳이다.

- /srv - Service Data
  - 서비스 디렉토리로 주로 ftp, http, cvs등의 데이터가 들어 있다.

- /sys
  - 시스템이 필요한 파일이들이 들어있다.

- /lost+found
  - 한 파일 시스템에 하나만 존재
  - 부팅 시 파일시스템에 문제가 생길 경우 fcsk(file system check)명령어로 복구할 때 사용하는 디렉토리가 존재한다.

## Path

- 트리 구조
  - 루트 디렉토리 (/)
  - 부모 디렉토리 (..)
  - 현재 디렉토리 (.)
  - 서브 디렉토리 (./sub)
  - 홈 디렉토리 (~)
- 절대 경로 (Absolute Path)
- 상대 경로 (Relative Path)