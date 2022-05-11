# wsl (Windows Subsystem for Linux)

- wsl --update
- wsl --list --online
- wsl -l -v
- wsl -t ubuntu-20.04 (terminate)
- wsl --shutdown Ubuntu-20.04

## Execution

- windows key + r
- ws
- wsl -l -v
- ubuntu2004.exe

## Linux File Position

- windows key + r
- \\wsl$\Ubuntu-20.04
- explorer.exe .

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
