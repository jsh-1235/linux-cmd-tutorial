# Process

- 프로그램 실행 단위
- Multitasking Operating System : 여러 프로세스를 고속으로 전환하여 동시에 실행되는 것처럼 운영한다.
- Scheduling : 어떤 프로세스를 어떤 순서로 전환할지 정하는 것
- Thread : 프로세스 보다 빠르고 효율적인 병렬 처리 단위 (같은 프로세스에서 실행되므로 스레드끼리 자원을 빠르고 효율적으로 공유할 수 있다.)
- Multi Thread

## top

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
  - STOP (19): 프로세스에 정지 신호를 보냅니다.
- killall xeyes

## nice (run a program with modified scheduling priority)

- nice xeyes & (기본 NI + 10)
- nice -19 xeyes & (0 + 19)
