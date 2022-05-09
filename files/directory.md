# Directory

## mkdir (make directories)

- mkdir backup
- mkdir -p a/b/c

## rmdir (remove empty directories)

- rmdir backup

## rm (remove files or directories)

- rm -r backup
- rm -ri backup (prompt before every removal)
- rmdir -v * (output a diagnostic for every directory processed)

## mv (move (rename) files)

- mv backup backup2 (rename)

## cp (copy files and directories)

- cp -r backup backup2 (copy directories recursively)

## Structure

- /
  - 루트 디렉토리. 모든 디렉토리의 최상위 경로이다.

- /root
  - 루트 계정을 위한 디렉토리입니다. /home/root 는 없습니다. /root는 일반 계정이 접근할 수 없습니다.
  - 소유자만 rwx할 수 있는 것을 확인해볼 수 있습니다.

- /bin - User Binaries
  - 사용자가 사용하는 가장 기본적인 명령어들이 위치해 있습니다. 이 부분은 python, go 등 다른 언어 등에서도 공통적인 관습입니다.

- /sbin - System Binaries
  - bin과 같이 명령어가 모여있는 곳이지만 sudo 권한이 필요합니다.

- /etc - Configuration Files
  - 시스템 설정 파일이 들어 있는 디렉토리이다.
  - 사용자, 그룹 등 시스템의 환경 뿐만 아니라 설치된 외부 패키지들의 설정들도 살필 수 있습니다.

- /dev - Device Files
  - 시스템 주변 장치들, 즉, 마우스 모니터 비디오카드 하드디스크 등이 '파일' 로 등록되어 있는 디렉토리이다.

- /proc - Process Information
  - 시스템 정보를 제공하는 가상 파일 시스템 디렉토리입니다.
  - 이 디렉토리를 확인해서 cpu 정보, 입출력 주소 목록 등 시스템 상태를 모니터링 할 수 있습니다.

- /var - Variable Files
  - 시스템을 운영하면서 생기는 임시 파일들(시스템 로그, 스풀, 전자 메일) 등을 저장하는 디렉토리입니다.
  - 크기가 계속해서 변하는 임시 파일을 저장합니다.

- /tmp - Temporary Files
  - 임시 파일 생성, 삭제하는 공간입니다.
  - 임시로 필요한 것들을 넣어두면 좋습니다.
  - 언제든지 삭제되어도 무리가 없는 것들을 넣어두는 것이 좋습니다.

- /usr - User Programs
  - 시스템, 응용 프로그램에서 필요한 파일들이 저장되어 있는 디렉토리입니다.
  - 일반적으로 /usr에는 선택적으로 설치되는 응용 프로그램들이 저장됩니다.
  - 유저가 만든 쉘 스크립트는 일반적으로 /usr/local/bin에 저장하여 $PATH에 등록하고 경로 불문 명령어 처럼 사용하는 관습이 있습니다.

- /home - Home Directories
  - 사용자를 만들면 /home/[username] 꼴로 사용자 디렉토리가 생성됩니다.
  - 사용자는 각자 파일을 사용자 홈 디렉토리에 저장합니다.

- /boot - Boot Loader Files

- /lib - System Libraries
  - 공유 라이브러리 파일이 저장되어 있는 디렉토리입니다. 시스템의 부팅, 응용 프로그램 실행에 필요한 코드들이 있습니다.

- /opt - Optional add-on Application

- /mnt - Mount Directory

- /media - Removable Media Devices

- /srv - Service Data
