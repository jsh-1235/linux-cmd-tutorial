
# wsl (Windows Subsystem for Linux)

- windows key + r
- ws
  - wsl -l -v
  - ubuntu2004.exe
  - bash
  - wsl

## wsl command

- wsl --help
- wsl --status

- wsl --list --online
- wsl --install Ubuntu-20.04
- wsl --update

- wsl --list --verbose (wsl -l -v)

- wsl --set-default-version 2 (wsl 버전으로 2로 변경)
- wsl --set-default Ubuntu-20.04 (wsl 명령에서 실행에 사용할 기본 Linux 배포판 설정)
- wsl -d Ubuntu-20.04 cat /etc/os-release

- wsl -t ubuntu-20.04 (terminate)

## Linux File Position

- windows key + r
- \\wsl$\Ubuntu-20.04
- explorer.exe .

## Port Forwarding

- powershell (관리자 모드)
  - cd /
  - dir
  - .\ports_wsl.ps1

## Can't open display

- Xming install
- Machine ID 생성
  - sudo systemd-machine-id-setup
  - sudo dbus-uuidgen --ensure
  - cat /etc/machine-id

- sudo apt-get install x11-apps xfonts-base xfonts-100dpi xfonts-75dpi xfonts-cyrillic
- export DISPLAY=$(cat /etc/resolv.conf | grep nameserver | awk '{print $2}'):0
- echo $DISPLAY
- cat /etc/resolv.conf
- export DISPLAY=172.26.16.1:0

- sudo vi ~/.bashrc
  - export DISPLAY="`grep nameserver /etc/resolv.conf | sed 's/nameserver //'`:0"
  - export LIBGL_ALWAYS_INDIRECT=1
- source ~/.bashrc
