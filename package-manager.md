# Package Manager

- deb 형식 패키지
- cat /etc/apt/sources.list
  - deb http://security.ubuntu.com/ubuntu/ focal-security main restricted
  - dev URI distribution component [component...]
  - distribution : Ubuntu-20.04 LTS (focal)
- APT(Advanced Packaging Tool)는 데비안(Debian) GNU/리눅스 계열의 패키지 관리 명령도구로 우분투(Ubuntu)에서도 지원한다.

## RMP (RedHat Package Manager)

- RedHat 계열의 리눅스는 RPM 형태의 바이너리 패키지로 배포가 이루어진다.
- RPM은 RedHat에서 만든 패키지 배포 및 관리 프로그램으로 리눅스 소스 및 컴파일된 프로그램의 배포, 업그레이드 관리 등을 쉽게 하기 위해 프로그램과 설정 파일 등을 하나로 묶어 만든 것을 말한다.

- rpm -ivh tree (설치)
- rpm -q tree
- rpm -qa tree | grep tree
- rpm -e tree (제거)

## yum (Yellowdog Updater Modified)

- RPM 명령의 패키지 의존성 문제를 해결
- 인터넷을 통하여 필요한 파일들을 저장소(Repository)에서 다운로드 해서 설치하는 방식
- 또한 의존성을 가지는 다른 RPM 패키지까지 알아서 다운로드하여 설치한다.
- Update된 패키지들을 검사하고, 다운로드하여 설치까지 자동으로 진행한다.

- sudo yum update (모든 패키지 업데이트)
- yum check-update (설치된 패키지 중에 업데이트가 가능한 패키지 목록 출력)

- yum -y (설치 여부를 묻지 않고 바로 설치한다.)
- yum install tree
- yum update tree
- yum remove tree
- yum info tree

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
