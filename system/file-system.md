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

## 파일 시스템의 생성 (파티션 만들기)

- 시스템을 운영하던 중 하드디스크의 용량 부족으로 인하여 새로운 하드디스크를 추가할 경우 리눅스 시스템이 사용할 수 있게 파티션을 생성하고 파일 시스템을 만들어 주어야 한다.
- 파티션은 Primary Partition, Extended Partition, 확장 파티션 내 논리 파티션으로 구분하며, 논리 파티션은 확장 파티션을 만들 경우 메뉴에 출력된다.

- 가상 하드 디스크 만들기
  - Controller (SATA)
  - 하드 디스크 파일 종류 (VHD: 가상 하드 디스크)

- fdisk, parted

- fdisk /dev/sdb
  - m (print this menu)
  - n (add a new partition)
  - p (Primary partition)
  - d (delete a partition)
  - w (write table to disk and exit)
- fdisk -l | grep sdb*
  - /dev/sdb1        2048 2097151 2095104 1023M 83 Linux

## 파일 시스템의 만들기 (format)

- fdisk 명령어를 이용하여 새로운 하드디스크의 파티션 테이블을 만들어 주었다면, 해당 파티션에 파일 시스템을 생성해 주어야한다.
- mke2fs, mkfs

- mkfs.ext4 /dev/sdb1

## 파일 시스템 마운트

- 리눅스는 파일 단위로 관리를 하게 되며 새롭게 만든 파일시스템을 사용하기 위하여 생성된 디스크 장치를 트리 구조의 임의의 디렉토리 즉, 마운트 포인트에 연결시켜야 한다.
- 윈도우 시스템은 드라이브 볼륨 문자로 지정해서 사용하는 방식
- Mount Point
  - 파일시스템을 디렉토리로 연결해야 하는데, 이 때 연결되는 디렉토리를 의미한다.
  - 최상위 디렉토리(/) 파일시스템에 존재하기 때문에, 사용 중이던 디렉토리를 마운트 포인트로 이용할 경우에는 존재하던 파일과 디렉토리를 사용할 수 없게 되므로 마운트 포인트는 비어 있는 디렉토리를 사용해야 한다.

- mount /dev/sdb1 /media/jsh/hdd
- df -h | grep sdb1
- du -sh /media/jsh/hdd

- dmesg | grep sdb1
- blkid | grep sdb1

## /etc/fstab

- 리눅스가 부팅되면서 파일 시스템을 어디에 자동으로 마운트하고, 외부 장치들에 대한 마운트를 어떻게 설정하는지, 권한 및 복구 등의 옵션을 어떻게 이용할지 지정하는 파일이다.
- 시스템 부팅 시 /etc/fstab에 기록되어 있는 순서대로 파티션이 마운트 되어 한 개의 디렉토리 트리가 만들어 진다.
- cat /etc/fstab

## fdisk

- fdisk -l (현재 시스템의 파티션 테이블 확인)
- du -sh /media/jsh/hdd
- ls -l /media/jsh/hdd

## df (report file system disk space usage, Disk Free)

- 각 파일 시스템 디스크 사용량을 표시한다.
- [전체용량, 사용중인 용량, 사용 가능한 용량, 사용률, Mount Point]
- df [-ahHt]
- df -a (include pseudo, duplicate, inaccessible file systems)
- df -i (list inode information instead of block usage)
- df -k (like --block-size=1K)
- df -h (human readable: print sizes in powers of 1024)
- df -H (human readable: print sizes in powers of 1000)
- df -t (limit listing to file systems of type TYPE)
- df -x (limit listing to file systems not of type TYPE)

## du (estimate file space usage, Disk Usage)

- 현재 디렉토리 이하 디스크 사용량을 표시한다.
- du [-abhsd]
- du -a (write counts for all files, not just directories)
- du -b (Byte, ls -l)
- du -h (print sizes in human readable format)
- du -l (count sizes many times if hard linked)
- du -s (display only a total for each argument)

- du -sh ~
- du -shL ~ (dereference all symbolic links)

- du /etc | sort -n | tail -n 5
- du /etc | sort -r | tail -n 5
- du -sh ~ (홈 디렉토리의 전체 용량 확인)
- du -sh /var/* (var 디렉토리의 전체 용량 확인)

## fallocate (Preallocate space to, or deallocate space from a file.)

- fallocate -l 1K file-name
- fallocate -l 1M file-name
- fallocate -l 1G file-name

## mount

- mount (현재 시스템의 마운트 정보를 확인)
- mount | grep "C:"
- mount / (마운트된 정보 확인)
  - mount: /: /dev/sda3 already mounted on /.

## umount

- umount [mount-point]
- umount /media/jsh/VBox_GAs_6.1.34

## lsusb (list USB devices)

- 시스템에 어떤 USB 디바이스가 연결됐는지 확인한다.
- lsusb
  - Bus 001 Device 002: ID 090c:1000 Silicon Motion, Inc. - Taiwan (formerly Feiya Technology Corp.) Flash Drive

## dmesg

- dmesg | grep 090c

## lsblk (list block devices)

- lsblk
- lsblk -a

## blkid (locate/print block device attributes)

- blkid

## USB 인식

- df -h
  - /dev/sdb1       3.8G  3.8G   29M 100% /media/jsh/644A-AED8

- fdisk -l | grep FAT32
  - 부착된 장치 이름 찾기

- fdisk -l | grep sdb1
  - /dev/sdb1          56 7866367 7866312  3.8G  c W95 FAT32 (LBA)

- lsusb
  - Bus 001 Device 003: ID 090c:1000 Silicon Motion, Inc. - Taiwan (formerly Feiya Technology Corp.) Flash Drive

- dmesg | grep 090c

- lsblk | grep sdb1 (마운트 포인터 확인)
  - sdb1   8:17   1   3.8G  0 part /media/jsh/644A-AED8

- blkid | grep sdb1
  - /dev/sdb1: UUID="644A-AED8" BLOCK_SIZE="512" TYPE="vfat" PARTUUID="c3072e18-01"

- umount /media/jsh/644A-AED8

- mount /dev/sdb1 /media/jsh/usb

- ls -al  /media/jsh/usb
