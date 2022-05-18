# Package Manager

- deb 형식 패키지
- cat /etc/apt/sources.list
  - deb http://security.ubuntu.com/ubuntu/ focal-security main restricted
  - dev URI distribution component [component...]
  - distribution : Ubuntu-20.04 LTS (focal)
- APT(Advanced Packaging Tool)는 데비안(Debian) GNU/리눅스 계열의 패키지 관리 명령도구로 우분투(Ubuntu)에서도 지원한다.

## apt (command-line interface)

- apt: 더 나은 대화식 사용을위한 고급 명령 줄 인터페이스이다.
  - apt list
  - apt list | grep tree
  - apt update (apt 명령어 패키지 자체 갱신)
  - apt search tree (특정 패키지 존재 여부 확인)
  - apt install tree (패키지 설치)
  - apt remove tree (설치한 패키지 제거)
  - apt upgrade tree (설치한 패키지 업그레이드)
  - dpkg -L tree (설치한 패키지에 포함된 파일 확인)
  - dpkg -l (설치된 패키지 확인)
  - dpkg -l | grep tree

## apt-cache ( query the APT cache)

- apt-cache search tree (특정 패키지 존재 여부 확인)
- apt-cache show tree (패키지 정보 확인)
- apt-cache dumpavail (설치 가능한 모든 패키지 표시)
- apt-cache dumpavail | less

## apt-get (APT package handling utility -- command-line interface)

- apt-get: 인증 된 소스에서 패키지 및 패키지에 대한 정보를 검색하고 종속성과 함께 패키지를 설치, 업그레이드 및 제거한다.
  - apt-get update
  - apt-get search tree
  - apt-get install tree
  - apt-get remove tree
  - apt-get upgrade
  - dpkg -L tree (설치한 패키지에 포함된 파일 확인)

## dpkg (package manager for Debian)

- dpkg -L tree (설치한 패키지에 포함된 파일 확인)
- dpkg -l (설치된 패키지 확인)
- dpkg -l | grep tree
- dpkg -l | wc -l
