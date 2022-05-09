# Process

## ps (report a snapshot of the current processes.)

- ps
- ps -aux (To see every process on the system using BSD syntax)
- ps aux | grep vim

## top

- top (display Linux processes)

## htop (interactive process viewer)

- htop

## kill (send a signal to a process)

- kill -9 %1

## Multi Task

- ls -alR / > result.txt 2> error.log
- ls -alR / > result.txt 2> error.log &
- ctrl + z (change background)
- jobs
- fg (Move job to the foreground.)
- fg 1
- kill %1
- kill -9 %1

## sleep (delay for a specified amount of time)

- sleep 1s
- sleep 1m
- sleep 1s
- sleep 5; pwd;
