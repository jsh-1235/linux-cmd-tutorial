# File System

- 저장 장치를 영역별로 나누는 것을 파티션(Partition)이라고 한다.
- 디바이스 드라이버로 추상화한 디바이스를 S/W 입출력하기 편하도록 디바이스 노드 파일로 나타낸다.
- 디바이스 노드는 /dev 디렉토리 아래에 존재한다.
- 저장 장치는 /dev/sda 같은 명칭을 사용한다.
- 디바이스 노드를 파일처럼 사용해서 디바이스와 데이터를 주고 받습니다.

- ls -lF /dev
- Partition (GUID / MBR)
- ls -lF /dev/sd*
- sda (sd: SCSI, a: First Disk)
- sdb (sd: SCSI, a: Second Disk)

## mount

- mount
- mount | grep "C:"

## df (report file system disk space usage)

- 각 파일 시스템 디스크 사용량을 표시한다.
- df [-ahHt]
- df -a

## du (estimate file space usage)

- 현재 디렉토리 이하 디스크 사용량을 표시한다.
- du [-abhsd]
- du -ab
- du -ah
- du /etc | sort -n | tail -n 5
- du /etc | sort -r | tail -n 5

## lsblk (list block devices)

- lsblk
- lsblk -a

## mount (mount a filesystem)

- mount

## free (Display amount of free and used memory in the system)

- free

## lsusb (list USB devices)

- 시스템에 어떤 USB 디바이스가 연결됐는지 확인한다.
- lsusb

