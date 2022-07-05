# 시스템 초기화

## init

- 모든 UNIX 계열의 시스템에서 가장 먼저 실행되는 프로세스이다.
- 모든 프로세스의 부모(Parent) 프로세스이다.
- 부팅 시에 커널이 수행하는 맨 마지막 과정이다.
- init은 파일시스템 검사, 마운트, 데몬의 구동 및 CMOS와 운영체제의 시간을 맞추는 등의 시스템 시동에 필요한 갖가지 작업을 수행한다.
- init 프로세스는 사용자가 시스템을 사용할 수 있는 환경을 만들어 주는데 이러한 과정을 시스템 초기화라고 한다.
- 로그인 프롬프트가 나오기 전까지 파일시스템 점검, 필요한 커널 모듈의 메모리 적재, 스와 파티션 초기화, 네트워크 초기화, 서비스 프로세스 관리, 가상 콘솔 접속 관리, 실행 레벨 관리, /etc/fstab에 명시되어 있는 각 파티션들을 마운트하는 과정을 수행한다.

## inittab

- init 프로세스가 참조하는 파일, 즉 처리방법을 지정하고 있는 파일이다.
  - /etc/inittab
  - id:run level:action:process

## id

- inittab 파일 안에서 각 항목들에 대한 식별자이다.

## run level

- 0 [poweroff.target]
  - 시스템 종료 모드: halt

- 1 [rescue.target]
  - 단일 사용자 모드 (Single User Mode)
  - 사용자명이나 패스워드를 요구하지 않는다.
  - 시스템 복구 시 사용한다.

- 2 [multi-user.target]
  - 다중 사용자 텍스트 모드(Multi User Text Mode)
  - 네트워크를 사용하지 않는다.
  - NFS와 X-Window 환경을 제외한 부팅

- 3 [multi-user.target]
  - 다중 사용자 텍스트 모드(Multi User Text Mode)
  - 네트워크를 사용한다.

- 4 [multi-user.target]
  - 사용 안함 (Unused)

- 5 [graphical.target]
  - Default Run Level
  - 다중 사용자 그래픽 모드(Multi User Graphic Mode)
  - 네트워크를 사용한다.
  - X 윈도우 시스템을 사용한다.

- 6 [reboot.target]
  - 시스템 재 부팅 (reboot)

## action

- 프로세스가 어떠한 방식으로 실행할 것인가를 나타낸다.
  - respawn : 프로세스가 종료되면 항상 다시 시작하게 한다.
  - wait : 프로세스를 실행하고, init는 해당 프로세스가 종료될 때까지 기다린다.
  - once : 프로세스를 한번만 실행한다.
  - boot : 부팅 시에 프로세스를 실행하며, 이 경우 run level 값이 무시된다.
  - bootwait : 부팅 시에 프로세스를 실행하며, init는 해당 프로세스가 종료될 때까지 기다린다. 이 경우 run level 값이 무시된다.

## init command

- init -t 10 0 (10초 뒤에 시스템 종료)

## runlevel command

- man runlevel

- runlevel
  - N 5

- type runlevel
  - runlevel is hashed (/usr/sbin/runlevel)

- who -r (print current runlevel)

- systemctl get-default (Return the default target to boot into.)
  - graphical.target

- systemctl set-default multi-user.target
- systemctl set-default graphical.target
