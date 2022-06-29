# 시스템 초기화

- Boot Loader
  - 시스템에 부팅 시킬 운영체제 선택 (Linux)
  - 운영체제가 하드웨어 인식 및 마운트
  - LILO(Linux LOader)
  - GRUP(GRand Unified Boot Loader)
    - /sbin/grup (실행 파일)
    - /etc/grup.conf (참조 파일)

- init
  - UNIX 계열의 시스템에서 가장 먼저 실행되는 프로세서이며 모든 프로세스의 부모(Parent)이다.
    - pstree -p
  - 부팅 시에 커널이 수행하는 맨 마지막 과정이다.
  - 시스템 초기화 작업 실행
    - 파일 시스템 검사
    - 마운트
    - 데몬의 구동
    - CMOS와 운영체제의 시간을 맞추는 과정 수행
  - /sbin/init (실행 파일)
  - /etc/inittab (참조 파일 : 처리 방법을 지정하는 파일이다.)

- mingetty (MINimal GET TeleType writer)
  - 콘솔을 초기화하고 로그인 프롬프트를 생성시키는 과정도 포함한다.
  - 사용자가 시스템을 로그아웃하게 되면 'mingetty' 프로세스가 다시 로그인 프롬프트를 발생시켜 다음 사용자 로그인을 준비하게 된다.
  - /sbin/mingetty (실행 파일)
  - /etc/issue (로그인하기 전 사용자에게 나타낼 메시지 포함)
  - /etc/issue.net (네트워크를 이용해 접속하는 사용자 메시지)

- login
  - 'login'  프로세스가 사용자 인증(Authentication)을 수행하고 마지막으로 셸을 구도시키면 시스템을 사용할 수 있다.
  - /etc/login.defs (패스워드 정책을 비롯한 여러 가지 정보를 설정하는 파일이다.)
  - /etc/passwd
  - /etc/group
  - /etc/motd (로그인 후 출력되는 메시지)

- shell
  - /bin/bash
  - /etc/profile
  - /etc/bashrc

- logout