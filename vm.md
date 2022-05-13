
# VM

## VM 설정

- 마우스 통합
  - 파일 - 환경 설정 -> 입력 -> 가상 머신
  - Right Ctrl (Exit) -> Ctrl + Alt
  - Ctrl + Alt + Del or Win + L (Exit)

- 클립보드 공유
  - 머신 -> 설정 -> 일반 -> 고급
  - 양방향

- 터미널 화면 크기
  - ctrl + shift + '+' (확대)
  - ctrl + '-' (축소)

## hostname

- vi /etc/hostname
- docker-ubuntu -> docker-ubuntu.example.com

## hosts file

- sudo vi /etc/hosts
- 10.0.2.105 docker-ubuntu.example.com docker-ubuntu
- ping -c 5 docker-ubuntu.example.com
- ping -c 5 8.8.8.8

## Booting Mode

- sudo passwd root
- su - root
- systemctl get-default
- systemctl set-default multi-user.target (CUI Mode)
- sudo systemctl set-default graphical.target (GUI Mode)
- reboot

## ubuntu install

- apt update
- apt install -y openssh-server curl vim tree
- dpkg -l | grep openssh-server

- sudo vi /etc/ssh/sshd_config
- port 22 -> port 22221

## centOS install

- yum update
- yum list (저장소 서버에 있는 모든 패키지 목록)
- yum list updates
- yum list available (설치된 패키지 목록)
- yum list available | grep openssh*
- yum install -y openssh-server curl vim tree
- yum remove openssh-server
- dpkg -l | grep openssh-server

- sudo vi /etc/ssh/sshd_config
- port 22 -> port 22222
