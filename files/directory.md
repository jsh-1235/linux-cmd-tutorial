# Directory

- 디렉터리는 트리(Tree) 모양의 계층적 구조(Hierarchical Structure)를 가진다.
- 네트워크로 정보를 공유하는 서비스를 디렉터리 서비스라고 부른다.
  - LDAP, PAM, NSS

## structure

- 트리 구조
  - 루트디렉터리 (/)
  - 부모디렉터리 (..)
  - 현재디렉터리 (.)
  - 서브디렉터리 (./sub)
  - 홈디렉터리 (~)

- Root Directory (/)
  - Parent Directory (..)
    - Working Directory (.)
      - Sub Directory (./sub)

- Working Directory (Current Directory)
  - 현재 사용 중인 디렉터리이다.

- Home Directory (~)
  - 홈 디렉터리는 각 사용자에게 할당된 디렉터리로 처음 사용자 계정을 만들 때 지정된다.

## path

- 절대 경로명 (Absolute Path Name)
  - 최상위디렉터리(/)를 기준으로 파일이나 디렉터리의 위치를 나타낸다.
- 상태 경로명 (Relative Path Name)
  - 현재의 위치를 기존으로 파일이나 디렉터리 위치를 나타낸다.

## Structure

- /
  - 루트 디렉터리는 모든 디렉터리의 최상위 경로이다.
  - 기본적으로 리눅스 파티션의 마운트 포인트가 된다.

- /root
  - 루트의 홈 디렉터리이다.

- /boot (Boot Loader Files)
  - 부트로더와 부팅을 위한 파일들이 들어 있다.
  - 커널과 부팅에 필요한 핵심 파일이 들어 있는 중요한 디렉터리이다.
  - /boot 디렉터리리를 보호하기 위해 리눅스 설치 시 따로 파티션을 나누기도 한다.

- /bin (User Binaries)
  - 기본적인 명령어와 유틸리티들의 실행 파일(Binary File)이 들어 있는 디렉터리이다.
  - 일반 사용자를 위한 가장 기본적인 명령어들이 위치해 있습니다.

- /sbin (System Binaries)
  - 시스템 관리자용 명령어들이 존재한다.
  - bin과 같이 명령어가 모여있는 곳이지만 sudo 권한이 필요합니다.
  - 시스템 수정, 복구 등의 많은 작업이 가능한 명령어들이 존재한다.

- /etc (Configuration Files)
  - 리눅스에서 실행되는 프로그램의 설정 파일이 존재한다.
  - 사용자, 그룹 등 시스템의 환경 뿐만 아니라 설치된 외부 패키지들의 설정들도 볼 수 있다.

- /dev (Device Files)
  - 시스템 주변 장치들, 즉, 마우스 모니터, 비디오 카드, 하드디스크 등이 '파일' 형태로 존재한다.
  - udev라는 데몬이 관리한다.

- /proc (Process Information)
  - 시스템 정보를 제공하는 가상 파일 시스템 디렉터리입니다.
  - /proc는 하드 디스크상에 존재하는 것이 아니라, 메모리에 존재한다.
  - 이 디렉터리를 확인해서 cpu 정보, 입출력 주소 목록 등 시스템 상태를 모니터링 할 수 있습니다.
  - 대부분 읽기 전용이지만 쓰기 가능한 파일이 존재하는데 이런 파일을 이용하여 커널의 기능을 변경할 수 있다.

- /var (Variable Files)
  - 시스템을 운영하면서 생기는 임시 파일들(시스템 로그, 스풀, 전자 메일) 등을 저장하는 디렉터리이다.
  - 로그 파일과 같이 크기가 계속해서 변하는 임시 파일을 저장합니다.

- /tmp (Temporary Files)
  - 시스템 사용 중에 발생하는 임시 데이터가 저장된다.
  - 이 디렉타리에 있는 파일은 시스템 재시작 시 모두 삭제된다.

- /usr (Unix System Resource)
  - 시스템 응용 프로그램은 설치할 때 대부분 /usr 디렉터리에 설치가 된다.
  - 기본 실행 파일과 라이이브러리 파일, 헤더 파일 등 많은 파일들이 저장된다.
  - 유저가 만든 쉘 스크립트는 일반적으로 /usr/local/bin에 저장하여 $PATH에 등록하여 경로에 상관 없이 실행 할 수 있다.

- /home (Home Directories)
  - 일반 사용자의 홈 디렉터리가 생성되는 곳이다.
  - 사용자를 만들면 /home/[username] 형태로 사용자 디렉터리가 생성된다.
  - /home 디렉터리는 별도의 파티션으로 분리하는 경우가 보통이다.

- /lib (System Libraries)
  - 공유 라이브러리(Shared Library)와 커널 모듈(Kernel Module)이 들어 있는 디렉터리이다.
  - 시스템의 부팅, 응용 프로그램 실행에 필요한 코드들이 있다.

- /opt (Optional add-on Application)
  - 애드온 소프트웨어를 설치할 수 있도록 만들어진 디렉터리이다.

- /mnt (Mount Directory)
  - 파일 시스템(NFS 등)을 임시로 마운트하는 디렉터리이다.
  - 기본적인 마운트 포인트가 존재하는 디렉타리이다.

- /media (Removable Media Devices)
  - FDISK, CDDROM, DVD등의 이동식 디스크와 같은 외부 장치를 연결(Mount)하는 디렉터리이다.

- /srv (Service Data)
  - 서비스 디렉터리로 주로 ftp, http 등 시스템에서 제공하는 서비스의 데이터가 저장된다.

- /sys
  - 리눅스 커널과 관련된 파일이 있는디렉터리이다.
  - 시스템이 필요한 파일이들이 들어있다.

- /lost+found
  - 부팅 시 파일시스템에 문제가 생길 경우 fcsk(file system check)명령어로 복구할 때 사용하는디렉터리가 존재한다.
  - 이 디렉터리는 아무런 파일도 없는 것이 정상이며 각각 파티션의 최상위 디렉터리마다 존재한다.

## mkdir (make directories)

- mkdir DIR
- mkdir DIR1 DIR2
- mkdir DIR{1..10}
- mkdir -p a/b/c (no error if existing, make parent directories as needed)
- ls -R

## rmdir (remove empty directories)

- rmdir 명령으로 디렉터리를 삭제할 때 해당 디렉터리가 비어 있어야 한다.

- rmdir DIR
- rmdir DIR{1..10}
- rmdir -p a/b/c (인수로 지정한 디렉터리 경로가 존재하면 그 중간 디렉터리도 포함해서 삭제한다.)

## rm (remove files or directories)

- rm -r DIR
- rm -ri DIR (prompt before every removal)
- rmdir -v * (output a diagnostic for every directory processed)

- alias rm='rm -i'
- \rm test
- rm -f test

## mv (move (rename) files)

- mv FILE1 FILE2 (rename)

## cp (copy files and directories)

- cp -r FILE1 FILE2 (copy directories recursively)
