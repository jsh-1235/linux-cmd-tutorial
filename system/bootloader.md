# daemon

- 부트로더는 컴퓨터를 시작할 때 동작해서 디스크에 설치된 OS 등을 부팅하는 프로그램이다.

## GRUB2

- start + [shift]
- F12

## 싱글 유저 모드 (Read Only)

- Ubuntu용 고급 설정 -> recovery mode

## 싱글 유저 모드 (Read & Write)

- Ubuntu용 고급 설정 -> recovery mode -> e

## Boot Manger

- 부트 매니저 (Boot Manager)는 보조기억장치에 위치한 운영체제를 주기억장치로 로드하기 위한 프로그램이다.
- BIOS -> MBR (Master Boot Record: 0번 섹터[512byte]) -> IPL (Initial Program Loader)
- IPL은 파티션 테이블을 검사하여 부트 로더듸 나머지 코드의 위치를 알아내서 실행한다.

- LILO (Linux Loader)
  - 모든 리눅스 배포판의 표준이자 가장 오랜된 부트 로더로서 리눅스 커뮤니티의 지속적인 지원을 받고 잇다.
- GRUB (Grand Unified BootLoader)
  - GNU 프로젝트에서 만든 부트 로더이다.
  - LILO와 달리 대화형 명령어 인터페이스를 제공하고 네트워크 부팅을 제공한다.
  - cat /boot/grub/grub.cfg

- 부트 로드란 운영 체제의 부팅 이전에 먼저 실행되는 프로그램으로 커널이 올바르게 부팅되기 위해 필요한 모든 관련 작업을 마무리하고 최종적으로 운영 체제를 부팅 시키키 위한 목적을 가지고 있다.

## LILO (Linux LOader)

## grub (GRand Unified Bootloader)

- LILO의 단점을 보완한 매우 강력한 기능 때문에 Linux의 기본 부트로더로 자리잡았다.
- Chain-loader를 이용하여 Linux, Window, FreeBSD 등 다양한 운영체제등과 멀티부팅이 가능하다.
- 메뉴 인터페이스를 제공한다.
- 시스템 BIOS에서 인식하는 모든 디바이스들에 액세스가 가능하다.

- vim /boot/grub/grub.cfg

## grub에 패스워드 설정

- grub-md5-crypt

## booting option

- ubuntu : shift
- centOS : e

## single user mode booting

- 관리자 패스워드 복구
- F12
- ubuntu : shift
- e
- ro ... -> rw single init=/bin/bash
- Ctrl + x or F10
- passwd
- exec /sbin/init
- systemctl reboot

## 리눅스 시스템 부팅 과정

- 시스템 전원 ON
- BIOS 프로그램 실행
- 부팅매체 검색 (CMOS 설정에 의한 부팅 시도)
- 부트로더(GRUB) 실행
- 커널 부트 이미지 적제
- 루트(/) 파일시스템 마운트
- INIT 프로세스 실행 (/etc/inittab 설정 내용 실행)

## INIT 프로세스

- INIT 프로세스는 사용자가 시스템을 사용할 수 있는 환경을 만들어 주는데 이러한 과정을 시스템 초기화라고 한다.
- 로그인 프롬프트가 나오기 전까지 파일시스템 점검, 필요한 커널 모듈의 메모리 적재, 스와 파티션 초기화, 네트워크 초기화, 서비스 프로세스 관리, 가상 콘솔 접속 관리, 실행 레벨 관리, /etc/fstab에 명시되어 있는 각 파티션들을 마운트하는 과정을 수행한다.

## 시스템 종료와 재부팅

- init (RunLevel 선택 명령어)
- 0 [poweroff.target] (종료 모드: halt)
- 1 [rescue.target] (단일 사용자 모드: 시스템 복구 시 사용한다.)
- 2 [multi-user.target] (다중 사용자 텍스트 모드: NFS와 X-Window 환경을 제외한 부팅)
- 3 [multi-user.target] (다중 사용자 텍스트 모드: X-Window 환경을 제외한 부팅)
- 4 [multi-user.target] (사용 안함)
- 5 [graphical.target] (다중 사용자 그래픽 모드: X-Windows 환경으로 모든 서비스 포함)
- 6 [reboot.target] (재부팅 모드: reboot)

- init -t 10 0 (10초 뒤에 시스템 종료)

## runlevel

- runlevel
- who -r
- systemctl get-default
- ls /lib/systemd/system/runlevel?.target -ls

- systemctl set-default multi-user.target
- systemctl set-default graphical.target
- systemctl get-default
