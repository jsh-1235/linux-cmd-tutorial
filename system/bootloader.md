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

## grub

- ubuntu : shift
- centOS : e

## 시스템 종료와 재부팅

- init (RunLevel 선택 명령어)
- 0 (종료 모드: halt)
- 1 (단일 사용자 모드: 시스템 복구 시 사용한다.)
- 2 (다중 사용자 텍스트 모드: NFS와 X-Window 환경을 제외한 부팅)
- 3 (다중 사용자 텍스트 모드: X-Window 환경을 제외한 부팅)
- 4 (사용 안함)
- 5 (다중 사용자 그래픽 모드: X-Windows 환경으로 모든 서비스 포함)
- 6 (재부팅 모드: reboot)

- init -t 10 0 (10초 뒤에 시스템 종료)

## runlevel

- runlevel
- who -r
- systemctl get-default
- ls /lib/systemd/system/runlevel?.target -ls
