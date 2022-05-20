# Process

- 프로그램 실행 단위
- Multitasking Operating System : 여러 프로세스를 고속으로 전환하여 동시에 실행되는 것처럼 운영한다.
- Scheduling : 어떤 프로세스를 어떤 순서로 전환할지 정하는 것
- Thread : 프로세스 보다 빠르고 효율적인 병렬 처리 단위 (같은 프로세스에서 실행되므로 스레드끼리 자원을 빠르고 효율적으로 공유할 수 있다.)
- Multi Thread

## top

- 현재 시스템에서 실행되고 있는 프로세스 상태를 실시간으로 화면에 출력해 준다.
- top (display Linux processes)

## htop (interactive process viewer)

- htop

## ps (report a snapshot of the current processes.)

- Process Parameters
  - USER
  - PID
  - PPID (Parent Process ID)
  - %CPU : CPU 이용률
  - %MEM : 메모리 이용률
  - VSZ : 가상 이미지 크기 (text + data + stack)
  - RSS : 실제 메모리 크기
  - TTY : 제어 터미널
  - STAT
    - 프로세서 상태
      - R : Runnable
      - S : Sleep
      - D : 디스크 내부
      - T : Halt (정지 상태)
      - Z : Zombi (좀비 상태)
    - 보조 정보
      - < : 우선 순위가 높은 프로세스
      - N : 우선 순위가 낮은 프로세스
      - L : 메모리 내에 락이 걸린 페이지가 있음
      - s : 섹션 리더
      - l : 멀티 스레드
  - START : 시작 시간
  - TIME : CPU 시간
  - COMMAND : 명령어
  - PRI : 실제 실행 우선 순위
  - NI : nice 우선순위 번호
  - WCHAN : 프로세스를 기다리고 있는 이벤트
  - PLAGS : 프로세스와 관련된 숫자 값
  - C(sysV), CP(BSD) : 짧은 기간 동안의 CPU 사용률

- ps 1000 (pid)
- ps t0 (tty)
- ps -aux (To see every process on the system using BSD syntax)
- ps aux | grep vim
- ps [-auxwmt]
  - a : 모든 사용자의 프로세서 정보 표시
  - u : 사용자명과 시작 시각 등을 표시
  - x : 제어 터미널이 없는 프로세서 정보(데몬 등)를 표시
  - f : 프로세스의 부모 자식 관계를 트리 형태로 표시
  - w : 프로세스의 정보 표시 내용을 늘린다.
  - m : Thread 표시
  - t : 제어 터미널 표시
  - U user : user 사용자가 실행한 프로세서만 표시 (ps -U jsh)
  - l : PRI (Priority)
- ps -alx
- ps -al

## jobs (Display status of jobs.)

- [1]+ Running xeyes & (작업 번호|현재 작업|작업 상태|프로그램명)
  - [%%, %+] : 현재 작업
  - [%-] : 이전 작업
  - [%n] : n번 작업
  - [%string] : string으로 시작하는 작업
  - [%?string] : string이 포함된 작업
- jobs %% (현재 작업)
- jobs %+ (현재 작업)
- jobs %- (이전 작업)
- jobs %n

## fg (Foreground execution)

- fg
- fg %n
- ctrl + c (강제 종료)
- ctrl + z (실행 정지 : Stopped)
- ctrl + d (작업 정상 종료)

## bg (Background execution)

- xeyes &
- xcalc &
- bg
- bg %n (n번 작업 백그라운드로 실행)

## kill (send a signal to a process)

- kill %%
- kill %-
- kill %n
- kill -STOP %% (현재 작업에 Stop Signal을 보낸다.)
- kill -9 %1
- kill -KILL 256 (PID)
- kill -HUO %2 (작업 번호 : 실행 중인 데몬 등의 설정을 변경했을 때 해당 프로세스를 재시작한다.)
- SIGNAL
  - HUP (1: Hangup) : 프로세스에 재시작 신호를 보냅니다.
  - INT (2) : 프로세에 끼어들기 신호를 보냅니다.
  - QUIT (3) : 프로세스에 종료 신호를 보낸다. (core 작성)
  - KILL (9) : 프로세스에 강제 종료 신호를 보낸다.
  - TERM (15): 프로세스에 종료 신호를 보낸다.
  - CONT (18): 프로세서에 재개 신호를 보냅니다.
  - STOP (19): 로세스에 정지 신호를 보냅니다.

## killall

- 프로세서를 이름을 지정하여 프로세스를 종료시킬 수 있다.
- 보통 데몬을 종료시킬 때 유용하다.
- killall -l (list all known signal names)
- killall xeyes
- killall apache2

## nice (run a program with modified scheduling priority)

- 프로세스의 스케줄링 우선권을 변경하여 프로그램을 수행한다.
- 조정 범위 : -20 ~ 19
- 일반 사용자는 NI 값을 증가만 시킬= 수 있고 관리자인 root는 값을 감소시켜 우선순위를 높일 수 있다.
- nice xeyes & (기본: NI + 10 = 10)
- nice -n 19 xeyes & (0 + 19)
- ps -al | grep xeyes

## renice

- 실행중인 프로세스의 우선순위를 변경하는 명령어이다.
- xeyes &
- ps -al | grep xeyes
- renice 10 -p pid

## pstree

- 프로세스들을 계층적인 트리구조 형태로 출력해준다.
- pstree