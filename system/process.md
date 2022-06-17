# Process

- 프로그램 실행 단위
- 프로그램이나 명령어가 메모리에 적재되어 실행되고 있는 상태
- Multitasking Operating System : 여러 프로세스를 고속으로 전환하여 동시에 실행되는 것처럼 운영한다.
- Scheduling : 어떤 프로세스를 어떤 순서로 전환할지 정하는 것
- Thread : 프로세스 보다 빠르고 효율적인 병렬 처리 단위 (같은 프로세스에서 실행되므로 스레드끼리 자원을 빠르고 효율적으로 공유할 수 있다.)
- Multi Thread

## PID

- 프로세스들은 프로세스가 시작하면서 할당받는 프로세스 식별번호인 PID(Process ID), 해당 프로세스를 실행한 부모 프로세스를 나타내는 PPID(Parent Process ID) 갖는다.
- UID와 GID 정보를 통해 해당 프로세스가 어느 사용자에 속해 있는지, 프로세스가 파일에 대해 갖는 권한 및 프로세스가 실행된 터미널, 입력된 명령어, 시작 시간 등 많은 정보를 가지고 있다.

## top

- 현재 시스템에서 실행되고 있는 프로세스 상태를 실시간으로 화면에 출력해 준다.
- top (display Linux processes)

## htop (interactive process viewer)

- htop

## ps (report a snapshot of the current processes.)

- Process Parameters
  - USER
  - PID : 프로세스가 갖는 식별 번호
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
  - START (STIME) : 시작 시간
  - TIME : 총 CPU 사용 시간
  - COMMAND (CMD) : 실행한 명령어 라인
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
  - a : 제어 터미널을 가지는 모든 사용자의 프로세서 정보 표시
  - e, -A : 시스템에서 실행 중인 모든 프로세스의 상태 출력
  - x : 제어 터미널이 없는 프로세서 정보(데몬 등)를 표시
  - u : 사용자명과 시작 시각 등을 표시
  - f : 프로세스의 부모 자식 관계를 트리 형태로 표시
  - w : 프로세스의 정보 표시 내용을 늘린다.
  - m : Thread 표시
  - t : 제어 터미널 표시
  - U user : user 사용자가 실행한 프로세서만 표시 (ps -U jsh)
  - l : PRI (Priority)
- ps -alx (PRI, NI)
- ps -al

## pstree (display a tree of processes)

- 프로세스들을 계층적인 연결 구조를 트리구조 형태로 출력해준다.
- pstree
- pstree -a (Show command line arguments)
- pstree -p (Show PIDs; implies -c)
- pstree -u (Show uid transitions)
- pstree -h (Highlight the current process and its ancestors.)
- pstree -n (Sort processes with the same parent by PID instead of by name.)

## jobs (Display status of jobs.)

- [1]+ Running xeyes & (작업 번호|현재 작업|작업 상태|프로그램명)
  - [%%, %+] : 현재 작업
  - [%-] : 이전 작업
  - [%n] : n번 작업
  - [%string] : string으로 시작하는 작업
  - [%?string] : string이 포함된 작업
- jobs (사용자가 실행시킨 프로세스의 리스트 확인)
- jobs -l (lists process IDs in addition to the normal information)
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

- kill -l (list the signal names)

- kill %%
- kill %-
- kill %n
- kill -STOP %% (현재 작업에 Stop Signal을 보낸다.)
- kill -9 %1
- kill -KILL 256 (PID)
- kill -HUO %2 (작업 번호 : 실행 중인 데몬 등의 설정을 변경했을 때 해당 프로세스를 재시작한다.)
- SIGNAL (실행 중에 있는 프로세스에게 전달하는 메시지)
  - HUP (1: Hangup) : 프로세스에 재시작 신호를 보냅니다.
  - INT (2) : 프로세에 끼어들기 신호를 보냅니다. (Ctrl + c)
  - QUIT (3) : 프로세스에 종료 신호를 보낸다. (core 작성)
  - KILL (9) : 프로세스에 강제 종료 신호를 보낸다. (커널이 직접 프로세스 종료, 강제 종료, 즉시 종료)
  - TERM (15): 프로세스에 종료 신호를 보낸다. (저장할 데이터가 있을 시에는 저정 후 프로세스 종료)
  - CONT (18): 프로세서에 재개 신호를 보냅니다.
  - STOP (19): 로세스에 정지 신호를 보냅니다.

## pkill (look up or signal processes based on name and other attributes)

- pkill -SIGNAL PID
- kill -KILL 1647

## killall

- 프로세서를 이름을 지정하여 프로세스를 종료시킬 수 있다.
- 보통 데몬을 종료시킬 때 유용하다.
- killall -l (list all known signal names)
- killall xeyes
- killall apache2

## Process Priority

- 리눅스 시스템은 한번에 여러 개의 프로그램이 동시에 작동할 수 있는 시스템이다.
- 프로세스의 중요도를 따지 위해 프로세스 우선 순위(Priority)를 설정한다.
- PRI 조정범위 : -20 ~ +19, Default : 0
- 일반 사용자는 NI 값을 증가만 시킬 수 있고 관리자인 root는 값을 감소시켜 우선순위를 높일 수 있다.

## nice (run a program with modified scheduling priority)

- 프로세스의 스케줄링 우선권을 변경하여 프로그램을 수행한다.
- 프로세스를 실행할 때 우선 순위를 설정할 수 있다.

- nice xeyes & (기본: NI + 10 = 10)
- nice -n 19 xeyes & (0 + 19)
- ps -al | grep xeyes

## renice (alter priority of running processes)

- xeyes &
- ps -el | grep xeyes
- renice 10 -p PID

## snice (send a signal or report process status)

- 실행중인 프로세스의 우선순위를 변경하는 명령어이다.
- snice -l (List all signal names.)
- snice -L (List all signal names in a nice table.)
- ps -el | grep xeyes
- jobs -l
- snice -n PID
- snice +n PID

## nohub

- 사용자가 시스템 작업을 실행 한 후 로그아웃을 해야 하는 경우에 사용하는 명령어이다.
- 로그아웃을 하더라도 작업이 계속 진행될 수 있도록 할 때 유용하다.
- 백업이나 tar 명령어를 통해 많은 파일을 압축하는 경우나, wget, ftp를 이용해 용량아 큰 파일을 다운로드 받을 때 시간이 많이 소요되므로 유용하게 사용된다.

- nohup find / -name cat* &
- cat nohup.out (작업 출력 내용 저장)

- ps -el | grep find
- kill -KILL 2837

## mc (Visual shell for Unix-like systems.)

- mc

## setup

## yes (print a random, hopefully interesting, adage)

- yes (output a string repeatedly until killed)
- yes I love you.
- ctrl + c (exit)
