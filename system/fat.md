# File System

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
