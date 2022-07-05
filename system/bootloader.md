# Boot Loader

- 부트로더는 컴퓨터를 시작할 때 동작해서 디스크에 설치된 OS 등을 부팅하는 프로그램이다.
- 운영 체제의 부팅 이전에 먼저 실행되는 프로그램으로 커널이 올바르게 부팅되기 위해 필요한 모든 관련 작업을 마무리하고 최종적으로 운영 체제를 부팅 시키키 위한 목적을 가지고 있다.

## 리눅스 시스템 부팅 과정

- 시스템 전원 ON
- BIOS 프로그램 실행
- 부팅매체 검색 (CMOS 설정에 의한 부팅 시도)
- 부트로더(GRUB) 실행
- 커널 부트 이미지 적제
- 루트(/) 파일시스템 마운트
- INIT 프로세스 실행 (/etc/inittab 설정 내용 실행)

## Boot Manager

- 부트 매니저 (Boot Manager)는 보조기억장치에 위치한 운영체제를 주기억장치로 로드하기 위한 프로그램이다.
- BIOS -> MBR (Master Boot Record: 0번 섹터[512byte]) -> IPL (Initial Program Loader)
- IPL은 파티션 테이블을 검사하여 부트 로더의 나머지 코드의 위치를 알아내서 실행한다.

## LILO (Linux LOader)

- 모든 리눅스 배포판의 표준이자 가장 오랜된 부트 로더로서 리눅스 커뮤니티의 지속적인 지원을 받고 있다.

## GRUB (GRand Unified Bootloader)

- GNU 프로젝트에서 만든 부트 로더이다.
- LILO의 단점을 보완한 매우 강력한 기능 때문에 Linux의 기본 부트로더로 자리 잡았다.
- LILO와 달리 대화형 명령어 인터페이스를 제공하고 네트워크 부팅을 제공한다.
- Chain-loader를 이용하여 Linux, Window, FreeBSD 등 다양한 운영체제등과 멀티부팅이 가능하다.
- 시스템 BIOS에서 인식하는 모든 디바이스들에 액세스가 가능하다.

- configuration file
  - vim /boot/grub/grub.cfg

- grub에 패스워드 설정
  - grub-md5-crypt

- booting option
  - ubuntu : shift ore F12
  - centOS : e

## 관리자 패스워드 복구 (Recovery Mode)

- GNU GRUB 메뉴 불러 오기
  - F12 or shift (ubuntu)

- 설정
  - e (edit the commands before booting) (편집 모드로 들어 가기)
  - ro ... -> rw single init=/bin/bash (편집 하기)
  - Ctrl + x or F10 (편집 완료)
-
- 새로운 관리자 패스워드 등록
  - passwd

- 변경 사항 적용
  - exec /sbin/init
  - systemctl reboot -f (force)
