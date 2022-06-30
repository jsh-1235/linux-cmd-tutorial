# Power

## reboot (halt, poweroff, reboot - Halt, power-off or reboot the machine)

- reboot
- reboot --halt (Halt the machine.)
- reboot -f (Force immediate halt, power-off, or reboot.)
- reboot -p (Power-off the machine, regardless of which one of the three commands is invoked.)

## shutdown

- shutdown -k now (모든 사용자에게 경고 메시지만 보내고 동작은 수행하지만, 실제로 시스템을 종료하지는 않음)
- shutdown -h now (시스템 shutdown 후 종료(halt)를 실행)
- shutdown -P +1 (Poweroff)
- shutdown -r +1 (1분 후 종료하고 다시 시작한다.)
- shutdown -r now (reboot)
- shutdown -f now (Fast Reboot: 재시작 시 fsck(file system check)를 실행하지 않음)
- shutdown -c (셧다운 취소)

## halt

## poweroff

- poweroff는 하드디스크와 메모리를 동기화 시키지 않고 바로 종료시키므로 가급적 사용하지 않는게 좋다.
- 사용할 경우 동기화 명령어인 sync 명령으로 동기화를 수행하고 사용하는 것이 좋다.
- poweroff
